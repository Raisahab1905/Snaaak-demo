##🧾 SOP: Disk Usage, Mount Points, and Ulimit Settings

Category: Common Stack
Platform: Ubuntu (20.04/22.04 LTS)
Purpose: To standardize how to monitor and configure disk usage and ulimit settings across all Ubuntu-based systems in the environment.

1. 🔍 Checking Disk Usage
Step 1: View disk usage across all mounted filesystems
bash
Copy
Edit
df -h
-h: Human-readable format.

Key columns: Filesystem, Size, Used, Avail, Use%, Mounted on

Step 2: Identify disk usage per directory (optional for detailed inspection)
bash
Copy
Edit
du -sh /var/* /home/* /opt/* /tmp/*
-s: Summarize total.

-h: Human-readable.

Step 3: List inode usage
bash
Copy
Edit
df -i
Helps identify inode exhaustion, often caused by many small files.

2. 📌 Identifying Mount Points
Step 1: View current mounts
bash
Copy
Edit
mount | column -t
Or:

bash
Copy
Edit
cat /proc/mounts
Step 2: Check /etc/fstab for permanent mount configurations
bash
Copy
Edit
cat /etc/fstab
Ensure entries are correctly defined for persistent mounts.

3. 🔧 Configuring ulimit (User Limits)
Step 1: Check current ulimit settings for a user
bash
Copy
Edit
ulimit -a
Step 2: Check limits for a running process (by PID)
bash
Copy
Edit
cat /proc/<PID>/limits
4. ⚙️ Set Persistent ulimit Values
Step 1: Edit security limits
bash
Copy
Edit
sudo nano /etc/security/limits.conf
Example:

php-template
Copy
Edit
# <domain>   <type>  <item>          <value>
myuser       hard    nofile          65535
myuser       soft    nofile          65535
myuser       hard    nproc           32768
myuser       soft    nproc           32768
Step 2: Ensure PAM module includes limits
bash
Copy
Edit
sudo grep pam_limits.so /etc/pam.d/common-session
Ensure this line exists:

swift
Copy
Edit
session required pam_limits.so
Step 3: For system-wide defaults
Edit or create:

bash
Copy
Edit
/etc/security/limits.d/99-custom.conf
Step 4: Update systemd user limits (for services)
Edit service override or drop-in:

bash
Copy
Edit
sudo systemctl edit <service-name>
Add:

ini
Copy
Edit
[Service]
LimitNOFILE=65535
LimitNPROC=32768
Then reload:

bash
Copy
Edit
sudo systemctl daemon-reexec
sudo systemctl restart <service-name>
5. ✅ Verification After Configuration
Log in again as the target user and run:

bash
Copy
Edit
ulimit -n
ulimit -u
Or verify via:

bash
Copy
Edit
cat /proc/$(pgrep -u <user> bash | head -n1)/limits
6. 🛠 Troubleshooting

Issue	Possible Cause	Resolution
Limits not applied	PAM not configured	Add pam_limits.so line
Systemd services not picking limits	Missing systemd overrides	Add LimitNOFILE in service override
Disk usage 100%	Large log or core files	Use ncdu or du to analyze; clean unneeded files
Inodes exhausted	Too many small files	Find and clean with find /path -type f
