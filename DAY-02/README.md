# Linux File Operations & Searching - Day 02

## Overview

This repository documents my progress in learning DevOps fundamentals. On **Day 02**, I focused on Linux CLI commands for file management, viewing, text processing, searching, and file comparison.

---

## 🛠️ Key Commands & References

| Command | Category | Description |
| :--- | :--- | :--- |
| `rm -rf <path>` | File Operations | Forcefully and recursively removes files or directories |
| `cp <src> <dest>` | File Operations | Copies files or directories from source to destination |
| `mv <src> <dest>` | File Operations | Moves or renames files and directories |
| `head -5 <file>` | File Viewing | Displays the first 5 lines of a file |
| `tail -5 <file>` | File Viewing | Displays the last 5 lines of a file |
| `sort <file>` | Text Processing | Sorts lines of text alphabetically or numerically |
| `sort -r <file>` | Text Processing | Sorts lines in reverse (descending) order |
| `sort <file> \| uniq` | Text Processing | Filters out duplicate lines after sorting |
| `split -l 3 <file>` | Text Processing | Splits a file into smaller files of 3 lines each |
| `shuf <file>` | Text Processing | Generates random permutations of lines in a file |
| `wc -l <file>` | Text Processing | Counts the total number of lines in a file |
| `grep "<pattern>" <file>` | Text Searching | Searches for specific text patterns within a file |
| `egrep "<pattern>" <file>` | Text Searching | Searches using Extended Regular Expressions |
| `ls *` | Navigation | Lists contents of current directory and all subdirectories |
| `cmp <file1> <file2>` | File Comparison | Compares two files byte-by-byte |
| `diff -u <file1> <file2>` | File Comparison | Displays unified differences between two files |
| `find <path> -name "<name>"` | System Utility | Searches for files or directories in real-time |
| `updatedb` | System Utility | Updates the file index database for fast searching |
| `locate <filename>` | System Utility | Quickly finds files using the indexed database |
| `history` | System Utility | Displays the list of previously executed commands |

---

## 💻 Practice Execution Log

```bash
# File operations and renaming
$ cp sample.txt backup.txt
$ mv old_name.txt new_name.txt
$ rm -rf temp_dir

# Inspect and process text content
$ head -5 data.txt
$ tail -5 data.txt
$sort names.txt \vert{} uniq$ wc -l logfile.log

# Search patterns and compare files
$ grep "ERROR" application.log
$ diff -u config_v1.json config_v2.json

# Locate files and check terminal history
$ find . -name "*.txt"
$ history | tail -10
