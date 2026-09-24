# Linux Boot Process & Architecture — Day 11

## Overview
This repository documents my progress in learning DevOps fundamentals. On **Day 11**, I covered the **Linux Boot Process**, analyzing the sequence of events from power-on to user-space execution across six key stages: **BIOS**, **MBR**, **GRUB**, **Kernel**, **Initrd / Initramfs**, and **Systemd**[span_0](start_span)[span_0](end_span)[span_1](start_span)[span_1](end_span).
---
## 🛠️ Section 1: The 6 Stages of the Linux Boot Process
| Stage | Component | Role & Functionality |
| :---: | :--- | :--- |
| **1** | **BIOS** | Performs Hardware Initialization & POST (Power-On Self-Test); searches and loads the bootloader from the designated bootable device[span_2](start_span)[span_2](end_span). |
| **2** | **MBR** | Located in the very first sector of the boot disk (512 bytes); executes primary bootloader code and reads partition table information[span_3](start_span)[span_3](end_span). |
| **3** | **GRUB** | Default Linux bootloader; displays the OS selection boot menu and loads the selected Linux Kernel image (`vmlinuz`) into RAM[span_4](start_span)[span_4](end_span). |
| **4** | **Kernel** | The core of the operating system; initializes hardware, mounts the root filesystem in read-only mode, and launches the first user-space process[span_5](start_span)[span_5](end_span). |
| **5** | **Initrd / Initramfs** | Temporary root filesystem loaded into memory to supply essential storage drivers required before mounting the real root filesystem[span_6](start_span)[span_6](end_span). |
| **6** | **Systemd** | The primary init process (PID 1); initializes system services, target environments, and user spaces[span_7](start_span)[span_7](end_span). |

---

## 🛠️ Section 2: Detailed Technical Breakdowns

### 1. BIOS (Basic Input/Output System)
* **Role:** Hardware initialization and POST (Power-On Self-Test) execution[span_8](start_span)[span_8](end_span).
* **Key Action:** Searches for, loads, and executes the bootloader program from a designated bootable storage device (e.g., Hard Disk, SSD, USB Drive)[span_9](start_span)[span_9](end_span).
* **Interview Insight:** BIOS passes control directly to the Master Boot Record (MBR)[span_10](start_span)[span_10](end_span).

### 2. MBR (Master Boot Record)
* **Location:** Stored in the very first sector of a bootable disk (`/dev/sda` or `/dev/hda`)[span_11](start_span)[span_11](end_span).
* **Size:** Size is exactly **512 Bytes**[span_12](start_span)[span_12](end_span).
* **Internal Structure:**
  * **446 Bytes:** Primary Bootloader Code[span_13](start_span)[span_13](end_span)
  * **64 Bytes:** Partition Table Information[span_14](start_span)[span_14](end_span)
  * **2 Bytes:** Magic Number (Validation Check: `0xAA55`)[span_15](start_span)[span_15](end_span)

### 3. GRUB (GRand Unified Bootloader)
* **Role:** The default bootloader used across most modern Linux distributions[span_16](start_span)[span_16](end_span).
* **Key Action:** Displays the boot menu to select the OS/Kernel version and loads the chosen Linux Kernel image (`vmlinuz`) along with `initrd`/`initramfs` into system RAM[span_17](start_span)[span_17](end_span).
* **Configuration Path:** `/boot/grub2/grub.cfg` or `/boot/grub/grub.cfg`[span_18](start_span)[span_18](end_span)

### 4. Kernel Architecture
* **Role:** The foundational core of the Linux operating system[span_19](start_span)[span_19](end_span).
* **Key Action:** Initializes system hardware components, mounts the root filesystem (`/`) in read-only mode initially to load necessary drivers via `initrd`, and then executes the initial user-space process[span_20](start_span)[span_20](end_span).
* **Interview Insight:** The Linux Kernel always executes the first process with **Process ID 1 (PID 1)**[span_21](start_span)[span_21](end_span).

---

## 💻 Practice Execution Log

```bash
# Check the default bootloader configuration
$ cat /boot/grub2/grub.cfg

# Inspect Process ID 1 on a running system
$ ps -p 1 -o comm=

# View boot logs via systemd journal
$ journalctl -b
