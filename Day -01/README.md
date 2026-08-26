# 🐧 Linux Basics & Navigation - Day 01

## 📌 Overview
This repository documents my progress in learning DevOps fundamentals. On **Day 01**, I focused on basic Linux CLI commands essential for environment navigation, directory management, and system inspection.

---

## 🛠️ Key Commands & References

| Command | Category | Description |
| :--- | :--- | :--- |
| `pwd` | System Info | Prints absolute path of the current working directory |
| `whoami` | System Info | Displays the active user profile |
| `date` | System Info | Displays current system date and time |
| `date +%T` | System Info | Formats and prints time in `HH:MM:SS` format |
| `ls` | File System | Lists files and subdirectories |
| `ls -lt` | File System | Lists detailed file metadata sorted by modification time |
| `cd <path>` | Navigation | Changes working directory to specified path |
| `cd ..` | Navigation | Navigates one directory level up |
| `cd ../..` | Navigation | Navigates two directory levels up |
| `mkdir <dir>`| File Operations| Creates a new directory |
| `touch <file>`| File Operations| Creates a new empty file or updates timestamp |

---

## 💻 Practice Execution Log

```bash
# Verify active environment and identity
$pwd$ whoami
$date$ date +%T

# Inspect directory contents
$ls$ ls -lt

# Traverse workspace hierarchy
$cd ..$ cd ../..

# Initialize workspace resources
$ mkdir linux-practice
$cd linux-practice$ touch notes.txt
