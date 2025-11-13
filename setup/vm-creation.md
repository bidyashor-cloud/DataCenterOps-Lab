\# 📄 \*\*setup/vm-creation.md\*\*



\# 🖥️ Creating My Virtual Machines for the DataCenterOps Lab



In this part of my DataCenterOps project, I created two Ubuntu Server virtual machines in VirtualBox.  

These VMs will act like simple servers so I can practice data center–style installation, configuration, and troubleshooting.



---



\## 1️⃣ Creating the First Virtual Machine (VM1)



I opened VirtualBox and clicked \*\*New\*\* to create the first VM.



\### \*\*Basic Settings\*\*

```



Name: VM1-Server

Type: Linux

Version: Ubuntu (64-bit)



```



\### \*\*Memory (RAM)\*\*

I set:

```



2048 MB (2 GB)



```

This is enough for Ubuntu Server without GUI.



\### \*\*Processor\*\*

```



1 or 2 CPUs (depending on my laptop)



```



\### \*\*Hard Disk\*\*

I selected:

```



Create a virtual hard disk now

VDI (VirtualBox Disk Image)

Dynamically allocated

Size: 20 GB



```



Then clicked \*\*Create\*\*.



---



\## 2️⃣ Attaching the Ubuntu Server ISO



After creating VM1, I attached the Ubuntu Server ISO so I can install the OS.



Steps:

1\. Click \*\*Settings\*\*

2\. Go to \*\*Storage\*\*

3\. Click the empty disk under “Controller: IDE”

4\. Click the small \*\*CD icon\*\*

5\. Select \*\*Choose a disk file\*\*

6\. Choose my Ubuntu Server ISO file



This prepares the VM to boot from the installer.



---



\## 3️⃣ Installing Ubuntu Server on VM1



I started VM1 and followed the installer steps:



\- Chose \*\*English\*\*

\- Selected \*\*Install Ubuntu Server\*\*

\- Kept default keyboard layout

\- Skipped network configuration (I set it later)

\- Used default disk partitioning

\- Created my user:

```



Username: admin

Password: (my own password)



```

\- Skipped optional packages

\- Let the installation finish

\- Rebooted the VM



Once rebooted, I logged in successfully.



---



\## 4️⃣ Creating VM2 (Server 2)



Instead of repeating all the steps again, I cloned VM1 to save time.



Steps:

1\. Right-click \*\*VM1\*\*

2\. Select \*\*Clone\*\*

3\. Name it:

```



VM2-Server



````

4\. Choose \*\*Full Clone\*\*

5\. Click \*\*Clone\*\*



This created VM2 with the same resources, disk size, and OS.



---



\## 5️⃣ Verifying Both VMs



I started \*\*VM1\*\* and \*\*VM2\*\* one by one and ran:



```bash

uname -a

lsb\_release -a

ip a

````



I checked:



\* The OS installed correctly

\* Network interfaces are available

\* Both VMs boot without errors

\* Both accept login normally



---



\## ✔️ What I Completed in This Step



\* Installed VirtualBox VMs

\* Installed Ubuntu Server inside both VMs

\* Prepared both machines for network setup

\* Ensured both are working correctly



The next step is to configure networking and static IPs.

I documented this in my \*\*network-configuration.md\*\* file.



```



