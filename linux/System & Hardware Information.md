1# System & Hardware Information

Commands to identify the operating system version and underlying hardware resources.

## Operating System
* **`cat /etc/os-release`**: detailed OS info (name, version, ID).
* **`cat /etc/issue`**: A simple welcome message/version info.
* **`uname -a`**: Full system info including kernel name, version, and architecture.
* **`cat /proc/version`**: Detailed kernel version and compiler info.

## CPU & Memory
* **`cat /proc/cpuinfo`**: Detailed processor info (model, cores, speed).
* **`cat /proc/meminfo`**: Detailed system memory statistics.
* **`free -h`**: Human-readable summary of RAM and Swap usage.

## Storage & Devices
* **`df -h`**: Disk space usage for mounted filesystems.
* **`lsblk`**: Lists block devices (disks, partitions) and mount points.
* **`lspci`**: Lists devices connected to the PCI bus.
* **`lsusb`**: Lists connected USB devices.
* **`lshw`**: Detailed hardware configuration (requires root usually).

---
