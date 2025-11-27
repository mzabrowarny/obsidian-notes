---
tags:
  - linux
  - processes
  - systemd
  - cron
---
Managing running tasks and background services is a daily task in Linux environments.

## Process Management
* **`ps`**: Lists currently running processes for the current shell session.
* **`ps aux`**: Displays a detailed list of **all** running processes (users, PID, CPU/Mem usage).
* **`ps auxf`**: Shows processes in a hierarchical tree view, visualizing parent-child relationships.
* **`top`**: Provides a dynamic, real-time view of system processes and resource usage.
    * *Control:* `Ctrl + C` stops a running program.
    * *Backgrounding:* `Ctrl + Z` pauses a process and sends it to the background.

## System Services (Systemd)
* **`systemctl status <service>`**: Checks the status of a specific service (e.g., `ssh`), showing active state, logs, and errors.

## Cron Jobs (Scheduling)
* **`/etc/crontab`**: The system-wide configuration file for scheduled tasks.
* **`crontab -e`**: Opens an editor to manage personal cron jobs for the current user.
* **Security Note**: Misconfigured cron jobs (e.g., writable scripts running as root) can be used for privilege escalation.

---
