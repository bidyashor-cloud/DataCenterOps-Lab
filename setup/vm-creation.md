# 🖥️ Creating My Virtual Machines for My Virtual Lab

In this part of my project, I created two Ubuntu Server virtual machines in VirtualBox. These VMs act as simple lab servers where I can practice Linux commands, installations, and troubleshooting.

---

## 1️⃣ Creating the First Virtual Machine (VM1)

I opened VirtualBox and clicked **New** to create the first VM.

### 🔧 Basic Settings

```
Name: VM1-Server
Type: Linux
Version: Ubuntu (64-bit)
```

### 🧠 Memory (RAM)

I assigned:

```
2048 MB (2 GB)
```

This is enough for Ubuntu Server since it doesn’t use a desktop environment.

### ⚙️ Processor

```
1 or 2 CPUs (based on my laptop)
```

### 💽 Hard Disk

I created a new virtual disk:

```
Create a virtual hard disk now
VDI (VirtualBox Disk Image)
Dynamically allocated
Size: 20 GB
```

Then clicked **Create**.

---

## 2️⃣ Attaching the Ubuntu Server ISO

Once VM1 was created, I attached the Ubuntu Server ISO for installation.

Steps:

1. Open **Settings**
2. Go to **Storage**
3. Select the empty disk under *Controller: IDE*
4. Click the **CD icon**
5. Choose **Select a disk file**
6. Pick my Ubuntu Server ISO

This prepared the VM to boot the installer.

---

## 3️⃣ Installing Ubuntu Server on VM1

I started VM1 and followed the Ubuntu Server installation steps:

* Selected **English**
* Chose **Install Ubuntu Server**
* Kept default keyboard layout
* Skipped network configuration (I set it later)
* Accepted default disk partitioning
* Created my user:

```
Username: admin
Password: (my password)
```

* Skipped optional packages
* Waited for installation to complete
* Rebooted the system

After rebooting, I logged in normally.

---

## 4️⃣ Creating VM2 (Server 2)

To save time, I cloned VM1 instead of installing Ubuntu again.

Steps:

1. Right-click **VM1**
2. Click **Clone**
3. Name it:

```
VM2-Server
```

4. Choose **Full Clone**
5. Click **Clone**

This created VM2 with the same OS, storage, and settings.

---

## 5️⃣ Verifying Both VMs

I started both VMs and ran:

```bash
uname -a
lsb_release -a
ip a
```

I checked that:

* The OS installed correctly
* The network interfaces appeared normally
* Both VMs booted without issues
* I could log in on both machines

---

## ✔️ What I Completed in This Step

* Created two Ubuntu Server VMs
* Installed Ubuntu Server inside both VMs
* Saved time using cloning for VM2
* Verified both machines are running properly
* Prepared everything for the network setup

The next step of my project is configuring networking and static IPs. I documented this in **network-configuration.md**.

---
