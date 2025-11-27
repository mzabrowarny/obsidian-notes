# User Management

Enumerating users and understanding identity is critical for both administration and penetration testing.

## Current User Context
* **`whoami`**: Displays the username of the current user.
* **`id`**: Shows user identity details, including UID (User ID), GID (Group ID), and group memberships.
* **`echo $USER`**: Displays the user environment variable.

## User Enumeration
* **`who`**: Lists users currently logged into the system.
* **`last`**: Shows a history of the last user logins.
* **`cat /etc/passwd`**: Displays the system's user database (username, UID, GID, home dir, shell).

## Search Techniques (Grep)
* **Find Shell Users**: `grep sh /etc/passwd` helps find users with a login shell.
* **Find Active Users**: `grep -v nologin /etc/passwd` filters out service accounts that cannot log in.

## Switching Users
* **`su`**: Switch User. Used to switch to another account (e.g., root) if you know the password.

---
