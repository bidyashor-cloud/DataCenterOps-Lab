# 📄 troubleshooting/vm-shutdown-recovery.md

# 🔄 Unexpected VM Shutdown & Recovery – Troubleshooting Practice

In this troubleshooting exercise, I simulated an **unexpected shutdown** of my Ubuntu Server VM and then practiced how to bring the machine back online, check logs, and verify system health.

Unexpected shutdowns can happen in real data centers because of:

* Power failures
* Hardware issues
* Kernel crashes
* Forced shutdowns
* Overheating or host instability

This was a good chance for me to understand how the OS behaves after a sudden shutdown.

---

## 1️⃣ Simulating an Unexpected Shutdown

I powered off the VM abruptly using VirtualBox:

* Right-clicked the VM
* Selected **Close**
* Chose **Power Off** (NOT “Shut down”)

This is similar to a server losing power.

---

## 2️⃣ Starting the VM Again

I started the VM normally from VirtualBox.

Sometimes after unexpected shutdowns, Linux may:

* Take slightly longer to boot
* Run a disk check (fsck)
* Show warnings in dmesg
* Rebuild the journal

After booting, I logged in and began checking the system state.

---

## 3️⃣ Checking System Logs for Shutdown Errors

The first thing I checked was the system log to confirm the unexpected shutdown:

```bash
sudo journalctl -b -1 -xe
```

This shows logs from the **previous boot**, where the crash happened.

I also checked the current boot messages:

```bash
dmesg | less
```

And then syslog:

```bash
tail -n 50 /var/log/syslog
```

In the logs, I found entries like:

* “Power failure detected”
* “Unexpected shutdown”
* “System rebooted without proper shutdown”
* “Filesystem not clean, running fsck”

These confirmed the VM had an abrupt shutdown.

---

## 4️⃣ Checking File System Health

Unexpected shutdowns can corrupt file systems, so I checked the disk with:

```bash
sudo df -h
```

Then checked the journal mount options:

```bash
mount | grep " / "
```

Everything looked normal, meaning the shutdown did not damage the filesystem.

---

## 5️⃣ Verifying Critical Services After Boot

After a crash, some services may fail to start.

I checked:

```bash
systemctl --failed
```

Then tested key services like SSH:

```bash
sudo systemctl status ssh
```

If any service was down, I restarted it:

```bash
sudo systemctl start <service-name>
```

And enabled automatic startup:

```bash
sudo systemctl enable <service-name>
```

---

## 6️⃣ Checking Server Performance After Recovery

I monitored the system for any abnormal behavior:

```bash
top
free -h
ss -tulnp
```

Everything was stable.

---

## ✔️ What I Learned from This Exercise

* How servers behave after sudden power loss
* How to check logs from the previous boot
* How to confirm filesystem health
* How to identify services that failed to start
* How to bring the system back to a clean and stable state

This is a very real-world troubleshooting skill for data center operations and Linux support roles.

---

# 🎉 Done!

---
