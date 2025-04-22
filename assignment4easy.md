# Assignment - 4 (Linux Working)

## Answer the short questions:

### **1. What is the use of the `sudo` command in Linux?**

- `sudo` stands for **Super User Do**.
- It allows a **normal user to run commands as an administrator** (root user).
- Example: `sudo apt update` lets you update the system with admin rights.

---

### **2. What is cron job scheduling in Linux?**

- A **cron job** is a way to **automate tasks** at specific times or intervals.
- It uses the **cron service** to run commands like backups or updates automatically.
- Example: Run a script every day at 8 AM.

---

### **3. How do you check system performance in Linux?**

- Use these commands:
  - `top`: Shows running processes and CPU/memory usage.
  - `htop`: A better version of `top` (if installed).
  - `free -h`: Shows memory usage.
  - `uptime`: Shows how long the system has been running.

---

### **4. What is the purpose of the `/etc/passwd` file?**

- It stores **user account information**.
- Each line represents a user, with details like username, user ID (UID), home directory, and default shell.
- It does **not store passwords** directly.

---

### **5. Define Process IDs (PID) in Linux.**

- A **PID (Process ID)** is a unique number given to every **running program or process**.
- You can see it using the `ps` or `top` command.

---

### **6. What are Linux runlevels?**

- **Runlevels** are **modes of operation** in Linux, like:
  - 0 = Shutdown
  - 1 = Single-user mode
  - 3 = Multi-user (no GUI)
  - 5 = Multi-user with GUI
  - 6 = Reboot
- Modern Linux uses **systemd targets** instead of runlevels.

---

### **7. Explain the difference between `apt-get` and `yum`.**

- Both are **package managers** used to install or update software.
  - `apt-get`: Used in **Debian-based** systems (like Ubuntu).
  - `yum`: Used in **RedHat-based** systems (like CentOS).
- They work differently but serve the same purpose.

---

### **8. How do you change file ownership in Linux?**

- Use the `chown` command.
- Example: `sudo chown user:group file.txt` changes the owner of `file.txt`.
- Helps control **who can access or edit a file**.

---

### **9. What is the difference between `kill` and `killall` commands?**

- `kill <PID>`: Stops a specific process using its **process ID**.
- `killall <process_name>`: Stops **all processes** with that name.
- Example:
  - `kill 1234` kills process with PID 1234.
  - `killall firefox` kills all Firefox processes.

---

### **10. What is the role of the `df` and `du` commands?**

- `df`: Shows **disk space usage** of file systems (like drives).
  - Example: `df -h` (human-readable).
- `du`: Shows **disk usage of files/folders**.
  - Example: `du -sh /home` shows size of the `/home` directory.

---

### 🔗 **Resources**

- [Linux sudo Guide](https://linuxize.com/post/how-to-use-sudo-on-linux/)
- [Cron Job Basics](https://opensource.com/article/19/7/cron-linux)
- [System Performance Tools](https://linuxhint.com/check_cpu_usage_linux/)
- [Linux File Ownership](https://www.geeksforgeeks.org/chown-command-in-linux-with-examples/)
- [Process Management](https://www.tecmint.com/manage-processes-in-linux/)
- [df and du usage](https://linuxize.com/post/check-disk-usage-in-linux-with-du-and-df/)

---

## Answer the long questions:

### 1. **Step-by-Step Process of Installing Linux**

1. **Download Linux ISO:** Go to a Linux distro website (e.g., Ubuntu) and download the ISO file.
2. **Create Bootable USB:** Use tools like Rufus (Windows) or Etcher to make a bootable USB with the ISO.
3. **Insert and Restart:** Plug in the USB and restart your PC.
4. **Enter Boot Menu:** Press the boot menu key (like F12, F2, Esc) during startup.
5. **Choose USB:** Select your USB drive to boot from.
6. **Try or Install:** Choose “Try Linux” to test or “Install Linux” to begin installation.
7. **Set Language & Keyboard:** Choose your preferred language and keyboard layout.
8. **Connect to Wi-Fi:** Connect to the internet if required.
9. **Choose Installation Type:**
   - Erase disk and install Linux (clean install).
   - Install alongside another OS (dual boot).
10. **Set User Info:** Enter your name, PC name, username, and password.
11. **Install & Reboot:** The system installs. Once done, remove USB and restart.

---

### 2. **Installing Open-Source Software in Linux**

1. **Using Terminal (APT/YUM/Pacman):**
   - Ubuntu/Debian: `sudo apt install <package-name>`
   - RedHat/CentOS: `sudo yum install <package-name>`
   - Arch: `sudo pacman -S <package-name>`
2. **Using Software Center:** GUI-based, like an app store for Linux (for beginners).
3. **Download Source Code:**
   - Download `.tar.gz` or `.zip`
   - Extract and run:
     ```bash
     ./configure
     make
     sudo make install
     ```
4. **Using Snap/Flatpak:**
   - Snap: `sudo snap install <app-name>`
   - Flatpak: `flatpak install <app-name>`

---

### 3. **User Account Management in Linux**

1. **Add a User:**  
   `sudo adduser <username>`
2. **Delete a User:**  
   `sudo deluser <username>`
3. **Change User Password:**  
   `sudo passwd <username>`
4. **Switch User:**  
   `su <username>` or `sudo -i`
5. **View All Users:**  
   Check `/etc/passwd`
6. **User Groups:**  
   Add user to a group:  
   `sudo usermod -aG <groupname> <username>`

---

### 4. **Different Package Management Tools in Linux**

1. **APT (Debian, Ubuntu):**  
   `sudo apt install package-name`
2. **YUM / DNF (Red Hat, Fedora):**  
   `sudo dnf install package-name`
3. **Pacman (Arch Linux):**  
   `sudo pacman -S package-name`
4. **Zypper (openSUSE):**  
   `sudo zypper install package-name`
5. **Snap (Universal):**  
   `sudo snap install app-name`
6. **Flatpak (Universal):**  
   `flatpak install app-name`

---

### 5. **Linux File System Structure**

- `/` – Root directory (base of the file system)
- `/home` – User files (like Documents, Downloads)
- `/etc` – Configuration files
- `/bin` – Essential binaries (commands like `ls`, `cp`)
- `/usr` – User-installed software
- `/var` – Variable data (like logs)
- `/tmp` – Temporary files
- `/dev` – Device files (like USBs, hard drives)
- `/proc` – System information (virtual files)

---

### 6. **Environment Variables in Linux**

- These are settings used by the system and programs.
- Example: `PATH` – tells Linux where to find programs.

**Common Commands:**

- View: `printenv` or `echo $VARIABLE`
- Set temporarily: `export VAR=value`
- Set permanently: Add `export VAR=value` in `~/.bashrc` or `~/.bash_profile`

---

### 7. **Managing Processes in Linux**

1. **View Running Processes:**  
   `ps`, `top`, or `htop`
2. **Kill a Process:**  
   `kill <PID>` or `killall <process-name>`
3. **Start in Background:**  
   `command &`
4. **Foreground to Background:**  
   Press `Ctrl + Z` then type `bg`
5. **See Background Jobs:**  
   `jobs`
6. **Stop a Job:**  
   `fg` to bring it back, then `Ctrl + C` to stop

---

### 8. **Disk Partitioning and Management in Linux**

1. **Partitioning Tools:**
   - CLI: `fdisk`, `parted`
   - GUI: GParted
2. **Check Disk Info:**
   - `lsblk`, `df -h`, `blkid`
3. **Mount a Partition:**
   - `mount /dev/sdX /mnt/folder`
4. **Unmount:**
   - `umount /mnt/folder`
5. **Create Filesystem:**
   - `mkfs.ext4 /dev/sdX`

---

### 9. **System Logs in Linux**

1. **Logs are stored in:**  
   `/var/log/`
2. **Important Log Files:**
   - `/var/log/syslog` or `/var/log/messages`: System messages
   - `/var/log/auth.log`: Authentication logs
   - `/var/log/dmesg`: Boot messages
3. **View Logs:**
   - `cat`, `less`, `tail -f /var/log/syslog`
4. **Log Management Tool:**
   - `journalctl` (for systemd-based systems)

---

### 10. **Network Configuration in Linux**

1. **Check IP Info:**  
   `ip a` or `ifconfig`
2. **Edit Network Config (older systems):**
   - Files: `/etc/network/interfaces`
3. **Modern Systems (Netplan, NetworkManager):**
   - Netplan: `/etc/netplan/*.yaml`
   - Apply with: `sudo netplan apply`
4. **Restart Network:**
   - `sudo systemctl restart NetworkManager`
5. **Ping Test:**  
   `ping google.com`

---

### 🔗 Resources:

- [Ubuntu Installation Guide](https://ubuntu.com/tutorials/install-ubuntu-desktop)
- [Linux File System Hierarchy](https://refspecs.linuxfoundation.org/FHS_3.0/fhs/index.html)
- [APT Package Manager](https://help.ubuntu.com/lts/serverguide/apt.html)
- [Systemd Journal Logs](https://www.freedesktop.org/software/systemd/man/journalctl.html)
- [Beginner Linux Commands](https://linuxcommand.org/lc3_learning_the_shell.php)

---

<p align="right"><strong>- Aarsh Patel</strong></p>
