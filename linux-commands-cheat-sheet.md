# **🐧 Linux Command Cheat Sheet**

---

## **Network Commands**

- **`ip a` (or `ip addr`)** – Display all network interfaces and their IP addresses.  
  ```bash
  ip a                                # Shorthand for 'ip addr'
  ip addr                             # Full command, provides the same output
  ```
  **Note**: `ip a` is a shorthand for `ip addr`. Both commands are identical in functionality and can be used interchangeably. The choice depends on your typing preference.

- **`ifconfig`** – (Deprecated but still works) Display network interfaces and their IP addresses.
  ```bash
  ifconfig                            # Show network interfaces and IP details
  ```

- **`hostname -I`** – Show all IP addresses associated with the system.
  ```bash
  hostname -I                         # Display the IP address of the system
  ```

---

## **Accessing Linux via SSH**

- **`ssh`** – Secure Shell to access remote systems.
  ```bash
  ssh user@hostname_or_ip             # Access a remote system via SSH (replace 'user' and 'hostname_or_ip')
  ssh username@192.168.1.100          # Example with IP address
  ssh -l username hostname_or_ip      # Specify the username explicitly with the `-l` option
  ```
  **Note**: The `-l` option explicitly specifies the username to log in with, which is especially useful when the username differs from your local machine's username.

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
  su username                         # Switch to another user (replace 'username' with the desired user)
  su - username                       # Switch to another user and start a login shell
  ```

- **`exit`** – Exit the current session or log out.
  ```bash
  exit                                # Exit the current user shell session
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
  cd /path/to/directory               # Navigate to a specific directory
  cd ..                               # Go back one directory level
  cd or cd ~                          # Go to the home directory
  ```

- **`ls`** – List the contents of a directory.
  ```bash
  ls                                  # List files in the current directory
  ls -l                               # List with detailed information
  ls -lt                              # List sorted by modification time
  ls -ltr                             # List in reverse order of modification time
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

---

## **Searching for Files and Directories**

### **`find`** – Search for files and directories.

- **Search for a file in the current directory**
  ```bash
  find . -name "file1.txt"            # Search for file1.txt in the current directory (.)
  ```

- **Search for a directory in the current directory**
  ```bash
  find . -type d -name "DirectoryName"  # Search for a directory named "DirectoryName" in the current directory (.)
  ```

- **Search for a file starting from the root directory**
  ```bash
  find / -name "file1.txt"            # Search for file1.txt in the entire file system starting from the root (/)
  ```

- **Search for a directory starting from the root directory**
  ```bash
  find / -type d -name "DirectoryName"  # Search for a directory named "DirectoryName" in the entire file system starting from the root (/)
  ```

### **Note on `.` and `/`**
- **`.` (dot)** refers to the **current directory**. When you use `find .`, it searches within the directory you are currently in.
- **`/` (slash)** refers to the **root directory**. When you use `find /`, it searches the entire file system, starting from the top-level directory.

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
  cd /home/anupmoitra/Documents       # Navigate using an absolute path
  ```

- **Relative Paths**: Start from the current directory.
  ```bash
  cd ../Projects                      # Navigate to the Projects directory in the parent directory
  ```

---

## **Copying Directories**

- **`cp -R`** – Copy directories and their contents recursively.
  ```bash
  cp -R source_directory destination_directory
  cp -R dir1 /home/anupmoitra/dir2     # Copy dir1 to /home/anupmoitra/dir2
  ```

---

### **Note**:
This cheat sheet is designed to provide a quick reference for essential Linux commands that are commonly used in various tasks such as network management, file and directory manipulation, user management, and searching for files.

---
