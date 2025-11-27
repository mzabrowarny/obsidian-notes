# Package Management

Kali Linux (Debian-based) uses the `apt` command to manage software packages (.deb).

## Updates & Upgrades
* **`apt update`**: Refreshes the list of available packages from repositories.
* **`apt upgrade`**: Upgrades currently installed packages to the newest versions without removing existing packages.
* **`apt full-upgrade`**: Performs a full upgrade, adding new dependencies or removing packages if necessary.

## Cleanup
* **`apt autoremove`**: Removes packages that were installed as dependencies but are no longer needed.
* **`apt clean`**: Clears the local cache of retrieved package files.

## Information
* **`apt list --upgradable`**: Lists all packages that have a newer version available.

---
