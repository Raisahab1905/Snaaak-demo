
# 🏷️ **Standard Operating Procedure (SOP) for Common Ubuntu Commands**

This document provides a comprehensive guide for frequently used Ubuntu commands, organized for easy reference.

---

| **Created**  | **Version**  | **Author**   | **Comment**  | **Reviewer**  |
| :------- | :------- | :------- | :------- | :------- |
| 14-04-2025| V1 | **Durgesh Sharma** |          |   **Pritam**      |

## **Table of Contents**
1. [Introduction](#introduction)
2. [Scope](#scope)
3. [Prerequisites](#prerequisites)
4. [Commands](#commands)
    - [Basic System Commands](#1-basic-system-commands)
    - [File Commands](#2-file-commands)
    - [Directory Commands](#3-directory-commands)
    - [File Permission Commands](#4-file-permission-commands)
    - [Process Management Commands](#5-process-management-commands)
    - [Network Commands](#6-network-commands)
    - [Disk Management](#7-disk-management)
5. [Notes](#notes)
6. [Reference Table](#reference-table)
7. [Contact](#contact)

---

##  ✨**Introduction** 
This document serves as a comprehensive guide to essential **Ubuntu commands**, designed to help users efficiently manage their system. Whether you're a beginner or an experienced user, these commands cover key tasks such as system maintenance, file management, and troubleshooting. By familiarizing yourself with these Ubuntu commands, you’ll be able to streamline your workflow, solve problems faster, and gain better control over your Ubuntu environment. Mastering these basic Ubuntu commands will ultimately boost your productivity and enhance your ability to manage your system effectively.

---

## 🎯**Scope** 
Applicable for users managing Ubuntu systems for personal, development, or server-related tasks. 
It includes commands for file operations, directory management, user permissions, process monitoring, and more.

---

## ✅**Prerequisites** 
- Access to a terminal on an Ubuntu system.
- Appropriate permissions for commands requiring `sudo`.

---

## 🛠️**Commands** 

### **1. Basic System Commands**
1. **Check Ubuntu Version**
   ```bash
   lsb_release -a
   ```
   Displays details about the current Ubuntu version.

2. **View Kernel Version**
   ```bash
   uname -r
   ```
   Displays the Linux kernel version.

3. **Update and Upgrade Packages**
   ```bash
   sudo apt update && sudo apt upgrade
   ```
   Updates package lists and installs available updates.

4. **Reboot System**
   ```bash
   sudo reboot
   ```
    Safely restarts the system, ensuring all running processes are terminated properly.

---

### **2. File Commands**
1. **Create an Empty File**
   ```bash
   touch filename
   ```
   The `touch` command creates a new, empty file named filename or updates the timestamp if the file already exists.

2. **View File Content**
   ```bash
   cat filename
   ```
   The `cat` command displays the contents of a file, allows concatenation of multiple files, or can be used to create and append content to files.

3. **Delete a File**
   ```bash
   rm filename
   ```
   The `rm filename` command deletes the specified file (filename) permanently from the filesystem.

4. **Rename or Move a File**
   ```bash
   mv old_filename new_filename
   ```

5. **Copying to a Same Directory**
   ```bash
   cp file1.txt file2.txt
   ```
   The `cp file1.txt file2.txt` command copies the contents of file1.txt to a new file named file2.txt. If file2.txt doesn't exist, it will be created.

6. **Copying to a Different Directory:**
   ```bash
   cp file.txt Path_of_the_directory
   ```
   The `cp file.txt Path_of_the_directory` command copies the file file.txt into the specified directory `(Path_of_the_directory)`.

---

### **3. Directory Commands**
1. **Create a New Directory**
   ```bash
   mkdir directory_name
   ```
   The `mkdir directory_name` command creates a new, empty directory named `directory_name` in the current working directory.

2. **Remove an Empty Directory**
   ```bash
   rmdir directory_name
   ```
   The `rmdir directory_name` command removes an empty directory named `directory_name`. It only works if the directory is empty.

3. **Delete a Directory with Files**
   ```bash
   rm -r directory_name
   ```
   The `rm -r` directory_name command recursively removes a directory `(directory_name)` and all of its contents, including subdirectories and files.

4. **List Contents of a Directory**
   ```bash
   ls -la
   ```
   Displays files, directories, and permissions in detailed format.

---

### **4. File Permission Commands**
1. **View File Permissions**
   ```bash
   ls -l filename
   ```
   The `ls -l` filename command displays detailed information about the specified file (filename), including its permissions, owner, group, size, and the last modification date.

2. **Change File Permissions**
   ```bash
   chmod 755 filename
   ```
   The `chmod 755 filename` command sets the file permissions of filename to rwxr-xr-x, which means:

* The owner has read, write, and execute permissions.
* The group and others have read and execute permissions.

3. **Change Ownership of a File**
   ```bash
   sudo chown user:group filename
   ```
   The `sudo chown user:group filename` command changes the ownership of a specified file (filename), setting the user as user and the group as group.

4. **Add Write Permission for All Users**
   ```bash
   chmod a+w filename
   ```
   The `chmod a+w filename` command adds write permissions for all users (owner, group, and others) on the specified file `(filename)`.

---

### **5. Process Management Commands**
1. **List Running Processes**
   ```bash
   ps aux
   ```
   The `ps aux` command displays detailed information about all running processes on the system, including their user, CPU/memory usage, and other statistics.

2. **Kill a Process**
   ```bash
   kill PID
   ```
   Replaces `PID` with the Process ID.

3. **Force Kill a Process**
   ```bash
   kill -9 PID
   ```
   The `kill -9` command forcefully terminates a process by sending it the SIGKILL signal, ensuring it stops immediately.

4. **Monitor System Processes**
   ```bash
   top
   ```
   The `top` command provides a real-time, dynamic view of system processes, including CPU, memory usage, and running tasks.

5. **Search for a Specific Process**
   ```bash
   pgrep process_name
   ```
   The `pgrep process_name` command searches for processes by name and returns their process IDs (PIDs).

6. **Check Resource Usage by Process**
   ```bash
   htop
   ```
   The `htop` command is an interactive, user-friendly process viewer that displays system resource usage and allows you to manage processes in real time.

---

### **6. Network Commands**
1. **Ping a Server**
   ```bash
   ping example.com
   ```
   The `ping` command tests the network connectivity between your system and a specified host by sending ICMP echo requests and measuring response times.

2. **Check Open Ports**
   ```bash
   sudo netstat -tuln
   ```
   The `sudo netstat -tuln` command displays active TCP and UDP network connections, along with their listening ports, in a numeric format, requiring root privileges for complete information.

3. **Traceroute**
   ```bash
   traceroute example.com
   ```
   The `traceroute` command is used to trace the route that packets take from your computer to a specified destination, showing the sequence of routers (hops) the packets pass through along with the time taken for each hop.

---

### **7. Disk Management**
1. **Check Disk Usage**
   ```bash
   df -h
   ```
   The `df -h` command displays the disk space usage of all mounted filesystems in a human-readable format, showing sizes in KB, MB, or GB.

2. **View Free Memory**
   ```bash
   free -h
   ```
   The `free -h` command displays the system's memory usage, including total, used, free, and available memory, in a human-readable format (KB, MB, GB).

3. **List Partitions**
   ```bash
   lsblk
   ```
   The `lsblk` command lists all block devices (such as hard drives, partitions, and USB drives) on your system, showing their names, sizes, and mount points.

---

## 📝**Notes** 
- Always double-check commands involving `sudo` to avoid unintentional changes.
- Refer to the `man` command (e.g., `man ls`) for detailed usage instructions.
- For troubleshooting, consult the [Ubuntu Documentation](https://help.ubuntu.com/).

---

## 📚**Reference Table** 

| Other Commands                    | Link        |
| :--------                         | :------------------ |
| `Comprehensive Command List`      | [DigitalOcean Linux Commands](https://www.digitalocean.com/community/tutorials/linux-commands) |

---

## 📧**Contact** 
| **Name**           | **Email Address**                                 |
|----------------|-----------------------------------------------|
| Durgesh Sharma | durgesh.sharma.snaatak@mygurukulam.co         |
