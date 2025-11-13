\# 🛰️ Network Configuration for My DataCenterOps Lab



In this part of my project, I am setting up the network for both of my VirtualBox VMs so they can talk to each other just like servers inside a real data center.

I will be configuring:



\* NAT (for internet access)

\* Internal Network (for private VM-to-VM communication)

\* Static IP addresses

\* Connectivity testing



---



\## 1️⃣ Setting Up Network Adapters in VirtualBox



Each VM needs \*\*two\*\* network adapters.



\### \*\*Adapter 1 — NAT\*\*



This gives the VM access to the internet so I can install updates.



Settings I selected:



```

Adapter 1 → Enable Network Adapter

Attached to: NAT

```



---



\### \*\*Adapter 2 — Internal Network\*\*



This allows both VMs to communicate with each other only inside VirtualBox.



Settings I selected:



```

Adapter 2 → Enable Network Adapter

Attached to: Internal Network

Name: intnet

```



I made sure both VMs use the \*\*same internal network name (`intnet`)\*\*.



---



\## 2️⃣ Configuring Static IP Addresses Inside the VMs



Now inside each VM, I set a \*\*static IP\*\* so the two systems always get the same address.



I opened the netplan file with:



```bash

sudo nano /etc/netplan/00-installer-config.yaml

```



---



\## 🖥️ VM1 (Server 1) – My Settings



I gave VM1 the following IP:



```

IP: 192.168.10.10

Gateway: 192.168.10.1

DNS: 8.8.8.8

```



My actual netplan config looked like this:



```yaml

network:

&nbsp; version: 2

&nbsp; ethernets:

&nbsp;   enp0s3:

&nbsp;     dhcp4: true

&nbsp;   enp0s8:

&nbsp;     addresses:

&nbsp;       - 192.168.10.10/24

&nbsp;     gateway4: 192.168.10.1

&nbsp;     nameservers:

&nbsp;       addresses: \[8.8.8.8]

```



---



\## 🖥️ VM2 (Server 2) – My Settings



For VM2, I used:



```

IP: 192.168.10.20

Gateway: 192.168.10.1

DNS: 8.8.8.8

```



Netplan config:



```yaml

network:

&nbsp; version: 2

&nbsp; ethernets:

&nbsp;   enp0s3:

&nbsp;     dhcp4: true

&nbsp;   enp0s8:

&nbsp;     addresses:

&nbsp;       - 192.168.10.20/24

&nbsp;     gateway4: 192.168.10.1

&nbsp;     nameservers:

&nbsp;       addresses: \[8.8.8.8]

```



---



\## 3️⃣ Applying My Network Configuration



I applied the changes using:



```bash

sudo netplan apply

```



Then verified it with:



```bash

ip a

```



---



\## 4️⃣ Testing Connection Between My VMs



From \*\*VM1\*\*, I tested:



```bash

ping 192.168.10.20

```



From \*\*VM2\*\*, I tested:



```bash

ping 192.168.10.10

```



If both responded → internal network is working perfectly.



---



\## 5️⃣ How I Fixed Common Issues



\### ❌ If VMs couldn’t ping each other



I checked:



\* Adapter 2 is set to Internal Network

\* Both VMs use the same name: `intnet`

\* Firewall status:



```bash

sudo ufw status

```



---



\### ❌ If my static IP didn’t apply



I ran:



```bash

sudo netplan generate

sudo netplan apply

```



Also checked indentation in the YAML file (very important).



---



\### ❌ If internet didn’t work inside the VM



I made sure NAT was enabled and the primary adapter was:



```

enp0s3 → dhcp4: true

```



---



\## ✔ Summary (What I Completed)



In this section, I successfully configured:



\* NAT for internet

\* Internal network for VM communication

\* Static IP addresses

\* Connectivity testing

\* Troubleshooting and validation



This network setup makes my virtual lab behave like a simple \*\*data center network environment\*\*, which is exactly what I want to practice for AWS Data Center Operations.



---



\# ✔ Done!



