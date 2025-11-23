# 5.1 🛡️ Basic Security and Identifying User Types (weight: 2)

**Weight:** 2  
**Description:** Various types of users on a Linux system.  

---

## Key Knowledge Areas & Notes

### 👑 Root and Standard Users
- **Root user**: Superuser, full privileges, can modify all system files.  
  - 🏠 Home directory: `/root`  
  - 🆔 UID: `0`  
  - 💻 Commands:  
    - `whoami` → shows current user  
    - `id root` → shows UID/GID info for root  
- **Standard users**: Limited permissions, cannot modify system files without sudo.  
  - 🆔 UID ≥ 1000  
  - 🏠 Home directories: `/home/username`  
  - 🔄 Practice: Switch user  
    - `su username` → switch to another user  
    - `sudo -i` → become root

### 🖥️ System Users
- Special accounts for running services (e.g., `www-data`, `daemon`).  
- 🚫 Typically no login shell, no home directory.  
- Stored in `/etc/passwd` with shell `/usr/sbin/nologin` or `/bin/false`.  
- 🔍 Practice: Check all users → `cat /etc/passwd`

### 📂 Partial List of Files, Terms, and Utilities
- **/etc/passwd**: Stores basic user info (username, UID, GID, shell)  
- **/etc/shadow**: Stores encrypted passwords, only readable by root 🔒  
- **/etc/group**: Defines groups and group memberships 👥  
- **id**: Show user and group IDs → `id username`  
- **last**: Shows last logins of users → `last`  
- **who**: Show currently logged-in users → `who`  
- **w**: Show users currently logged in and what they are doing → `w`  
- **sudo**: Execute commands as another user (usually root) → `sudo command`  
- **su**: Switch user → `su - username`

### 📝 Lab / Practice
- 📜 List all users and their UID/GID: `cat /etc/passwd`  
- 👤 Check your own UID/GID: `id`  
- 🔄 Switch to root user using `sudo` and `su`  
- 🔒 Observe system users with no login shell: `grep -E '(/sbin/nologin|/bin/false)' /etc/passwd`  
- 📊 Review last logins and current sessions: `last`, `who`, `w`

