# 📄 README.md

# 🏗️ My DataCenterOps Virtual Lab (VirtualBox + Ubuntu Server)

This project is my own virtual Data Center Operations lab that I built using VirtualBox and Ubuntu Server.

I created this lab to practice real data center skills like installing servers, configuring networks, analyzing logs, simulating failures, and troubleshooting issues — all using just my personal laptop.

The idea is to recreate a small two-server environment similar to what you would see inside an actual data center, but in a fully virtual setup.

---

## 🔧 Technologies I Used

* **VirtualBox** (for creating virtual servers)
* **Ubuntu Server 22.04 LTS** (Linux OS for both VMs)
* **Linux CLI, Bash**
* **NAT + Internal Network setup**
* **Netplan for static IP configuration**
* **System logs: syslog, dmesg, journalctl**
* **Troubleshooting tools:** ping, top, free, df, ss, traceroute

---

## 📡 My Lab Architecture

This is the lab I built:

```
    +----------------------+
    |   VM1 – Server 1     |
    |  192.168.10.10       |
    |  Internal Network    |
    +----------+-----------+
               |
               |  Internal Network (intnet)
               |
    +----------+-----------+
    |   VM2 – Server 2     |
    |  192.168.10.20       |
    |  Internal Network    |
    +----------------------+
```

Both servers also use NAT for internet access.

This setup gives me:

* Internet access for updates
* Private communication between both servers
* A small multi-server environment for troubleshooting

---

## 🎯 What I’m Trying to Learn in This Lab

* How virtual servers are created and configured
* How data centers use NAT + private internal networks
* How to assign static IPs and manage network settings
* How servers communicate
* How to read and understand Linux system logs
* How to detect and fix errors in a real troubleshooting workflow
* How failures actually look inside a server environment

---

## 🚀 Step-by-Step Setup (Documented in the `setup/` folder)

I documented everything I did so far:

### 1️⃣ Installing VirtualBox

`setup/virtualbox-installation.md`
How I downloaded and installed VirtualBox and the Ubuntu Server ISO.

### 2️⃣ Creating My Virtual Machines

`setup/vm-creation.md`
How I created two Ubuntu Server VMs for my virtual data center.

### 3️⃣ Configuring Networking

`setup/network-configuration.md`
How I configured NAT + Internal Network and set static IPs.

---

## 🔍 Troubleshooting Scenarios (in progress)

I am documenting different issues I can reproduce inside the servers, such as:

* Disk full errors
* Service crashes
* Unexpected shutdowns
* Network misconfigurations

These are stored in the `troubleshooting/` folder.

---

## 📝 System Logs

I saved actual logs from inside the VMs:

* `logs/syslog.txt`
* `logs/dmesg.txt`

These logs help me understand how servers behave during failures.

---

## 📸 Screenshots

I will also attach screenshots of:

* VM creation
* Network settings
* Ping tests
* Errors
* Fixes

Screenshots will be stored in the `screenshots/` folder.

---

## ✔️ Current Status

I am actively updating this project as I complete each part of the lab.
This is an ongoing learning project to help me improve in:

* Data Center Operations
* Linux administration
* Troubleshooting
* Infrastructure basics

---

## 🎓 Why I Built This Lab

My goal is to gain hands-on technical experience that aligns with real data center work such as:

* Server setup
* Internal networking
* Monitoring
* Issue diagnosis
* Reliability and support

This project helps me practice the skills needed for roles like:

* Data Center Operations Trainee
* Cloud Support
* Infrastructure Technician
* Linux Server Tech

---

## 📌 Next Updates (Coming Soon)

* More troubleshooting scenarios
* Monitoring setup
* Load testing between the VMs
* Adding automation using simple Bash scripts

---

# 🎉 DONE

---
