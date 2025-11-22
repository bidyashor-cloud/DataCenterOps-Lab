# 📄 **README.md**

# 🏗️ My Virtual Lab (VirtualBox + Ubuntu Server)

This project is a complete virtual lab environment that I built using VirtualBox and Ubuntu Server.
It includes two fully configured virtual machines, internal networking, static IP setup, log collection, and basic troubleshooting scenarios — all created and tested on my own laptop.

---

## 🔧 **Technologies Used**

* VirtualBox
* Ubuntu Server 22.04 LTS
* Linux CLI / Bash
* NAT + Internal Network
* Netplan for static IPs
* System logs: `dmesg`, `syslog`, `journalctl`
* Tools: ping, ss, traceroute, free, df, top

---

## 📡 **Lab Architecture**

```
    +----------------------+
    |     VM1 – Server 1   |
    |     192.168.10.10    |
    +----------+-----------+
               |
               | Internal Network (intnet)
               |
    +----------+-----------+
    |     VM2 – Server 2   |
    |     192.168.10.20    |
    +----------------------+
```

Both VMs also use NAT for internet access.

This setup allowed me to install packages, test connectivity, simulate issues, and practice troubleshooting between two servers.

---

## ✔️ **What I Completed in This Lab**

### **1️⃣ Installed VirtualBox**

Documented in:
`setup/virtualbox-installation.md`

I installed VirtualBox on Windows and prepared the Ubuntu Server ISO.

---

### **2️⃣ Created Two Virtual Machines**

Documented in:
`setup/vm-creation.md`

I created VM1 manually and then cloned it to create VM2.
Both machines are fully installed and configured with Ubuntu Server.

---

### **3️⃣ Configured Networking + Static IPs**

Documented in:
`setup/network-configuration.md`

I assigned static IPs:

* VM1 → `192.168.10.10`
* VM2 → `192.168.10.20`

I set up:

* **Adapter 1:** NAT
* **Adapter 2:** Internal Network (intnet)

Ping tests and SSH connectivity were verified between both servers.

---

### **4️⃣ Collected System Logs**

Stored in the `logs/` folder:

* `syslog.txt`
* `dmesg.txt` (full actual output from VM1)

These logs helped me understand the boot process, network initialization, hardware detection, and warnings.

---

### **5️⃣ Troubleshooting I Performed**

(Stored in the `troubleshooting/` folder)

I tested and fixed several issues during the lab, including:

* Static IP misconfiguration
* Broken netplan YAML
* VirtualBox adapter issues
* SSH connection failures
* Network timeout and routing problems

---

## 📸 **Screenshots**

The `screenshots/` folder contains images of:

* Network adapter settings
* Static IP configuration
* Ping tests
* Successful SSH access
* Errors and fixes

---

## 🎓 **What I Learned**

* How to build and configure a multi-VM environment
* How NAT and internal networks work
* How to assign static IPs using Netplan
* How to troubleshoot Linux connectivity issues
* How to read system logs (`dmesg`, syslog, journalctl)
* How to debug VirtualBox networking and VM cloning issues

---

## ✔️ **Project Status: Completed**

This lab is fully set up, tested, verified, and documented.
All steps, logs, and configurations are included in this repository.

If I add anything in the future, it will simply be extra improvements or more troubleshooting examples.

---

# 🎉 Done!

---
