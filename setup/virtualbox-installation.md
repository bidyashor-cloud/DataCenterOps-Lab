# 🖥️ Installing VirtualBox for My Virtual Lab

In this part of my project, I installed Oracle VirtualBox on my Windows system so I can create and run multiple Ubuntu Server virtual machines. These VMs will act as a simple internal lab environment where I can practice Linux, networking, and server operations.

---

## 1️⃣ Downloading VirtualBox

I started by downloading the latest version of VirtualBox from the official website:

[https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)

Since I’m using Windows, I clicked on:

* **Windows hosts**

This downloaded the VirtualBox installer (`.exe` file) to my system.

---

## 2️⃣ Installing VirtualBox

After the download finished, I installed VirtualBox by following these steps:

1. Double-clicked the installer file
2. Clicked **Next** through the setup screens
3. Kept the default installation components
4. Clicked **Yes** when Windows asked about creating network interfaces
5. Pressed **Install**
6. Waited for the installation to complete
7. Clicked **Finish** to launch VirtualBox

At this point, VirtualBox was successfully installed on my machine.

---

## 3️⃣ Verifying the Installation

To confirm that everything installed correctly, I opened VirtualBox from the Start Menu.

I checked the following:

* The VirtualBox main window opened without errors
* I could see the **New** button to create virtual machines
* The **Preferences** and **Network** options were available

This confirmed that VirtualBox was installed and working correctly.

---

## 4️⃣ Downloading the Ubuntu Server ISO

To prepare for creating my virtual machines, I downloaded the **Ubuntu Server 22.04 LTS ISO** from the official Ubuntu website:

[https://ubuntu.com/download/server](https://ubuntu.com/download/server)

I chose the server edition because:

* It runs in the terminal (like real Linux servers)
* It is lightweight
* It’s great for practicing Linux commands and troubleshooting

I saved the ISO file to my Downloads folder.

---

## 5️⃣ What I Will Do Next

Now that I have VirtualBox installed and the Ubuntu Server ISO ready, the next steps will be:

* Creating two Ubuntu Server VMs
* Configuring CPU, RAM, and storage for each VM
* Installing Ubuntu Server inside both VMs

I will document these steps in **vm-creation.md** as the next part of my project.

---

# ✔ Done!
