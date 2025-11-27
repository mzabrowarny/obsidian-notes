---
tags:
  - linux
  - hub
  - cybersecurity
---

###  File System Hierarchy

Understanding where files are stored is crucial for navigating Linux.

> [!NOTE] Key Directories
> * **`/bin`** – Essential command binaries (e.g., `ls`, `cp`).
> * **`/dev`** – Device files (e.g., hard drives like `/dev/sda`).
> * **`/etc`** – Configuration files (e.g., `passwd`, `resolv.conf`).
> * **`/home`** – User home directories.
> * **`/tmp`** – Temporary files (cleared upon reboot).
> * **`/var`** – Variable data (system logs, cache).

---

### Terminal Shortcuts

Efficiency tools for the command line to speed up your workflow.

| Shortcut                        | Action                                             |
| :------------------------------ | :------------------------------------------------- |
| **`TAB`**                       | Autocomplete commands or file paths.               |
| **`Ctrl + A`** / **`Ctrl + E`** | Jump to the **start** / **end** of the line.       |
| **`Ctrl + U`** / **`Ctrl + K`** | Delete from cursor to **start** / **end** of line. |
| **`Ctrl`** + `←` / `→`          | Jump words (stops at separators: space, `/`, `.`). |
| **`Ctrl + L`**                  | Clear screen (same as `clear`).                    |
| **`Ctrl + C`**                  | Kill the current process.                          |
| **`Ctrl + Z`**                  | Background the current process.                    |
| **`Ctrl + R`**                  | Search command history.                            |
| **`!!`**                        | Repeat the last command.                           |

---