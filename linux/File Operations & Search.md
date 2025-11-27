# File Operations & Search

Mastering the command line involves efficiently creating, managing, and finding files within the Linux file system.

## Directory Listing
* **`ls`**: Lists files and directories in the current working directory.
* **`ls -l`**: Displays a detailed list including permissions, owner, group, size, and modification date.
* **`ls -a`**: Shows all files, including **hidden files** (those starting with a dot `.`).

## Basic Operations
* **`touch <filename>`**: Creates a new, empty file or updates the timestamp of an existing one.
* **`mkdir <dirname>`**: Creates a new directory.
* **`echo "text" > file`**: Writes text into a file, creating it if it doesn't exist or overwriting it.
* **`cp <source> <dest>`**: Copies a file to a new location or name.
* **`mv <source> <dest>`**: Moves a file or **renames** it.
* **`rm <file>`**: Removes (deletes) a file.
* **`rmdir <dirname>`**: Removes an **empty** directory.

## Search Techniques
### File Search
* **`locate <pattern>`**: Quickly searches for file paths in a database (e.g., `locate .conf`).
* **`find / -name '<pattern>'`**: Searches the actual file system for files matching a pattern.
    * *Tip:* Use `2>/dev/null` to hide permission denied errors (e.g., `find / -name '*.conf' 2>/dev/null`).

### Content Search (Grep)
* **`grep <string> <file>`**: Searches for a specific string inside a file.
    * *Example:* `grep sh /etc/passwd` finds lines containing "sh".
    * *Invert Match:* `grep -v <string>` displays lines that **do not** contain the string.

---
