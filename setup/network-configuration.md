# 🛰️ Network Configuration for My VirtualBox Lab

This document explains how I set up networking for my two Ubuntu Server VMs in VirtualBox. My goal was to create a simple internal lab environment where both VMs can communicate with each other while still having internet access for updates and package installations.

To achieve this, I configured:

* NAT (for internet access)
* Internal Network (for private VM-to-VM communication)
* Static IP addresses on each VM
* Ping tests to verify connectivity

---

## 1️⃣ Setting Up the Network Adapters

Each VM uses **two** network adapters.

### **Adapter 1 — NAT (Internet Access)**

This adapter gives my VMs internet connectivity.

```
Adapter 1 → Enable Network Adapter
Attached to: NAT
```

---

### **Adapter 2 — Internal Network (VM-to-VM Communication)**

This adapter allows both VMs to communicate privately inside VirtualBox.

```
Adapter 2 → Enable Network Adapter
Attached to: Internal Network
Name: intnet
```

Both VMs use the same internal network name: `intnet`.

---

## 2️⃣ Configuring Static IPs Using Netplan

I set static internal IPs so each VM always has the same address.

---

## 🖥️ VM1 (Server 1) – Static IP

```
IP: 192.168.10.10
DNS: 8.8.8.8
```

Netplan configuration:

```yaml
network:
  version: 2
  ethernets:
    enp0s3:
      dhcp4: true
    enp0s8:
      dhcp4: false
      addresses:
        - 192.168.10.10/24
      nameservers:
        addresses:
          - 8.8.8.8
```

---

## 🖥️ VM2 (Server 2) – Static IP

```
IP: 192.168.10.20
DNS: 8.8.8.8
```

Netplan configuration:

```yaml
network:
  version: 2
  ethernets:
    enp0s3:
      dhcp4: true
    enp0s8:
      dhcp4: false
      addresses:
        - 192.168.10.20/24
      nameservers:
        addresses:
          - 8.8.8.8
```

---

## 3️⃣ Applying the Network Configuration

I applied the configuration:

```bash
sudo netplan apply
```

Then verified:

```bash
ip a
```

I confirmed:

* `enp0s3` received a NAT DHCP address
* `enp0s8` showed the static IP I configured

---

## 4️⃣ Testing Connectivity Between My VMs

I tested communication using `ping`.

From **VM1**:

```bash
ping 192.168.10.20
```

From **VM2**:

```bash
ping 192.168.10.10
```

Both responded, confirming the internal network works correctly.

---

## 5️⃣ Issues I Faced and How I Fixed Them

### ❌ VMs Could Not Ping Each Other

I checked:

* Adapter 2 was set to *Internal Network*
* Both VMs used the name `intnet`
* Firewall status:

```bash
sudo ufw status
```

### ❌ Static IP Was Not Applying

I used:

```bash
sudo netplan generate
sudo netplan apply
```

Then re‑checked YAML indentation.

### ❌ Internet Was Not Working

I verified that the NAT interface (`enp0s3`) was using:

```
dhcp4: true
```

### ❌ SSH Collisions After Cloning the VM

I fixed this by:

* Regenerating machine‑id
* Refreshing MAC addresses in VirtualBox
* Assigning different SSH port forwards for each VM

---

## 🏁 What I Completed Successfully

* Created two Ubuntu Server VMs
* Set up NAT for internet
* Set up an Internal Network for private communication
* Assigned static IPs (192.168.10.10 and 192.168.10.20)
* Verified VM‑to‑VM connectivity
* Enabled SSH access using separate port forwarding
* Fixed copy/paste issues by using SSH
* Resolved clone‑related MAC/machine‑id conflicts
* Fully built a working internal VirtualBox lab network

---

# ✔ Done!
