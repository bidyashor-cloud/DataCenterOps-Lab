# 📄 **README.md**

# 🏗️ My Virtual Lab (VirtualBox + Ubuntu Server)

This project is my personal virtual lab environment built using VirtualBox and Ubuntu Server.
I created it so I can practice real technical skills such as Linux administration, networking, log analysis, troubleshooting, and general server operations—all on my own laptop.

The setup contains two Ubuntu Server VMs connected through an internal network, which lets me simulate multi-server workflows and issues in a safe environment.

---

## 🔧 **Technologies Used**

* **VirtualBox** – virtual machine platform
* **Ubuntu Server 22.04 LTS**
* **Linux command line & Bash**
* **NAT + Internal Network configuration**
* **Netplan** for static IP assignment
* **System logs:** `dmesg`, `syslog`, `journalctl`
* **Troubleshooting tools:** ping, ss, free, top, df, traceroute

---

## 📡 **Lab Architecture**

```
    +----------------------+
    |     VM1 – Server 1   |
    |     192.168.10.10    |
    |   Internal Network   |
    +----------+-----------+
               |
               |  intnet (Internal Network)
               |
    +----------+-----------+
    |     VM2 – Server 2   |
    |     192.168.10.20    |
    |   Internal Network   |
    +----------------------+
```

Both machines also use **NAT** for internet access.

This design gives me:

* Internet access for updates
* Private communication between the VMs
* A stable multi-VM setup for learning and testing

---

## 🎯 **What I’m Learning Through This Lab**

* How virtual machines are created and configured
* How internal networks work in virtual environments
* How to assign static IPs using Netplan
* How servers communicate and route traffic
* How to read and understand Linux system logs
* How to identify and fix system issues
* How real troubleshooting looks inside a Linux server

---

## 🚀 **Step-by-Step Documentation (stored in `/setup`)**

### **1️⃣ Installing VirtualBox**

`setup/virtualbox-installation.md`
How I installed VirtualBox and prepared the Ubuntu ISO.

### **2️⃣ Creating My Virtual Machines**

`setup/vm-creation.md`
How I created two Ubuntu Server VMs (VM1 and VM2).

### **3️⃣ Network Configuration**

`setup/network-configuration.md`
How I configured NAT + Internal Network and assigned static IPs.

---

## 🛠️ **Troubleshooting Scenarios (in progress)**

I’m documenting real issues I intentionally reproduce, such as:

* Network failures
* SSH problems
* Disk space issues
* Misconfigured services
* Boot-level warnings
* Package failures

All troubleshooting is stored in:
`/troubleshooting/`

---

## 📝 **System Logs**

I exported actual logs from inside the VMs so I can study them later:

* `logs/syslog.txt`
* `logs/dmesg.txt`

These help me understand how the system behaves during boot, network setup, and errors.

---

## 📸 **Screenshots**

I plan to store screenshots of:

* VM settings
* Network configuration
* Ping tests
* Errors
* Fixes

They will go inside the `/screenshots/` folder.

---

## ✔️ **Current Status**

I am actively updating this project as I learn more.
So far, I have completed:

* Creating two virtual machines
* Installing Ubuntu Server on both
* Configuring NAT + Internal networking
* Assigning static IP addresses
* Exporting log files
* Testing connectivity between the servers

This lab is helping me improve my understanding of Linux, networking, and troubleshooting.

---

## 🎓 **Why I Built This Lab**

I created this environment so I can gain practical, hands-on experience that aligns with real technical job roles such as:

* Server Operations
* Linux Support
* Cloud / Infrastructure Technician
* IT Support Engineer

It allows me to practice installation, configuration, monitoring, and diagnosing problems in a real-world way—without needing physical hardware.

---

## 📌 **Upcoming Additions**

* More detailed troubleshooting cases
* Simple monitoring setup
* Load testing between VMs
* Automation using shell scripts
* A small logging or metrics dashboard

---
