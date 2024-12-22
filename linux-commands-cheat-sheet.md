# **🐧 Linux Command Cheat Sheet** 🛠️

---

## **🔧 Network Commands**

- **`ip a`** (or **`ip addr`**) – Display all network interfaces and their IP addresses.  
  ```bash
  ip a              # Shorthand for 'ip addr'
  ip addr           # Full command, same functionality as 'ip a'
  ```

- **`ifconfig`** – (Deprecated but still works) Display network interfaces and their IP addresses.  
  ```bash
  ifconfig          # Show network interfaces and IP details
  ```

- **`hostname -I`** – Show all IP addresses associated with the system.  
  ```bash
  hostname -I       # Display the IP address of the system
  ```

---

## **🔐 Accessing Linux via SSH** 🌐

- **`ssh`** – Secure Shell to access remote systems.  
  ```bash
  ssh user@hostname_or_ip           # Access a remote system via SSH
  ssh -l username hostname_or_ip    # Specify the username explicitly
  ```

---

## **👤 User and Access Management**

- **`whoami`** – Display the current logged-in username.  
  ```bash
  whoami
  ```

- **`passwd`** – Change user passwords.  
  ```bash
  passwd                            # Change your own password
  sudo passwd username              # Change another user's password (requires sudo)
  ```

- **`su`** – Switch to another user account.  
  ```bash
  su username                       # Switch to another user
  su - username                     # Switch and start a login shell
  ```

- **`exit`** – Exit the current session or log out.  
  ```bash
  exit                              # Exit the current user shell session
  ```

---

## **⎸️ Interrupt a Running Command or Process**

- **`Ctrl + C`** – Interrupt a running command or process.  
  ```bash
  # Press Ctrl + C to stop a running process
  ```

---

## **📝 Basic Commands**

- **`pwd`** – Print the current working directory.  
  ```bash
  pwd
  ```

- **`cd`** – Change the current directory.  
  ```bash
  cd /path/to/directory             # Navigate to a specific directory
  cd ..                             # Go back one directory level
  cd or cd ~                        # Go to the home directory
  cd /                              # Go to the root directory
  ```

- **`ls`** – List the contents of a directory.  
  ```bash
  ls                                # List files in the current directory
  ls -l                             # Detailed listing
  ls -lt                            # Sort by modification time
  ls -ltr                           # Reverse order of modification time
  ```

- **`echo`** – Display a string or write text to a file.  
  ```bash
  echo "Anup is a superhero" > file.txt  # Write text to a file named 'file'
  ```

- **`cat`** – Display the content of a file or combine files.  
  ```bash
  cat file.txt                            # Show file content
  cat file1.txt file2.txt > combined.txt  # Combine files into one
  cat -n file.txt                         # Display content with line numbers
  ```

---

## **📂 File and Directory Management**

- **`touch`** – Create an empty file.  
  ```bash
  touch file1.txt                       # Create a file named file1.txt
  touch file1.txt file2.txt             # Create multiple files at once
  ```

- **`vim`** – Open or create a file using the `vim` editor.  
  ```bash
  vim file1.txt                         # Open (or create) file1.txt
  # Press 'Esc', then ':wq' to save and exit
  ```

- **`cp`** – Copy files and directories.  
  ```bash
  cp file1.txt file2.txt                # Copy file1.txt to file2.txt
  cp -R dir1 /home/user/dir2            # Copy directory and its contents
  ```

- **`mv`** – Move or rename files and directories.  
  ```bash
  mv file1.txt /path/to/destination     # Move file1.txt to a new location
  mv old_dir new_dir                    # Rename a directory
  ```

- **`rm`** – Remove files or directories.  
  ```bash
  rm file1.txt                          # Remove a file
  rm -r dir1                            # Remove a directory and its contents
  rm -rf dir1                           # Forcefully remove a directory and its contents
  ```

- **`mkdir`** – Create a new directory.  
  ```bash
  mkdir new_directory                   # Create a directory
  mkdir -p parent_dir/sub_dir           # Create nested directories
  ```

- **`clear`** – Clear the terminal screen.  
  ```bash
  clear                                 # Clears the terminal display
  ```

---

## **🔗 Creating Links**

- **`ln -s`** – Create a soft (symbolic) link.  
  ```bash
  ln -s <source_file> <link_name>      # Create a symbolic link to the source file
  ```

- **`ln`** – Create a hard link.  
  ```bash
  ln <source_file> <link_name>         # Create a hard link to the source file
  ```

---

## **🛡️ File and Directory Permissions**

- **`chmod`** – Change file or directory permissions.  
  ```bash
  chmod g-w file.txt                  # Remove write permission from the group
  chmod a-r file.txt                  # Remove read permission for all users
  chmod ug+rw file.txt                # Add read and write permissions for user and group
  chmod u+x script.sh                 # Add execute permission for the user to a script
  chmod a+x script.sh                 # Allow everyone to execute the file
  chmod -R u+rw directory             # Recursively add read and write permissions for user
  ```

  **Permission Levels**:  
  - **User (u)**: The owner of the file.  
  - **Group (g)**: Users belonging to the same group as the file owner.  
  - **Others (o)**: All other users.  

  **Permission Types**:  
  - **Read (r)**: View file contents.  
  - **Write (w)**: Modify or delete a file.  
  - **Execute (x)**: Run a file if it’s a script or program.  

  **Viewing Permissions**:  
  Use `ls -l` to view file permissions:  
  ```bash
  $ ls -l
  -rw-r--r-- 1 user1 user1 1048576 Dec 17 10:00 example.txt
  ```

---

## **🔢 Numeric Mode for File Permissions**

In this mode, permissions are assigned using numbers rather than letters. Each permission type has a numerical value, and you combine them to define permissions for the owner, group, and others.

### **Numerical Representation of Permissions**

| **Permission Type**             | **Numerical Value** | **Symbol** |
|----------------------------------|---------------------|------------|
| **No permission**               | 0                   | ---        |
| **Execute**                     | 1                   | --x        |
| **Write**                       | 2                   | -w-        |
| **Write + Execute**             | 3                   | -wx        |
| **Read**                        | 4                   | r--        |
| **Read + Execute**              | 5                   | r-x        |
| **Read + Write**                | 6                   | rw-        |
| **Read + Write + Execute**      | 7                   | rwx        |

### **Using `chmod` with Numeric Mode**

- **Example 1**: Assign `read`, `write`, and `execute` to the owner; `read` and `write` to the group; and `read` to others:
  ```bash
  chmod 764 filename
  ```

- **Example 2**: Remove all permissions:
  ```bash
  chmod 000 filename
  ```

- **Example 3**: Assign `read` and `write` to the owner, and no permissions to group and others:
  ```bash
  chmod 600 filename
  ```

- **Example 4**: Assign `read` and `write` to the owner, and `read` to others:
  ```bash
  chmod 604 filename
  ```

- **Example 5**: Assign `execute` to everyone:
  ```bash
  chmod 111 filename
  ```

- **Example 6**: Assign `read` and `execute` to the owner, group, and others:
  ```bash
  chmod 555 filename
  ```

---

## **🛠️ File Ownership Commands**

#### **1️⃣ `chown` (Change Owner)**

The **`chown`** command is used to change the owner and optionally the group of a file or directory.

**Syntax**:  
```bash
chown [OPTION] OWNER[:GROUP] FILE
```

- **OWNER**: The new owner of the file or directory.
- **GROUP**: (Optional) The new group for the file or directory.
- **FILE**: The file or directory whose ownership you want to change.

##### **Common Options**:
- **-R**: Recursively apply changes to all files and directories.
- **-v**: Verbose mode, which provides detailed output of the changes.

**Examples**:
- **Change the owner of a file**:
  ```bash
  chown user1 filename
  ```

- **Change both owner and group**:
  ```bash
  chown user1:group1 filename
  ```

- **Recursively change ownership**:
  ```bash
  chown -R user1:group1 /path/to/directory
  ```

---

#### **2️⃣ `chgrp` (Change Group)**

The **`chgrp`** command is used to change the group ownership of a file or directory.

**Syntax**:  
```bash
chgrp [OPTION] GROUP FILE
```

- **GROUP**: The new group for the file or directory.
- **FILE**: The file or directory whose group ownership you want to change.

##### **Common Options**:
- **-R**: Recursively apply changes to all files and directories.
- **-v**: Verbose mode, which provides detailed output of the changes.

**Examples**:
- **Change the group of a file**:
  ```bash
  chgrp group1 filename
  ```

- **Recursively change the group of files**:
  ```bash
  chgrp -R group1 /path/to/directory
  ```

---

## **⏰ Power Management**

- **`sudo shutdown`** – Schedule or perform system shutdown.  
  ```bash
  sudo shutdown                      # Schedules shutdown 1 minute from now (default behavior)
  sudo shutdown +10                  # Schedules shutdown 10 minutes from now
  sudo shutdown 23:00                # Schedules shutdown at 11:00 PM
  sudo shutdown now                  # Shuts down the system immediately
  sudo shutdown -c                   # Cancels a scheduled shutdown
  ```

- **`sudo reboot`** – Schedule or perform system reboot.  
  ```bash
  sudo reboot                         # Reboot immediately
  sudo shutdown -r +10                # Schedule a reboot in 10 minutes
  sudo shutdown -r 23:00              # Schedule a reboot at 11:00 PM
  ```

---

### **💡 Note**  
This cheat sheet provides a quick reference for essential Linux commands. Perfect for both beginners and advanced users! 🐧  

---
