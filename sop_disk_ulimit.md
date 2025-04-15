# ✅ SOP: Disk Usage, Mount Points & Ulimit Configuration on Ubuntu

---

## 📂 Section 1: Disk Usage & Mount Point Inspection

### 🔹 1.1 Check Disk Usage

```bash
df -h

```

- Shows disk usage of all mounted filesystems in human-readable format.

### 🔹 1.2 List Mounted File Systems and Types

```bash
mount | column -t

```

or

```bash

findmnt

```

- Displays mount hierarchy with filesystem types and mount targets.

### 🔹 1.3 Check Specific Mount Point Usage (e.g., `/var`)

```bash
du -sh /var/*

```

- Identifies disk usage per subdirectory.

### 🔹 1.4 View Disk Partitions

```bash
lsblk

```

- Lists block devices and mount points.

---

## 📦 Section 2: Ulimit Configuration for Users & Services

### 🔹 2.1 View Current Ulimit (Session-Based)

```bash
ulimit -a

```

- Displays all current user limits.

### 🔹 2.2 Temporarily Set Ulimit for Current Session

```bash
ulimit -n 65535       # Open file descriptors
ulimit -u 4096        # Max user processes

```

---

## 🔐 Section 3: Persistent Ulimit Settings for Users

### 🔹 3.1 Modify Limits for a Specific User

Edit the limits file:

```bash
sudo nano /etc/security/limits.conf

```

Add or update lines:

```
<username>   soft   nofile   65535
<username>   hard   nofile   65535
<username>   soft   nproc    4096
<username>   hard   nproc    4096

```

> 🔁 Use * for all users instead of a specific username.
> 

---

## ⚙️ Section 4: PAM & System-Wide Enforcement

### 🔹 4.1 Enable PAM Limits

Ensure PAM enforces limits:

```bash
sudo nano /etc/pam.d/common-session

```

Add this line if not already present:

```
swift
CopyEdit
session required pam_limits.so

```

---

## 🧩 Section 5: Ulimit Settings for Systemd Services

### 🔹 5.1 Configure Systemd Service Limits

```bash
bash
CopyEdit
sudo systemctl edit <your-service>

```

Add override settings:

```
ini
CopyEdit
[Service]
LimitNOFILE=65535
LimitNPROC=4096

```

Then reload and restart:

```bash
bash
CopyEdit
sudo systemctl daemon-reexec
sudo systemctl daemon-reload
sudo systemctl restart <your-service>

```

---

## 🛠️ Section 6: Validation & Troubleshooting

### 🔹 6.1 Confirm Limits for Running Processes

```bash
bash
CopyEdit
cat /proc/<pid>/limits

```

### 🔹 6.2 Confirm User Limits (Login Test)

```bash
bash
CopyEdit
ulimit -n
ulimit -u

```

Run this after logging in via SSH to confirm the changes applied.

---

## 📘 Summary Table

| Task | Command |
| --- | --- |
| Disk Usage | `df -h`, `du -sh /path/*` |
| Mount Points | `mount`, `findmnt`, `lsblk` |
| View Ulimit | `ulimit -a` |
| Set Ulimit Temporarily | `ulimit -n 65535` |
| Persistent User Limit | `/etc/security/limits.conf` |
| PAM Configuration | `pam_limits.so` in `/etc/pam.d/common-session` |
| Systemd Process Ulimit | `systemctl edit <service>` + `LimitNOFILE` |
| Check Running Process Limits | `cat /proc/<pid>/limits` |
