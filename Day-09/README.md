# Linux Aliases, File Systems & Inodes — Day 09

## Overview
This repository documents my progress in learning DevOps fundamentals. On **Day 09**, I focused on configuring custom command **Aliases**, understanding **Inodes** in Linux storage, and exploring the **Linux File System Hierarchy Standard (FHS)**.

---

## 🛠️ Section 1: Inodes in Linux

An **Inode** (index node) is a data structure in Linux that stores metadata about a file or directory on the file system[span_2](start_span)[span_2](end_span).

* **Metadata Stored:** File size, ownership, permissions, timestamps, and data block pointers[span_3](start_span)[span_3](end_span).
* **Functionality:** The file system uses the inode number to locate the inode, which contains pointers directing to the actual data blocks stored on disk[span_4](start_span)[span_4](end_span).

---

## 🛠️ Section 2: Linux Directory Hierarchy (FHS)

The Linux file system starts at the **Root Directory (`/`)**, denoted by a single slash, from which all other files and directories branch out[span_5](start_span)[span_5](end_span).

| Directory | Full Name / Concept | Purpose & Description |
| :--- | :--- | :--- |
| **`/`** | Root Directory | The top-level root directory of the entire file system structure[span_6](start_span)[span_6](end_span). |
| **`/bin`** | User Binaries | Contains essential user binaries (executables) such as common commands like `ls`, `cp`, etc.[span_7](start_span)[span_7](end_span)[span_8](start_span)[span_8](end_span) |
| **`/etc`** | Editable Text Configuration | Holds system configuration files (e.g., user profiles, network settings, services, system apps)[span_9](start_span)[span_9](end_span)[span_10](start_span)[span_10](end_span). |
| **`/home`** | Home Directories | Contains personal home directories for regular system users[span_11](start_span)[span_11](end_span)[span_12](start_span)[span_12](end_span). |
| **`/root`** | Root Home Directory | The home directory specifically reserved for the root user (administrator)[span_13](start_span)[span_13](end_span)[span_14](start_span)[span_14](end_span). |
| **`/var`** | Variable Data | Stores dynamic variable data such as system log files and databases[span_15](start_span)[span_15](end_span). |
| **`/tmp`** | Temporary Files | Stores temporary files created by system processes and users during session execution[span_16](start_span)[span_16](end_span). |

---

## 💻 Practice Execution Log

```bash
# Check inode usage on the file system
$ df -i

# Inspect the inode number of a specific file
$ ls -i file1.txt

# Inspect system log directory structure
$ ls -l /var/log
