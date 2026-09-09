# Linux System Administration & Process Management — Day 03

## Overview
This repository documents my progress in learning DevOps fundamentals. On **Day 03**, I focused on environment management, system inspection, package installation, process control, and background job handling.

---

## 🛠️ Key Commands & References

| Command | Category | Description |
| :--- | :--- | :--- |
| `man <command>` | System Info | Displays the manual page for a specific command |
| `which <command>` | System Info | Shows the full path of the shell command executable |
| `uptime` | System Info | Displays how long the system has been running and load averages |
| `printenv` | Environment | Lists all currently set environment variables |
| `export JAVA_HOME="/usr/lib/jvm/java-11"` | Environment | Sets an environment variable for the current session |
| `export PATH=$PATH:/new/path` | Environment | Appends a new directory path to the system PATH variable |
| `source ~/.bashrc` | Environment | Reloads shell configuration without restarting the session |
| `apt search <pkg>` | Package Manager | Searches for packages in Debian/Ubuntu repositories |
| `apt update && apt install <pkg>` | Package Manager | Updates package index and installs packages (Debian/Ubuntu) |
| `yum` / `dnf` | Package Manager | Package managers for RHEL/CentOS/Fedora systems |
| `rpm -qa \| grep <app>` | Package Manager | Queries installed RPM packages on RedHat-based systems |
| `dnf list installed` | Package Manager | Lists all packages installed via DNF |
| `systemctl start/stop <service>` | Systemd Service | Starts or stops a system service |
| `systemctl list-units --type=service --all` | Systemd Service | Lists all loaded services regardless of state |
| `ps -ef \| grep <process>` | Process Mgmt | Displays all running processes filtered by pattern |
| `pgrep <process>` | Process Mgmt | Finds Process IDs (PID) based on the process name |
| `kill -9 <PID>` | Process Mgmt | Forcefully terminates a running process by PID |
| `jobs` | Process Mgmt | Displays active background and suspended jobs |
| `bg` / `fg` | Process Mgmt | Resumes suspended jobs in background or foreground |
| `nohup <cmd> &` | Process Mgmt | Runs a command immune to hangups in the background |
| `top` | System Resources | Displays real-time interactive process and system memory usage |
| `free -th` | System Resources | Shows total, used, and free memory in human-readable format |
| `du -sh <path>` | Storage | Estimates file space usage for a directory |
| `df -h` | Storage | Displays disk space usage of file systems in human-readable format |
| `hostname` | System Info | Displays or sets the system's network hostname |
| `lscpu` | System Info | Displays CPU architecture and processor details |
| `arch` / `uname -a` | System Info | Prints system architecture and detailed kernel information |
| `lsblk` | System Info | Lists information about all available block storage devices |

---

## 💻 Practice Execution Log

```bash
# Check system performance and memory
$ uptime
$free -th$ df -h

# Environment setup
$ export JAVA_HOME="/usr/lib/jvm/java-11-openjdk"
$echo$JAVA_HOME >> ~/.bashrc
$ source ~/.bashrc

# Process control
$ ps -ef | grep nginx
$kill -9 12345$ nohup python3 script.py &
