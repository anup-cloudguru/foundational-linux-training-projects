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

## Table of Contents

### Module 1: Virtual Lab Setup
- [01-setup-virtualbox.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/01-virtual-lab-setup/01-setup-virtualbox.md)
- [02-virtualbox-vm-setup.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/01-virtual-lab-setup/02-virtualbox-vm-setup.md)
- [03-linux-centos-stream-install.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/01-virtual-lab-setup/03-linux-centos-stream-install.md)
- [04-taking-snapshots-virtualbox.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/01-virtual-lab-setup/04-taking-snapshots-virtualbox.md)

### Module 2: System Access and File Management
- [01-important-things-to-remember-in-linux.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/02-system-access-and-file-management/01-important-things-to-remember-in-linux.md)
- [02-accessing-linux-system.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/02-system-access-and-file-management/02-accessing-linux-system.md)
- [03-accessing-linux-putty-ssh.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/02-system-access-and-file-management/03-accessing-linux-putty-ssh.md)
- [04-regaining-command-prompt.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/02-system-access-and-file-management/04-regaining-command-prompt.md)
- [05-filesystem-basics.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/02-system-access-and-file-management/05-filesystem-basics.md)
- [06-navigating-file-system-cd-ls-pwd.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/02-system-access-and-file-management/06-navigating-file-system-cd-ls-pwd.md)
- [07-file-and-directory-properties.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/02-system-access-and-file-management/07-file-and-directory-properties.md)
- [08-linux-file-types.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/02-system-access-and-file-management/08-linux-file-types.md)
- [09-understanding-root-in-linux.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/02-system-access-and-file-management/09-understanding-root-in-linux.md)
- [10-changing-user-passwords.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/02-system-access-and-file-management/10-changing-user-passwords.md)
- [11-absolute-and-relative-paths.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/02-system-access-and-file-management/11-absolute-and-relative-paths.md)
- [12-creating_files_and_directories.md](https://github.com/anup-cloudguru/foundational-linux-training-projects/blob/main/02-system-access-and-file-management/12-creating_files_and_directories.md)

---

## Usage Instructions

1. **Clone the Repository:**
   - Start by cloning this repository to your local machine:
     ```bash
     git clone https://github.com/anup-cloudguru/foundational-linux-training-projects.git
     ```

2. **Follow Along with the Course:**
   - Each chapter in this repository corresponds to the content covered in the course. You can follow the instructions in the Markdown files and replicate the exercises on your own Linux system.

3. **Test and Practice:**
   - After completing each exercise, try to replicate it on your own Linux system to reinforce the concepts.
   - Troubleshoot any issues by reviewing your steps and checking the course material for clarification.

4. **Review Documentation:**
   - As you complete the exercises, you can review the documentation to ensure you've understood each concept thoroughly.

---

## Learning Goals

The goal of this repository is to provide a structured approach to learning Linux fundamentals, which will serve as the first step in my cloud engineering journey. By mastering Linux, I aim to build a strong foundation for working with cloud technologies, automating infrastructure, securing systems, and managing cloud-based environments.

Each exercise and project in this repository will help me develop critical Linux skills necessary for cloud engineering, and this hands-on experience will prepare me to take on more advanced topics in cloud platforms such as AWS and Azure.

---

## Future Enhancements

As I progress in my learning, I plan to expand the repository with more advanced topics such as:
- Shell scripting
- Cloud integrations
- Containerization and Docker
- Configuration management with tools like Ansible
- Cloud infrastructure automation

Stay tuned for future updates as I continue to build and document my learning journey.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
