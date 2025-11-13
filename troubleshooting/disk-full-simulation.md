\# 📄 \*\*troubleshooting/disk-full-simulation.md\*\*



\# 🧪 Disk Full Simulation – Troubleshooting Practice



In this troubleshooting exercise, I simulated a \*\*disk full issue\*\* inside my Ubuntu Server VM to understand how storage problems affect services and system stability.  

This is a very common issue in real data centers, so I wanted to learn how to detect it and fix it.



---



\## 1️⃣ Checking My Current Disk Space



Before starting, I checked how much free space I had:



```bash

df -h

```



This showed me the size of my root filesystem and how much space was already in use.



---



\## 2️⃣ Simulating the Disk Full Problem



To fill up the disk, I created a very large dummy file using the `fallocate` command:



```bash

sudo fallocate -l 5G /bigfile

```



(You can also use a bigger size depending on your VM.)



After creating the file, I ran:



```bash

df -h

```



Now the disk usage jumped up, and the free space dropped almost to zero.



---



\## 3️⃣ Observing System Behavior



Once the disk got full, I noticed:



\* Some commands started responding slowly

\* New files could not be created

\* Services began showing errors

\* `/var/log/syslog` showed warnings about “No space left on device”



I checked the logs using:



```bash

tail -n 20 /var/log/syslog

```



I also checked kernel messages:



```bash

dmesg | tail

```



Both logs clearly showed disk space errors.



---



\## 4️⃣ Fixing the Disk Full Issue



To fix the issue, I deleted the large file I created:



```bash

sudo rm /bigfile

```



Then I verified the free space again:



```bash

df -h

```



Now the disk usage went back to normal.



---



\## 5️⃣ Extra: Cleaning Unused Packages (Optional)



I also cleaned up unnecessary packages:



```bash

sudo apt autoremove -y

sudo apt clean

```



This freed a little extra space.



---



\## 6️⃣ What I Learned from This Exercise



\* Full disks cause services to fail silently

\* System logs are the best way to detect this problem

\* Even small logs cannot be written when disk is full

\* A single big file can completely break the server

\* Removing temporary files quickly fixes the issue



This is a very useful troubleshooting skill for Data Center Operations and Linux support roles.



```



---



\# 🎉 Done!



