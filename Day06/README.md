# Linux Pattern Searching with Grep Utilities — Day 06

## Overview
This repository documents my progress in learning DevOps fundamentals. On **Day 06**, I focused on mastering the `grep` family of commands and its specialized variants to search, filter, and extract pattern-matched data across standard text files, binary archives, and PDFs.

---

## 🛠️ Key Commands & References

| Command | Category | Description | Syntax |
| :--- | :--- | :--- | :--- |
| **`grep`** | Text Searching | Searches for specified plain text patterns or basic regular expressions within files. | `grep [options] "pattern" filename` |
| **`egrep`** | Text Searching | Extended Grep; supports extended regular expressions (ERE) like `+`, `?`, `\|`, and parenthesis without escaping. | `egrep [options] "pattern" filename` |
| **`pgrep`** | Process Searching | Searches currently running system processes based on name or other attributes and returns their PIDs. | `pgrep [options] "pattern"` |
| **`fgrep`** | Text Searching | Fixed Grep; searches strictly for literal fixed strings, disabling all regular expression metacharacters for faster searches. | `fgrep [options] "string" filename` |
| **`pdfgrep`** | Document Searching | Utility designed to search for regular expression patterns directly inside unencrypted PDF documents. | `pdfgrep [options] "pattern" filename.pdf` |
| **`zgrep`** | Archive Searching | Searches for patterns inside compressed files (`.gz`, `.tgz`) without needing to decompress them first. | `zgrep [options] "pattern" filename.gz` |

---

## 💻 Practice Execution Log

```bash
# Basic Grep search
$ grep -i "error" /var/log/syslog

# Extended Grep (matching multiple patterns)
$ egrep -i "(error|fatal|warning)" application.log

# Process Grep (finding process IDs)
$ pgrep -l nginx

# Fixed Grep (searching literal string containing regex characters)
$ fgrep "192.168.1.1*" config.txt

# Searching inside PDF documents
$ pdfgrep -i "invoice" document.pdf

# Searching directly inside compressed Gzip logs
$ zgrep "500 Internal Server Error" access.log.gz
