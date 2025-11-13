# 📄 troubleshooting/service-crash.md

# ⚠️ Service Crash Troubleshooting – SSH/Apache Failure

In this troubleshooting exercise, I practiced how to identify and fix a **service crash** inside my Ubuntu Server VM.
Service failures are very common in data centers, so I wanted to understand what actually happens behind the scenes and how to bring the service back online.

For this lab, I used **SSH** and **Apache** (you can choose either one).

---

## 1️⃣ Checking the Status of the Service

First, I checked if the service was running:

For SSH:

```bash
sudo systemctl status ssh
```

For Apache:

```bash
sudo systemctl status apache2
```

This gave me the current service state and logs.

---

## 2️⃣ Manually Simulating the Crash

To simulate a service failure, I manually stopped the service:

For SSH:

```bash
sudo systemctl stop ssh
```

For Apache:

```bash
sudo systemctl stop apache2
```

Now the service was “dead” or “inactive”.

---

## 3️⃣ Observing System Behavior When the Service Is Down

After stopping the service, I tested how the system behaved.

For SSH:

```bash
ssh localhost
```

This failed because SSH was not running.

For Apache:

```bash
curl localhost
```

This showed connection errors.

This helped me understand how a service crash affects connectivity in real scenarios.

---

## 4️⃣ Checking Logs to Identify the Issue

I checked the journal logs:

```bash
sudo journalctl -xe
```

And also checked syslog:

```bash
tail -n 20 /var/log/syslog
```

These logs showed that the service had been stopped and displayed some warnings related to the shutdown.

---

## 5️⃣ Restarting the Service (Recovery Step)

To recover the system, I restarted the service:

For SSH:

```bash
sudo systemctl start ssh
```

For Apache:

```bash
sudo systemctl start apache2
```

Then I verified the status:

```bash
sudo systemctl status ssh
# or
sudo systemctl status apache2
```

The service was now running again.

---

## 6️⃣ Enabling the Service to Start on Boot

I made sure the service automatically starts after a reboot:

For SSH:

```bash
sudo systemctl enable ssh
```

For Apache:

```bash
sudo systemctl enable apache2
```

This ensures reliability in case of unexpected shutdowns.

---

## ✔️ What I Learned

* How to check if a service is active or failed
* How to intentionally simulate a crash
* How to test connectivity when a service is down
* How to read logs using `journalctl` and `syslog`
* How to restart a failed service
* How to ensure the service auto-starts during boot

This exercise helped me understand how to handle service-related issues similar to real data center troubleshooting scenarios.

---

# 🎉 Done!

---
