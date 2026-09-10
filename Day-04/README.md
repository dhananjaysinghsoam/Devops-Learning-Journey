---

### Day 04: Networking, Users, Archiving & Automation

Day 04 mein Network Troubleshooting, Archiving/Compression, Text Processing, File Permissions aur User Management commands include ki gayi hain.

**Day-04/README.md**

```markdown
# Linux Networking, Security & Text Processing — Day 04

## Overview
This repository documents my progress in learning DevOps fundamentals. On **Day 04**, I focused on user and permission management, network utilities, file archiving, and text manipulation tools.

---

## 🛠️ Key Commands & References

| Command | Category | Description |
| :--- | :--- | :--- |
| `chmod a+rwx <file>` | Permissions | Modifies file read, write, and execute permissions for all |
| `chown root <file>` | Permissions | Changes the user ownership of a file/directory to root |
| `chgrp <group> <file>` | Permissions | Changes the group ownership of a file/directory |
| `su <user>` | User Mgmt | Switches to another user account |
| `sudo <command>` | User Mgmt | Executes a command with elevated superuser privileges |
| `useradd <username>` | User Mgmt | Creates a new user account |
| `passwd <username>` | User Mgmt | Changes or sets a user password |
| `groupadd <group>` | User Mgmt | Creates a new user group |
| `id <username>` | User Mgmt | Prints user and group IDs (UID/GID) for a user |
| `userdel <username>` | User Mgmt | Deletes a user account |
| `groupdel <group>` | User Mgmt | Deletes a user group |
| `ifconfig` / `ip a` | Networking | Displays network interface configuration |
| `ping <host>` | Networking | Tests network connectivity to a remote server |
| `telnet <ip> <port>` | Networking | Tests TCP port connectivity to a specific endpoint |
| `netstat -tulnp \| grep <port>`| Networking | Displays active network connections and listening ports |
| `traceroute <host>` | Networking | Displays the network route/hops taken to reach a host |
| `ssh user@hostname` | Remote Access | Connects securely to a remote server via SSH |
| `scp <file> user@host:/tmp/` | Remote Access | Copies files securely over SSH to a remote directory |
| `wget <URL>` | Networking | Downloads files from the web over HTTP/HTTPS/FTP |
| `curl <URL>` | Networking | Transfers data from or to a server using supported protocols |
| `tar -czf archive.tar.gz <dir>`| Archiving | Creates a compressed gzip archive from a directory |
| `tar -xzf archive.tar.gz` | Archiving | Extracts files from a compressed gzip archive |
| `gzip` / `gunzip <file>` | Archiving | Compresses or decompresses individual files |
| `zip file.zip f1 f2` | Archiving | Compresses multiple files into a zip archive |
| `awk -F':' '{print $1}'` | Text Processing | Advanced pattern scanning and processing language |
| `cut -c1-2 <file>` | Text Processing | Cuts out specified character columns from each line |
| `sed -n '1,5p' <file>` | Text Processing | Stream editor for filtering and transforming text |
| `tr 'a-z' 'A-Z'` | Text Processing | Translates or deletes characters from standard input |
| `truncate -s 100M <file>` | File Mgmt | Shrinks or extends the size of a file to 100MB |
| `at <time>` | Job Scheduling | Schedules a one-time task execution at a specified time |

---

## 💻 Practice Execution Log

```bash
# User and Permission Management
$ sudo useradd devops_user
$sudo passwd devops_user$ chmod 755 script.sh
$ chown devops_user:devops_user script.sh

# Networking & Transfer
$ ping -c 4 google.com
$netstat -tulnp \vert{} grep 80$ scp app.tar.gz deploy@192.168.1.50:/tmp/

# Archiving and Text Processing
$tar -czf backup.tar.gz /var/log$ cut -d':' -f1 /etc/passwd | head -5
