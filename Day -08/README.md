# Linux Archiving, Links & Environment Variables — Day 08

## Overview
This repository documents my progress in learning DevOps fundamentals. On **Day 08**, I focused on Linux file compression techniques, understanding symbolic (soft) vs. hard links, and configuring shell environment variables for system-wide persistence.

---

## 🛠️ Section 1: File Archiving & Compression

File compression reduces total file size by encoding data efficiently, which optimizes storage space and speeds up file transfers over networks.

| Operation | Command | Description |
| :--- | :--- | :--- |
| **Create Tar Archive** | `tar -cvf archive_name.tar file1.txt file2.txt` | Bundles files into an uncompressed archive. |
| **Compress with Gzip** | `tar -czvf archive_name.tar.gz file1.txt file2.txt` | Bundles and compresses files using Gzip (`.tar.gz`). |
| **Decompress Gzip** | `tar -xzvf archive_name.tar.gz` | Extracts contents from a Gzip compressed archive. |
| **Decompress Bzip2** | `tar -xjvf archive_name.tar.bz2` | Extracts contents from a Bzip2 compressed archive (`.tar.bz2`). |
| **Compress with Zip** | `zip archive_name.zip file1.txt file2.txt` | Compresses multiple files into a standard `.zip` archive. |
| **Decompress Zip** | `unzip archive_name.zip` | Extracts files from a `.zip` archive. |

---

## 🛠️ Section 2: Linux Links (Soft Links vs. Hard Links)

A link creates a connection between a file name and the actual data stored on disk.

| Link Type | Creation Command | Behavior & Features |
| :--- | :--- | :--- |
| **Soft Link (Symbolic)** | `ln -s myfile myfile-link` | Acts as a shortcut pointing to the file path. If the original file is renamed or deleted, the soft link breaks. |
| **Hard Link** | `ln myfile myfile-hard-link` | Points directly to the file's data (inode). Renaming or deleting the original file does not affect the hard link. |

---

## 🛠️ Section 3: Environment Variables

Environment variables store dynamic information in memory about the shell session and working environment, accessible by programs and scripts.

| Action | Command / Method | Scope & Description |
| :--- | :--- | :--- |
| **View Environment Variables** | `printenv` or `env` | Lists all active environment variables in the current shell. |
| **Create Local Variable** | `MY_VAR="Hello"` | Creates a variable accessible only within the current shell process. |
| **Print Variable Value** | `echo $MY_VAR` | Displays the value assigned to the specified variable. |
| **System-wide Persistence** | Edit `/etc/profile` and add `export MYVAR=VALUE` | Sets an environment variable permanently for all users across system sessions. |
| **Reload Global Environment** | `source /etc/profile` | Applies changes made to `/etc/profile` immediately without rebooting. |

---

## 💻 Practice Execution Log

```bash
# File Archiving & Decompression
$ tar -czvf logs.tar.gz file1.txt file2.txt
$ tar -xzvf logs.tar.gz
$ zip project.zip file1.txt file2.txt
$ unzip project.zip

# Link Management
$ln -s /var/log/syslog soft_log_link$ ln /var/log/syslog hard_log_link

# Managing Environment Variables
$printenv \vert{} grep USER$ MY_VAR="Hello"
$ echo $MY_VAR$ sudo nano /etc/profile
# Added line: export MYVAR="VALUE"
$ source /etc/profile
