# Foundational Linux Training Projects

This repository, **foundational-linux-training-projects**, is a comprehensive collection of projects and exercises inspired by the *"Complete Linux Training Course to Get Your Dream IT Job 2024"* by **Imran Afzal** on Udemy. The purpose of this repository is to document my journey of learning and practical application of Linux fundamentals. Through this project, I aim to build a solid foundation in Linux, preparing for real-world scenarios and enhancing my skills.  
You can access the course [here](https://www.udemy.com/course/complete-linux-training-course-to-get-your-dream-it-job/).

---

## Project Overview

### Download, Install, and Configure
- Downloading and Installing Oracle VirtualBox  
- Creating Virtual Machines  
- Virtual Machine Management  
- Downloading and Installing CentOS  
- Exploring the Linux Desktop (GUI)  

### System Access and File System
- Accessing Linux System  
- Installing and Using PuTTY  
- Network Commands: `ifconfig`, `ip`  
- Connecting Linux VM via PuTTY  
- File System Introduction and Structure  
- Navigation and Commands for File Systems  
- File and Directory Creation  
- Finding Files and Directories: `find`, `locate`  
- File and Directory Path Management  
- Wildcards and File Types  
- Managing Passwords and Links  
- Opening Image Files in GUI  

### Linux Fundamentals
- Command Syntax and Structure  
- File Permissions (`chmod`) and Ownership (`chown`, `chgrp`)  
- Getting Help: `man` pages, `whatis`  
- Keyboard Shortcuts: TAB Completion and Up Arrow  
- Text File Creation and Manipulation  
- Output Redirection (`tee` command) and Pipes (`|`)  
- File Maintenance and Display Commands  
- Text Processing Commands: `cut`, `sort`, `grep`, `awk`, `uniq`, `wc`  
- Comparing Files: `diff`, `cmp`  
- File Compression: `tar`, `gzip`, `gunzip`  
- Truncating File Size (`truncate`)  
- Combining and Splitting Files: `cat`, `split`  
- Linux vs. Windows Command Comparison  

### Linux System Administration
- Using `vi` Text Editor and `sed` Command  
- User Account Management  
- Switching Users and Managing Sudo Access  
- User Monitoring and Communication  
- Linux Directory Service (Account Authentication)  
- Essential System Utility Commands  
- Process and Schedule Management: `systemctl`, `ps`, `top`, `crontab`  
- System Monitoring Commands  
- Operating System Maintenance: `shutdown`, `reboot`, etc.  
- System Logs and Monitoring (`/var/log`)  
- Host Management: Changing Hostname (`hostnamectl`)  
- Finding System Information: `uname`, `/etc/*rel*`, `dmidecode`  
- System Architecture Overview  
- Terminal Controls and Commands  
- Root Password Recovery (Single User Mode)  
- Environment Variables and SOS Report  

### Shell Scripting
- Understanding the Linux Kernel  
- Introduction to Shells and Types  
- Basic Shell Scripting  
- Creating If-Then, For Loop, and Do-While Scripts  
- Case Statement Scripts  
- Using Aliases and Command History  

### Networking, Servers, and System Updates
- Enabling Internet in Linux VM  
- Network Components and Commands: `ping`, `ifconfig`, `netstat`, `tcpdump`  
- NIC Information (`ethtool`) and Bonding  
- Downloading Files with `wget` and `curl`  
- File Transfer Commands: `ftp`, `scp`  
- System Updates, Repositories, and Package Management  
- Creating a Local Repository  
- Patch Management and Rollbacks  
- SSH, Telnet, DNS, and Hostname Lookup  
- NTP, `chronyd`, Sendmail, and Apache Web Server  
- Central Logging with `rsyslogd`  
- Securing Linux (OS Hardening)  
- OpenLDAP Installation and Network Traffic Tracing  

### Disk Management and Run Levels
- System Run Levels and Boot Process  
- Customizing the Message of the Day  
- Storage and Disk Partitioning: `df`, `fdisk`  
- Creating Standard and LVM Partitions  
- LVM Configuration and Disk Extension  
- Adding Swap Space and RAID Management  
- File System Check and Repair: `fsck`, `xfs_repair`  
- Backup Solutions (`dd` Command)  
- Network File System (NFS)  
- CentOS/Red Hat Comparisons (versions 5, 6, and 7)  

---

## My Learning Journey

This repository represents the beginning of my cloud engineering journey. My goal is to gain hands-on Linux skills, which will be essential for managing cloud-based environments, automating infrastructure, and securing systems. By working through the course and documenting the projects here, I aim to build a solid foundation for tackling more advanced cloud technologies in the future.

---

## Project Structure

The repository is organized by modules, each corresponding to a chapter from the course. Below is an outline of the structure:

- `Module 1: Virtual Lab Setup/`
  - `01-setup-virtualbox.md`
  - `02-virtualbox-vm-setup.md`
  - `03-linux-centos-stream-install.md`
  - `04-taking-snapshots-virtualbox.md`
  
- `Module 2: System Access and File Management/`
  - `01-important-things-to-remember-in-linux.md`
  - `02-accessing-linux-system.md`
  - `03-accessing-linux-putty-ssh.md`
  - `04-regaining-command-prompt.md`
  - `05-filesystem-basics.md`
  - `06-navigating-file-system-cd-ls-pwd.md`
  - `07-file-and-directory-properties.md`
  - `08-linux-file-types.md`
  - `09-understanding-root-in-linux.md`
  - `10-changing-user-passwords.md`
  - `11-absolute-and-relative-paths.md`
  - `12-creating_files_and_directories.md`

- `Screenshots/`
  - `01-touch-command.png`
  - `02-cp-command.png`
  - `03-vi-editor-save-exit.png`
  - `...`

---

## Why This Repository?

This repository serves as a practical resource for learning and practicing Linux in a structured manner. By following the projects and exercises, you will be able to:
- Gain a comprehensive understanding of Linux as an operating system.  
- Practice essential commands and configurations in a controlled environment.  
- Build a solid hands-on foundation for advancing in cloud engineering and other IT-related fields.  

---

## Future Enhancements

As I progress in my learning, I plan to expand the repository with more advanced topics such as:
- Advanced shell scripting techniques
- Networking and security for cloud environments
- Introduction to Docker and containerization in Linux
- Linux in cloud platforms like AWS and Azure

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
