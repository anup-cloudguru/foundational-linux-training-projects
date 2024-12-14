# **Linux Command Cheat Sheet**  

## **Network Commands**  

- **`ip a`** – Show IP address information.  
  ```bash  
  ip a                                # Display all network interfaces and their IP addresses  
  ```

- **`ip addr`** – Display IP addresses of network interfaces.  
  ```bash  
  ip addr                             # Show IP addresses for all network interfaces  
  ```

- **`ifconfig`** – (Deprecated but still works) Display network interfaces and their IP addresses.  
  ```bash  
  ifconfig                            # Show network interfaces and IP details  
  ```

- **`hostname -I`** – Show all IP addresses associated with the system.  
  ```bash  
  hostname -I                        # Display the IP address of the system  
  ```

---

## **Accessing Linux via SSH**  

- **`ssh`** – Secure Shell to access remote systems.  
  ```bash  
  ssh user@hostname_or_ip             # Access a remote system via SSH (replace 'user' and 'hostname_or_ip')  
  ssh username@192.168.1.100          # Example with IP address  
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

- **`su`** – Switch to another user account.  
  ```bash  
  su username            # Switch to another user (replace 'username' with the desired user)  
  su - username          # Switch to another user and start a login shell  
  ```

- **`exit`** – Exit the current session or log out.  
  ```bash  
  exit                   # Exit the current user shell session  
  ```

---

## **Interrupt a Running Command or Process**  

- **`Ctrl + C`** – Interrupt a running command or process.  
  ```bash  
  # Press Ctrl + C to stop a running process  
  ```

---

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

- **`vim`** – Open or create a file using the `vim` editor.  
  ```bash  
  vim file1.txt                       # Open (or create) file1.txt in vim editor  
  # Press 'Esc', then ':wq' to save and exit.  
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
  rm -rf dir1                         # Remove a directory and its contents without confirmation, even for write-protected files  
  ```

- **`mkdir`** – Create a new directory.  
  ```bash  
  mkdir new_directory                 # Create a new directory  
  mkdir -p parent_dir/sub_dir         # Create nested directories  
  ```

- **`find`** – Search for files and directories.

```bash
find . -name "file1.txt"            # Search for file1.txt in the current directory (.)
find . -type d -name "DirectoryName"      # Search for a directory name in the current directory (.)
```

### **`locate`** – Quickly search for files and directories using a prebuilt database.

```bash
locate file1.txt                    # Search for file1.txt in the system's database
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
