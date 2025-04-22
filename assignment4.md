# Assignment - 4 (Linux Working)

## Answer the short questions:

Here are concise pointwise answers to your short questions:

---

### **1. What is the use of the `sudo` command in Linux?**

- Allows a permitted user to execute commands as a superuser or another user.
- Example: `sudo apt update` runs the command with administrative privileges.

---

### **2. What is cron job scheduling in Linux?**

- A way to schedule repetitive tasks or scripts at specific intervals.
- Managed using `crontab`.
- Example: `0 5 * * * /path/to/script.sh` runs the script daily at 5 AM.

---

### **3. How do you check system performance in Linux?**

- `top` or `htop` – real-time process monitoring.
- `vmstat` – memory usage.
- `iostat` – CPU and disk I/O.
- `free -h` – RAM usage.
- `uptime` – system load.

---

### **4. What is the purpose of the `/etc/passwd` file?**

- Stores user account information (username, UID, home directory, shell, etc.).
- Format: `username:x:UID:GID:info:home:shell`
- Passwords are usually stored in `/etc/shadow`.

---

### **5. Define process IDs (PID) in Linux.**

- A unique numeric identifier assigned to each running process.
- Use `ps`, `top`, or `pidof <process>` to find PIDs.

---

### **6. What are Linux runlevels?**

- Represent different states of the system (e.g., single-user mode, multi-user, reboot).
- Traditional SysV Init levels:
  - `0` – Halt
  - `1` – Single-user
  - `3` – Multi-user (console)
  - `5` – Multi-user with GUI
  - `6` – Reboot

(Systemd now uses `targets` like `graphical.target` instead.)

---

### **7. Explain the difference between `apt-get` and `yum`.**

- `apt-get`: Debian/Ubuntu-based systems (uses `.deb` packages).
- `yum`: RedHat/CentOS-based systems (uses `.rpm` packages).
- Both are package managers but for different Linux families.

---

### **8. How do you change file ownership in Linux?**

- Use `chown` command.
- Syntax: `chown user:group file`
- Example: `sudo chown alice:admin file.txt`

---

### **9. What is the difference between `kill` and `killall` commands?**

- `kill`: Sends a signal to a specific process by PID.
- `killall`: Sends a signal to all processes by name.
- Example: `kill 1234` vs `killall firefox`

---

### **10. What is the role of the `df` and `du` commands?**

- `df`: Displays disk space usage of file systems.
  - Example: `df -h`
- `du`: Shows disk usage of files/directories.
  - Example: `du -sh /home/user`

---

### 🔗 **Resources**

- [sudo command – Linuxize](https://linuxize.com/post/using-the-sudo-command/)
- [cron jobs – crontab.guru](https://crontab.guru/)
- [Linux performance commands – GeeksforGeeks](https://www.geeksforgeeks.org/linux-performance-monitoring-commands/)
- [Understanding /etc/passwd – The Geek Stuff](https://www.thegeekstuff.com/2012/01/etc-passwd/)
- [PID and process management – Linux Handbook](https://linuxhandbook.com/linux-process/)
- [Runlevels vs Systemd targets – RedHat](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/system_administrators_guide/chap-managing_services_with_systemd)
- [apt vs yum – Unixmen](https://www.unixmen.com/difference-between-yum-and-apt-get/)
- [chown – Linuxize](https://linuxize.com/post/linux-chown-command/)
- [kill vs killall – Linuxize](https://linuxize.com/post/killall-command-in-linux/)
- [df vs du – Linux Handbook](https://linuxhandbook.com/df-vs-du/)

---

## Answer the long questions:

### **1. Step-by-Step Process of Installing Linux**

1. **Download ISO**: Choose a Linux distribution (e.g., Ubuntu, Fedora) and download its ISO file from the official site.
2. **Create Bootable USB**: Use tools like Rufus (Windows) or `dd` (Linux/macOS) to create a bootable USB drive.
3. **Boot from USB**: Restart your PC and enter BIOS/UEFI settings. Set USB as the first boot device.
4. **Run Installer**: Boot into the Linux installer and select “Install Linux.”
5. **Partition Disk**: Choose automatic/manual partitioning. Define root (`/`), swap, and optionally `/home`.
6. **Select Region & Keyboard**: Choose your timezone and keyboard layout.
7. **Create User Account**: Set a username, password, and hostname.
8. **Install System**: The installer copies files and installs Linux.
9. **Remove USB & Reboot**: After installation, remove the USB and reboot into your new Linux system.

---

### **2. Installing Open-Source Software in Linux**

1. **Using Package Managers**:
   - Debian/Ubuntu: `sudo apt install <package-name>`
   - Red Hat/CentOS: `sudo yum install <package-name>`
   - Fedora: `sudo dnf install <package-name>`
   - Arch: `sudo pacman -S <package-name>`
2. **Using Snap/Flatpak**:
   - Snap: `sudo snap install <package-name>`
   - Flatpak: `flatpak install <repo> <package>`
3. **Using Source Code**:
   - Download source: `git clone <repo>` or `.tar.gz`
   - Install dependencies: `sudo apt install build-essential`
   - Compile: `./configure && make && sudo make install`
4. **Using AppImage**:
   - Make executable: `chmod +x <file>.AppImage`
   - Run: `./<file>.AppImage`

---

### **3. User Account Management in Linux**

1. **Add User**: `sudo adduser <username>`
2. **Delete User**: `sudo deluser <username>`
3. **Modify User**: `sudo usermod -aG sudo <username>` (add to sudo group)
4. **Change Password**: `passwd <username>`
5. **List Users**: View `/etc/passwd`
6. **Lock/Unlock User**: `sudo usermod -L <username>` / `-U`
7. **Switch User**: `su <username>` or `sudo -i`

---

### **4. Package Management Tools in Linux**

1. **APT (Debian/Ubuntu)**: `apt install`, `apt update`, `apt upgrade`
2. **YUM (RedHat/CentOS)**: `yum install`, `yum update`
3. **DNF (Fedora)**: Replaces YUM. `dnf install`
4. **Pacman (Arch Linux)**: `pacman -Syu`, `pacman -S <package>`
5. **Zypper (openSUSE)**: `zypper install`
6. **Snap**: Universal packages. `snap install`
7. **Flatpak**: Sandbox package manager. `flatpak install`
8. **rpm/deb**: Install packages manually: `dpkg -i`, `rpm -ivh`

---

### **5. Linux File System Structure**

1. `/` – Root directory.
2. `/home` – User directories.
3. `/bin` – Essential binaries (e.g., `ls`, `cat`).
4. `/sbin` – System binaries (for admin tasks).
5. `/etc` – Configuration files.
6. `/var` – Variable files (logs, spool).
7. `/usr` – User installed software.
8. `/tmp` – Temporary files.
9. `/dev` – Device files.
10. `/mnt` & `/media` – Mounted drives and external devices.
11. `/boot` – Bootloader files.
12. `/lib` – Shared libraries.

---

### **6. Environment Variables in Linux**

1. **Definition**: Key-value pairs used to configure system and app behavior.
2. **Common Examples**:
   - `PATH`: Directories to search for executables.
   - `HOME`: Current user’s home directory.
   - `USER`, `SHELL`, `EDITOR`, etc.
3. **View Variables**: `printenv` or `env`
4. **Set Temporarily**: `export VAR=value`
5. **Set Permanently**:
   - For a user: Add `export VAR=value` to `~/.bashrc` or `~/.profile`
   - For system-wide: Edit `/etc/environment`

---

### **7. Process Management in Linux**

1. **List Processes**: `ps aux`, `top`, `htop`
2. **Kill Process**:
   - `kill <PID>` (graceful)
   - `kill -9 <PID>` (force)
3. **Start Background Process**: `command &`
4. **Bring to Foreground**: `fg`
5. **Stop Process**: `Ctrl+Z`
6. **Check Process Tree**: `pstree`
7. **Change Priority**:
   - `nice -n 10 <command>`
   - `renice -n -5 <PID>`

---

### **8. Disk Partitioning and Disk Management**

1. **View Partitions**: `lsblk`, `fdisk -l`, `parted -l`
2. **Create/Modify Partitions**:
   - `fdisk /dev/sdX` (MBR)
   - `gdisk` or `parted` (GPT)
3. **Create File System**: `mkfs.ext4 /dev/sdX1`
4. **Mount Partition**: `mount /dev/sdX1 /mnt`
5. **Unmount**: `umount /mnt`
6. **Resize Partition**: `resize2fs`, `gparted`
7. **Disk Usage**: `df -h`, `du -sh *`

---

### **9. System Logs in Linux**

1. **Log Directory**: `/var/log/`
2. **Common Log Files**:
   - `/var/log/syslog` (Debian/Ubuntu)
   - `/var/log/messages` (RedHat/CentOS)
   - `/var/log/auth.log` – Authentication logs
   - `/var/log/kern.log` – Kernel logs
3. **View Logs**:
   - `cat`, `less`, `tail -f /var/log/syslog`
4. **Log Rotation**: Managed by `logrotate`
5. **Journal Logs (Systemd)**: `journalctl`, `journalctl -xe`, `journalctl -u <service>`

---

### **10. Network Configuration in Linux**

1. **View Interfaces**: `ip a` or `ifconfig`
2. **Assign IP Address**:
   - Temporary: `ip addr add 192.168.1.10/24 dev eth0`
   - Permanent: Edit `/etc/network/interfaces` or use `netplan` or `NetworkManager`
3. **Restart Networking**:
   - `sudo systemctl restart networking` or `network-manager`
4. **Check Connection**: `ping`, `traceroute`, `nslookup`
5. **DNS Settings**: `/etc/resolv.conf`
6. **Routing Table**: `ip route`
7. **Network Services**: `systemctl status NetworkManager`, `nmcli`, `nmtui`

---

### 🔗 **Resources**

- [Ubuntu Linux Installation Guide](https://ubuntu.com/tutorials/install-ubuntu-desktop)
- [Linux Package Management](https://wiki.debian.org/PackageManagement)
- [Linux Filesystem Hierarchy](https://tldp.org/LDP/Linux-Filesystem-Hierarchy/html/index.html)
- [Linux Environment Variables](https://linuxize.com/post/how-to-set-and-list-environment-variables-in-linux/)
- [Process Management](https://linuxize.com/post/how-to-use-ps-command-to-monitor-linux-processes/)
- [Disk Partitioning](https://wiki.archlinux.org/title/Partitioning)
- [System Logging](https://www.thegeekstuff.com/2011/08/linux-logs/)
- [Network Configuration](https://wiki.archlinux.org/title/Network_configuration)

---

<p align="right"><strong>- Aarsh Patel</strong></p>
