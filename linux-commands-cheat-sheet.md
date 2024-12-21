# **🐧 Linux Command Cheat Sheet** 🛠️

## **🔧 Network Commands**

- **`ip a`** (or **`ip addr`**) – Display all network interfaces and their IP addresses.
  ```bash
  ip a                                # Shorthand for 'ip addr'
  ip addr                             # Full command, same functionality as 'ip a'
  ```
  **Note**: `ip a` and `ip addr` are interchangeable. Use whichever you prefer.

- **`ifconfig`** – (Deprecated but still works) Display network interfaces and their IP addresses.
  ```bash
  ifconfig                            # Show network interfaces and IP details
  ```

- **`hostname -I`** – Show all IP addresses associated with the system.
  ```bash
  hostname -I                         # Display the IP address of the system
  ```

---

## **🔐 Accessing Linux via SSH** 🌐

- **`ssh`** – Secure Shell to access remote systems.
  ```bash
  ssh user@hostname_or_ip             # Access a remote system via SSH
  ssh -l username hostname_or_ip      # Specify the username explicitly
  ```
  **Note**: Use the `-l` option when the remote username differs from your local username.

---

## **👤 User and Access Management**

- **`whoami`** – Display the current logged-in username.
  ```bash
  whoami
  ```

- **`passwd`** – Change user passwords.
  ```bash
  passwd                              # Change your own password
  sudo passwd username                # Change another user's password (requires sudo)
  ```

- **`su`** – Switch to another user account.
  ```bash
  su username                         # Switch to another user
  su - username                       # Switch and start a login shell
  ```

- **`exit`** – Exit the current session or log out.
  ```bash
  exit                                # Exit the current user shell session
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
  cd /path/to/directory               # Navigate to a specific directory
  cd ..                               # Go back one directory level
  cd or cd ~                          # Go to the home directory
  cd /                                # Go to the root directory
  ```

- **`ls`** – List the contents of a directory.
  ```bash
  ls                                  # List files in the current directory
  ls -l                               # Detailed listing
  ls -lt                              # Sort by modification time
  ls -ltr                             # Reverse order of modification time
  ```

- **`echo`** – Display a string or write text to a file.
  ```bash
  echo "Hello, World!"               # Print "Hello, World!" to the terminal
  echo "Anup is a superhero" > file  # Write text to a file named 'file'
  echo $USER                         # Display the value of the 'USER' variable
  ```

- **`cat`** – Display the content of a file or combine files.
  ```bash
  cat file.txt                       # Show file content
  cat file1.txt file2.txt > combined.txt  # Combine files into one
  cat -n file.txt                    # Display content with line numbers
  ```

---

## **📂 File and Directory Management**

- **`touch`** – Create an empty file.
  ```bash
  touch file1.txt                     # Create a file named file1.txt
  touch file1.txt file2.txt           # Create multiple files at once
  ```

- **`vim`** – Open or create a file using the `vim` editor.
  ```bash
  vim file1.txt                       # Open (or create) file1.txt
  # Press 'Esc', then ':wq' to save and exit
  ```

- **`cp`** – Copy files and directories.
  ```bash
  cp file1.txt file2.txt              # Copy file1.txt to file2.txt
  cp -R dir1 /home/user/dir2          # Copy directory and its contents
  ```

- **`mv`** – Move or rename files and directories.
  ```bash
  mv file1.txt /path/to/destination   # Move file1.txt to a new location
  mv old_dir new_dir                  # Rename a directory
  ```

- **`rm`** – Remove files or directories.
  ```bash
  rm file1.txt                        # Remove a file
  rm -r dir1                          # Remove a directory and its contents
  rm -rf dir1                         # Forcefully remove a directory and its contents
  ```

- **`mkdir`** – Create a new directory.
  ```bash
  mkdir new_directory                 # Create a directory
  mkdir -p parent_dir/sub_dir         # Create nested directories
  ```

- **`clear`** – Clear the terminal screen.
  ```bash
  clear                               # Clears the terminal display
  ```

---

## **🔗 Creating Links**

- **`ln -s`** – Create a soft (symbolic) link.
  ```bash
  ln -s <source_file> <link_name>    # Create a symbolic link to the source file
  ```

- **`ln`** – Create a hard link.
  ```bash
  ln <source_file> <link_name>       # Create a hard link to the source file
  ```

---

## **🛡️ File and Directory Permissions**

- **`chmod`** – Change file or directory permissions.

  | Syntax                    | Description                                           |
  |---------------------------|-------------------------------------------------------|
  | `chmod g-w file.txt`      | Remove write permission from the group               |
  | `chmod a-r file.txt`      | Remove read permission for all users                 |
  | `chmod ug+rw file.txt`    | Add read and write permissions for user and group    |
  | `chmod u+x script.sh`     | Add execute permission for the user to a script      |
  | `chmod a+x script.sh`     | Allow everyone to execute the file                   |
  | `chmod -R u+rw directory` | Recursively add read and write permissions for user  |

- **Permission Levels**:
  - **User (u)**: The owner of the file.
  - **Group (g)**: Users belonging to the same group as the file owner.
  - **Others (o)**: All other users.

- **Permission Types**:
  - **Read (r)**: View file contents.
  - **Write (w)**: Modify or delete a file.
  - **Execute (x)**: Run a file if it’s a script or program.

- **Viewing Permissions**:
  Use `ls -l` to view file permissions:
  ```bash
  $ ls -l
  -rw-r--r-- 1 user1 user1 1048576 Dec 17 10:00 example.txt
  ```

  **Legend**:
  - `-`: File type (e.g., `-` for file, `d` for directory).
  - `rw-`: Permissions for the user (read and write).
  - `r--`: Permissions for the group (read-only).
  - `r--`: Permissions for others (read-only).

---

## **⚡ Wildcard and Pattern Matching**

| Wildcard | Description                              | Example             | Matches                                  |
|----------|------------------------------------------|---------------------|-----------------------------------------|
| `*`      | Matches zero or more characters          | `ls ABC*`           | `ABC123.txt`, `ABC_Notes.txt`, `ABC.txt` |
| `?`      | Matches exactly one character            | `ls A?.txt`         | `A1.txt`, `AB.txt`                     |
| `{}`     | Matches any choice in a comma-separated list | `echo {A,B,C}123`  | `A123`, `B123`, `C123`                 |
| `[]`     | Matches a single character in the set    | `ls file[1-2]*`     | `file1.txt`, `file2.txt`               |

---

## **🔍 Searching for Files and Directories**

- **`find`** – Search for files and directories.
  ```bash
  find . -name "file1.txt"            # Search for a file in the current directory
  find / -type d -name "DirectoryName"  # Search for a directory from the root
  ```

- **`locate`** – Quickly search using an index.
  ```bash
  locate file1.txt                   # Search for a file
  locate -i "filename"               # Case-insensitive search
  ```

- **`updatedb`** – Update the index for `locate`.
  ```bash
  sudo updatedb                      # Refresh the locate database
  ```

---

## **⏰ Power Management**

- **`sudo shutdown`** – Schedule or perform system shutdown.
  ```bash
  sudo shutdown                     # Schedule shutdown 1 minute from now
  sudo shutdown +10                 # Schedule shutdown 10 minute from now
  sudo shutdown 23:00               # Schedule shutdown at 11:00 PM
  sudo shutdown now                 # Shut down the system immediately
  sudo shutdown -c                  # Cancel a scheduled shutdown
  ```

- **`sudo reboot`** – Schedule or perform system reboot.
  ```bash
  sudo reboot                        # Schedules the reboot for 1 minute from now
  sudo reboot +10                    # Schedules the reboot for 10 minute from now
  sudo reboot 23:00                  # Schedules the reboot at 11:00 PM
  sudo reboot now                    # Reboot immediately
  ```

---

### **💡 Note**  

This cheat sheet provides a quick reference for essential Linux commands. Perfect for both beginners and advanced users! 🐧

---
