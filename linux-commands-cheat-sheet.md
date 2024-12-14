# **Linux Command Cheat Sheet**  

## **Basic Commands**  

- **`pwd`** – Print the current working directory.  
  ```bash  
  pwd  
  ```  

- **`cd`** – Change the current directory.  
  ```bash  
  cd /path/to/directory    # Navigate to a specific directory  
  cd ..                    # Go back one directory level  
  cd ~                     # Go to the home directory  
  ```  

- **`ls`** – List the contents of a directory.  
  ```bash  
  ls                       # List files in the current directory  
  ls -l                    # List with detailed information  
  ls -lt                   # List sorted by modification time  
  ls -ltr                  # List in reverse order of modification time  
  ```  

---

## **File and Directory Management**  

- **`touch`** – Create an empty file.  
  ```bash  
  touch file1.txt                     # Create a file named file1.txt  
  touch file1.txt file2.txt           # Create multiple files at once  
  ```  

- **`cp`** – Copy files and directories.  
  ```bash  
  cp file1.txt file2.txt              # Copy file1.txt to file2.txt  
  cp -R dir1 /home/anupmoitra/dir2    # Copy dir1 to dir2, including all subdirectories and files  
  ```  

- **`mv`** – Move or rename files and directories.  
  ```bash  
  mv file1.txt /path/to/destination   # Move file1.txt to a new location  
  mv old_dir new_dir                  # Rename directory  
  ```  

- **`rm`** – Remove files or directories.  
  ```bash  
  rm file1.txt                        # Remove a file  
  rm -r dir1                          # Remove a directory and its contents  
  ```  

- **`mkdir`** – Create a new directory.  
  ```bash  
  mkdir new_directory                 # Create a new directory  
  mkdir -p parent_dir/sub_dir         # Create nested directories  
  ```  

- **`find`** – Search for files and directories.  
  ```bash  
  find . -name "file1.txt"            # Search for file1.txt in the current directory  
  find /home -type f -name "*.txt"    # Find all .txt files in /home  
  find /var -mtime -7                 # Find files modified in the last 7 days  
  ```  

- **`locate`** – Quickly search for files and directories using a prebuilt database.  
  ```bash  
  locate file1.txt                    # Search for file1.txt  
  sudo updatedb                       # Update the locate database  
  ```  

---

## **File and Directory Properties**  

- **`ls`** – Display file types and properties.  
  ```bash  
  ls -l                               # Show file permissions, owner, group, and size  
  ls -lh                              # Show sizes in human-readable format  
  ```  

- **`stat`** – Display detailed file information.  
  ```bash  
  stat file1.txt                      # Display detailed information about file1.txt  
  ```  

---

## **User and Access Management**  

- **`whoami`** – Display the current logged-in username.  
  ```bash  
  whoami  
  ```  

- **`passwd`** – Change user passwords.  
  ```bash  
  passwd                              # Change your own password  
  sudo passwd username                # Change the password of another user (requires sudo)  
  ```  

---

## **File Paths**  

- **Absolute Paths**: Start from the root directory (`/`).  
  ```bash  
  cd /home/anupmoitra/Documents        # Navigate using an absolute path  
  ```  

- **Relative Paths**: Start from the current directory.  
  ```bash  
  cd ../Projects                       # Navigate to the Projects directory in the parent directory  
  ```  

---

## **Copying Directories**  

- **`cp -R`** – Copy directories and their contents recursively.  
  ```bash  
  cp -R source_directory destination_directory  
  cp -R dir1 /home/anupmoitra/dir2     # Copy dir1 to /home/anupmoitra/dir2  
  ```  

---

## **Network Commands**  

- **`ip a` or `ip addr`** – Display IP address and network interface details.  
  ```bash  
  ip a                                # Show all interfaces and their IP addresses  
  ip addr                             # Same as ip a, with detailed network interface information  
  ```  
  - Displays IP addresses, subnet masks, and interface status.  
  - Modern replacement for `ifconfig`.  

- **`ifconfig`** – (Deprecated) Display network interfaces and their IP addresses.  
  ```bash  
  ifconfig                            # Show network interfaces and IP details  
  ```  
  - Includes additional network information such as MAC addresses and packet stats.  
  - Still works but is considered outdated.  

- **`hostname -I`** – Display all IP addresses assigned to the host.  
  ```bash  
  hostname -I                         # Show space-separated IP addresses for the host  
  ```  
  - Does not show the loopback address (`127.0.0.1`).  
  - Provides a concise list of IPs without interface details.  

---

## **Accessing Linux via SSH**  

- **`ssh`** – Secure Shell to access remote systems.  
  ```bash  
  ssh user@hostname_or_ip             # Access a remote system via SSH (replace 'user' and 'hostname_or_ip')  
  ssh username@192.168.1.100          # Example with IP address  
  ```  

---
