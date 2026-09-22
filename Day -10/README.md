# Linux File Types & Device Files — Day 10

## Overview
This repository documents my progress in learning DevOps fundamentals. On **Day 10**, I focused on understanding the different **File Types** in Linux and learning how special files—such as Sockets, Named Pipes (FIFO), Block Devices, and Character Devices—operate within the file system hierarchy.

---

## 🛠️ Section 1: Linux File Types Overview

In Linux, "everything is a file." Different file types are represented by specific symbols in detailed directory listings (e.g., `ls -l`).

| File Symbol | File Type | Description |
| :---: | :--- | :--- |
| **`-`** | Regular File | Standard data file containing text, binaries, or image data. |
| **`d`** | Directory | Directory containing pointers to files and other directories. |
| **`l`** | Symbolic Link | Soft link pointing to another file or path. |
| **`c`** | Character Device | Device file handling unbuffered character-by-character I/O. |
| **`s`** | Socket File | Inter-process communication endpoint for stream-based data. |
| **`p`** | FIFO / Named Pipe | Inter-process communication pipe using First-In, First-Out queueing. |
| **`b`** | Block Device | Storage device file reading/writing data in block structures. |

---

## 🛠️ Section 2: Special File Types Explained

### 1. Socket Files (`s`)
* **Purpose:** Special files that enable local inter-process communication between running applications.
* **Location:** Typically located under `/run/` directory.
* **Example:** `/run/chrony/chronyd.sock`

### 2. Named Pipes / FIFO (`p`)
* **Purpose:** Sends output data sequentially from one process to another so the receiving process reads data in a First-In, First-Out (FIFO) manner.
* **Creation Command:** Created using the `mkfifo` command.

### 3. Block Device Files (`b`)
* **Purpose:** Represent physical or virtual hardware storage devices that transfer data in blocks (e.g., hard drives, SSDs, partitions).
* **Location:** Found under the `/dev/` directory.
* **Example:** `/dev/sda1`

### 4. Character Device Files (`c`)
* **Purpose:** Represent input/output hardware devices that read or write data character-by-character (unbuffered stream).
* **Creation Command:** Can be created using the `mknod` command.
* **Location:** Located within the `/dev/` directory.
* **Example:** `/dev/input/mouse2`

---

## 💻 Practice Execution Log

```bash
# Identifying file types using detailed directory listing
$ ls -l /dev /run

# Creating a Named Pipe (FIFO)
$mkfifo my_pipe$ ls -l my_pipe

# Viewing system block devices
$ ls -l /dev/sda*

# Viewing system character devices
$ ls -l /dev/input/
