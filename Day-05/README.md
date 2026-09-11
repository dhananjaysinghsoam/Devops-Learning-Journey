# Linux Piping, Stream Redirection & Command Processing — Day 05

## Overview
This repository documents my progress in learning DevOps fundamentals. On **Day 05**, I focused on Linux Piping (`|`), data stream redirection, and advanced text-processing utilities including `tee` and `xargs` to build efficient command-line execution pipelines.

---

## 🛠️ Key Concepts & References

| Command / Tool | Category | Description | Syntax / Example |
| :--- | :--- | :--- | :--- |
| **Pipe (`\|`)** | Redirection | Redirects the standard output (`stdout`) of one command to become the standard input (`stdin`) of another. | `command1 \| command2` |
| **`tee`** | Stream Processing | Reads standard input and writes it simultaneously to standard output and to specified files. | `cat file.txt \| tee output.txt` |
| **`xargs`** | Command Execution | Converts standard input stream into command-line arguments for another command. | `cat list.txt \| xargs touch` |
| **`sort`** | Text Processing | Sorts lines of text files alphanumerically (`-r` for reverse sorting). | `cat file.txt \| sort -r` |
| **`uniq`** | Text Processing | Filters out duplicate lines from a sorted input stream. | `cat file.txt \| sort \| uniq` |

---

## 💡 Practical Use Cases & Pipeline Implementations

### Case : Count Files in a Directory
List directory contents in a single column and pass the output to count the total number of items:
```bash
ls -1 | wc -l

Case : Combine File Contents & Sort
Merge contents from names.txt and countries.txt, then sort the combined output:
cat names.txt countries.txt | sort

Case : Extract Unique Records from a File
Process file entries (justfile) to sort in reverse or filter out duplicates:
# Sort in reverse order
cat justfile | sort -r
# Extract unique entries
cat justfile | sort | uniq

💻 Practice Execution Log💻 Practice Execution Log
# Pipeline execution across multiple cases
$ ls -1 | wc -l
$cat names.txt countries.txt \vert{} sort$ cat justfile | sort | uniq

# Tee command: Intercept pipeline and log output to file
$ cat names.txt | tee processed_output.txt | sort

# Xargs command: Convert stdin into CLI arguments
$ ls | echo                      # Output: blank (echo does not accept stdin directly)
$ ls | xargs echo                # Output: displays all file names
$ cat filenames.txt | xargs touch # Batch creates files listed in filenames.txt
