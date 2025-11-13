# 🖥️ Installing VirtualBox for My DataCenterOps Lab

In this part of the project, I installed VirtualBox on my system so I can create and run multiple Linux virtual machines. These VMs will act like small servers inside a mini data center environment.

---

## 1️⃣ Downloading VirtualBox

I downloaded the latest version of VirtualBox from the official website:

[https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)

Since I’m using Windows, I clicked on:

* **Windows hosts**

This downloaded the VirtualBox installer (`.exe` file).

---

## 2️⃣ Installing VirtualBox

Once the installer downloaded, I followed these steps:

1. Double-clicked the installer
2. Clicked **Next** through the setup pages
3. Selected all default components
4. Clicked **Yes** when it warned about network interfaces
5. Clicked **Install**
6. Waited for installation to complete
7. Clicked **Finish**

After this, VirtualBox was successfully installed on my system.

---

## 3️⃣ Verifying My Installation

To make sure everything worked correctly, I opened VirtualBox from the Start Menu.

I checked that:

* The VirtualBox main window opened without errors
* The “New” button for creating VMs was available
* I could access the Network Settings and Preferences

This confirmed VirtualBox installed correctly.

---

## 4️⃣ Downloading the Ubuntu Server ISO

To prepare for creating VMs, I downloaded the **Ubuntu Server 22.04 LTS ISO** from:

[https://ubuntu.com/download/server](https://ubuntu.com/download/server)

I chose the **server version** because:

* It uses a terminal (like real servers in a data center)
* It is lightweight
* It’s perfect for practicing Linux troubleshooting

I saved the ISO file to my Downloads folder.

---

## 5️⃣ What’s Next?

Now that VirtualBox and the Ubuntu ISO are ready, the next steps will be:

* Creating two Linux VMs
* Configuring CPU, RAM, and storage
* Installing Ubuntu inside each VM

I will document these steps in the `vm-creation.md` file in the next part of my project.

---
