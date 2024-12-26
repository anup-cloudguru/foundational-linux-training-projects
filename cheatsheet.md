# **🐧 Beginner's Guide to Linux Commands** 🔨

---

## **🔧 Basic Network Commands**

- **`ip a`** (or **`ip addr`**) – View your network interfaces and IP addresses.  
  These commands show details about your computer's network connections.
  ```bash
  ip a              # Displays network details (short form)
  ip addr           # Displays network details (full form)
  ```

- **`ifconfig`** – (Old command, still works) View your network interfaces and IP addresses.  
  This command is being replaced by `ip` on modern systems.
  ```bash
  ifconfig          # Displays network details
  ```

- **`hostname -I`** – Show all IP addresses of your system.  
  Use this to quickly see all network addresses assigned to your computer.
  ```bash
  hostname -I       # Displays system IP addresses
  ```

---

## **🔐 Accessing Linux via SSH** 🌐

- **`ssh`** – Secure Shell to access remote systems.  
  Use this command to securely connect to another computer over a network. You’ll need the remote system’s IP address or hostname.
  ```bash
  ssh user@hostname_or_ip           # Access a remote system via SSH
  ssh -l username hostname_or_ip    # Specify the username explicitly
  ```

---

## **⎸️ Interrupt a Running Command or Process**

- **`Ctrl + C`** – Stop a running command or process.  
  If you accidentally run a command that takes too long or gets stuck, press `Ctrl + C` to regain control of the terminal.
  ```bash
  # Press Ctrl + C to stop a running process
  ```

---

## **📁 Navigating the File System**

- **`pwd`** – Print the current working directory.  
  This shows the full path of the directory you’re currently in.
  ```bash
  pwd
  ```

- **`cd`** – Change the current directory.  
  Navigate through folders in the file system using these commands:
  ```bash
  cd /path/to/directory             # Go to a specific directory
  cd ..                             # Go back one directory level
  cd                                # Go to the home directory
  cd /                              # Go to the root directory
  ```

- **`ls`** – List the contents of a directory.  
  View files and directories in your current location:
  ```bash
  ls                                # Basic list of files
  ls -l                             # Detailed listing
  ls -lt                            # Sort by modification time
  ls -ltr                           # Reverse order of modification time
  ```

---

## **📄 Creating and Editing Files**

### **Creating Empty Files**
- **`touch`** – Create a blank file.
  ```bash
  touch filename
  ```

- **`echo`** – Create a blank file.
  ```bash
  echo "" > filename
  ```

### **Adding Content to Files**
- **`echo`** – Create a file with content.
  ```bash
  echo "Hello, World!" > filename
  ```

- **`cat`** – Write or view file content.
  ```bash
  cat > filename                    # Write content to a file (Ctrl + D to save)
  cat filename                      # View content of a file
  cat >> filename                   # Append content to an existing file
  ```

### **Editing Files Directly**
- **`nano`** – Beginner-friendly text editor.
  ```bash
  nano filename                     # Open a file in Nano editor
  ```

- **`vi`** / **`vim`** – Advanced text editors.
  ```bash
  vi filename                       # Open a file in Vi editor
  vim filename                      # Open a file in Vim editor
  ```

---

## **🔑 Changing User Passwords**

- **`passwd`** – Change user passwords.  
  Use this command to update your password or reset another user's password (requires `sudo` for other users).
  ```bash
  passwd                            # Update your own password
  sudo passwd username              # Update another user's password
  ```

---

## **📂 Copying Directories**

- **`cp -R`** – Copy directories and their contents.  
  Use the `-R` option to copy a directory along with all its files and subdirectories.
  ```bash
  cp -R source_directory destination_directory
  ```

### **Example**:  
To copy the `dir1` directory to `/home/user/dir2`:
```bash
cp -R dir1 /home/user/dir2
```

---

## **🔍 Finding Files and Directories**

### **Using the `find` Command**
- **Syntax**:
  ```bash
  find [path] [expression]
  ```
  - **`path`**: Directory to start the search (e.g., `.` for the current directory).
  - **`expression`**: Search criteria (e.g., `-name`).

- **Examples**:
  ```bash
  find . -name "filename"           # Search for a file by name
  find /path/to/search -type d -name "dirname"   # Search for a directory
  sudo find / -name "filename"      # Search from the root directory
  ```

### **Using the `locate` Command**
- **Syntax**:
  ```bash
  locate filename
  ```

- **Examples**:
  ```bash
  locate filename                   # Quickly search for a file
  sudo updatedb                     # Update the database for accurate results
  ```

### **Key Differences: `find` vs `locate`**
| Feature                | `find`                         | `locate`                   |
|------------------------|---------------------------------|----------------------------|
| **Speed**              | Real-time, slower             | Faster (uses a database)   |
| **Customization**      | Highly flexible search criteria| Limited to filenames       |
| **Database Required**  | No                            | Yes                        |
| **Requires Update**    | No                            | Yes (with `updatedb`)      |

---

## **🌟 Wildcards in Linux**

Wildcards help match patterns in filenames and simplify tasks like searching, copying, and deleting files.

### **Types of Wildcards**

- **`*` (Asterisk)** – Matches any number of characters.
  ```bash
  ls ABC*       # Lists files starting with "ABC"
  rm ABC*       # Deletes files starting with "ABC"
  ```

- **`?` (Question Mark)** – Matches exactly one character.
  ```bash
  ls A?.txt     # Matches files like A1.txt, A2.txt
  ```

- **`{}` (Curly Braces)** – Creates sequences or multiple options.
  ```bash
  touch file{1..5}.txt     # Creates file1.txt to file5.txt
  ```

- **`[]` (Square Brackets)** – Matches one character from a set.
  ```bash
  ls file[A-C]*   # Matches fileA.txt, fileB.txt, fileC.txt
  ```

---

## **🔗 Soft Links and Hard Links**  

### **Soft Links (Symbolic Links)**  
- **`ln -s`** – Create a symbolic (soft) link to a file or directory.  
  If the source file is deleted or renamed, the soft link breaks.
  ```bash
  ln -s <source_file> <link_name>    # Create a soft link
  ```

- **`ls -li`** – View the inode information for files and links. The soft link will show a different inode than the source file.
  ```bash
  ls -li                             # View the inode and details of files and links
  ```

- **`cat`** – View the content of the file or link. If the source file is deleted, the soft link will result in an error.
  ```bash
  cat <link_name>                    # View content of the soft link
  ```

### **Hard Links**  
- **`ln`** – Create a hard link to a file. Both the source file and the hard link share the same inode.
  ```bash
  ln <source_file> <link_name>       # Create a hard link
  ```

- **`ls -li`** – View the inode information for files and links. Both the source file and the hard link will have the same inode number.
  ```bash
  ls -li                             # View inode of the hard link (same as source file)
  ```

- **`cat`** – View the content of the hard link. The content remains accessible even if the original file is deleted.
  ```bash
  cat <link_name>                    # View content of the hard link
  ```
  
---

## **chmod Command - File and Directory Permissions**

### **View File Permissions**
- **`ls -l`** – View the permissions and details of files and directories.
  ```bash
  ls -l <file_or_directory>        # View file/directory permissions
  ```

### **Change Permissions with `chmod`**
- **`chmod g-w`** – Remove write permission from the group.
  ```bash
  chmod g-w <file_name>            # Remove write permission from the group
  ```

- **`chmod a-r`** – Remove read permission for everyone (user, group, others).
  ```bash
  chmod a-r <file_name>            # Remove read permission for everyone
  ```

- **`chmod ug+rw`** – Grant read and write permissions to user and group.
  ```bash
  chmod ug+rw <file_name>          # Grant read and write permissions to user and group
  ```

- **`chmod u+x`** – Grant execute permission to the user.
  ```bash
  chmod u+x <file_name>            # Grant execute permission to user
  ```

- **`chmod a+x`** – Grant execute permission to everyone (user, group, others).
  ```bash
  chmod a+x <file_name>            # Grant execute permission to everyone
  ```

- **`chmod -R u+rw`** – Grant read and write permissions recursively to all files and subdirectories within a directory.
  ```bash
  chmod -R u+rw <directory_name>   # Grant read and write permissions recursively
  ```

### **Directory Permissions**
- **`chmod a-x`** – Remove execute permission from a directory (prevents `cd` into the directory).
  ```bash
  chmod a-x <directory_name>       # Remove execute permission from a directory
  ```

- **`chmod a+x`** – Restore execute permission for a directory.
  ```bash
  chmod a+x <directory_name>       # Restore execute permission for a directory
  ```
  
---

## **chmod Command - File Permissions Using Numeric Mode**

### **Understanding Numeric Mode**
- **Permission Types**: 
  - **No Permission**: `0` (`---`)
  - **Execute**: `1` (`--x`)
  - **Write**: `2` (`-w-`)
  - **Write + Execute**: `3` (`-wx`)
  - **Read**: `4` (`r--`)
  - **Read + Execute**: `5` (`r-x`)
  - **Read + Write**: `6` (`rw-`)
  - **Read + Write + Execute**: `7` (`rwx`)

### **Structure of Numeric Permissions**
- **User (Owner)**: First digit
- **Group**: Second digit
- **Others (Everyone)**: Third digit
- **Formula**: Add values for the desired permissions (e.g., Read = 4, Write = 2, Execute = 1)

### **Examples:**

- **Assign `rwx` to owner, `rw` to group, and `r` to others**:
  ```bash
  chmod 764 filename
  ```
  - **Owner**: `rwx` = `7`
  - **Group**: `rw-` = `6`
  - **Others**: `r--` = `4`
  - **Output**: `-rwxrw-r-- filename`

- **Remove all permissions**:
  ```bash
  chmod 000 filename
  ```
  - **Owner, Group, Others**: `---` = `0`
  - **Output**: `---------- filename`

- **Assign `rw` to the owner, and no permissions to group and others**:
  ```bash
  chmod 600 filename
  ```
  - **Owner**: `rw-` = `6`
  - **Group, Others**: `---` = `0`
  - **Output**: `-rw------- filename`

- **Assign `rw` to owner, and `r` to others**:
  ```bash
  chmod 604 filename
  ```
  - **Owner**: `rw-` = `6`
  - **Group**: `---` = `0`
  - **Others**: `r--` = `4`
  - **Output**: `-rw----r-- filename`

- **Assign `execute` to everyone**:
  ```bash
  chmod 111 filename
  ```
  - **Owner, Group, Others**: `--x` = `1`
  - **Output**: `--x--x--x filename`

- **Assign `r-x` to owner, group, and others**:
  ```bash
  chmod 555 filename
  ```
  - **Owner**: `r-x` = `5`
  - **Group**: `r-x` = `5`
  - **Others**: `r-x` = `5`
  - **Output**: `-r-xr-xr-x filename`

### **Using Online Tools**
- Use online **`chmod` calculators** to generate numeric values for desired permissions.
- These tools visualize the permission combinations and their corresponding numeric values.

---

## **chown and chgrp Commands - Managing File Ownership**

### **1️⃣ `chown` Command**
- **Purpose**: Change the **owner** (and optionally the **group**) of a file or directory.
- **Syntax**:  
  ```bash
  chown [OPTION] OWNER[:GROUP] FILE
  ```
  - **OWNER**: The new owner.
  - **GROUP** (Optional): The new group.
  - **FILE**: The file or directory.

- **Common Options**:
  - `-R`: Apply changes recursively.
  - `-v`: Verbose output.

#### **Examples**:
- **Change both owner and group**:
  ```bash
  chown -v user1:group1 filename
  ```
  Output:
  ```
  changed ownership of 'filename' from user2:group2 to user1:group1
  ```

- **Change only the owner**:
  ```bash
  chown -v user1 filename
  ```
  Output:
  ```
  changed ownership of 'filename' from user2 to user1
  ```

- **Change only the group**:
  ```bash
  chown -v :group1 filename
  ```
  Output:
  ```
  changed group of 'filename' from group2 to group1
  ```

- **Recursively change ownership**:
  ```bash
  chown -R user1:group1 /path/to/directory
  ```

---

### **2️⃣ `chgrp` Command**
- **Purpose**: Change the **group** ownership of a file or directory.
- **Syntax**:  
  ```bash
  chgrp [OPTION] GROUP FILE
  ```
  - **GROUP**: The new group.
  - **FILE**: The file or directory.

- **Common Options**:
  - `-R`: Apply changes recursively.
  - `-v`: Verbose output.

#### **Examples**:
- **Change group ownership**:
  ```bash
  chgrp -v group1 filename
  ```
  Output:
  ```
  changed group of 'filename' from group2 to group1
  ```

- **Recursively change group ownership**:
  ```bash
  chgrp -v -R group1 /path/to/directory
  ```
  Output:
  ```
  changed group of '/path/to/directory/file1' from group2 to group1
  ```

- **Change group ownership for multiple files**:
  ```bash
  chgrp -v group1 file1 file2 file3
  ```
  Output:
  ```
  changed group of 'file1' from group2 to group1
  ```

---

### **📚 Verifying Ownership Changes**
- Use `ls -l` to verify ownership:
  ```bash
  ls -l filename
  ```
  Output:
  ```
  -rw-r--r-- 1 user1 group1 1234 Dec 22 12:00 filename
  ```
  - `user1` is the owner, `group1` is the group.

---

### **🔄 Combining Commands, Options, and Arguments**
- Use `chown` and `chgrp` with options to modify ownership recursively or make changes efficiently.
  
---

### **💡 Key Points**
- **`chown`**: Changes **owner** and optionally the **group**.
- **`chgrp`**: Changes the **group** only.
- **Only root or users with elevated privileges** can use `chown`.
- **Regular users** can use `chgrp` if they own the file and belong to the target group.
- **Use the `-R` option** to apply changes recursively.
- **Verify with `ls -l`** to confirm changes.

---

### **🔍 Additional Tips**
- **Using `sudo`**: For non-root users with administrative privileges, prepend `sudo` to execute commands:
  ```bash
  sudo chown user1:group1 filename
  ```

- **Manual Pages**: Use `man` to learn more about `chown` and `chgrp` options:
  ```bash
  man chown
  man chgrp
  ```

---
