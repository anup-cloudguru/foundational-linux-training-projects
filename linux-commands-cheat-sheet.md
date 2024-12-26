# 🐧 **Beginner's Guide to Linux Commands**

---

## 🔧 **Basic Network Commands**

### **`ip a`** or **`ip addr`** – View Your Network Interfaces & IP Addresses
A modern command to check your network details.

```bash
ip a              # Short form for network details
ip addr           # Full form for network details
```

### **`ifconfig`** – (Legacy Command) View Your Network Interfaces & IP Addresses  
Though older, `ifconfig` still works but is being replaced by `ip` on modern systems.

```bash
ifconfig          # Legacy command to show network details
```

### **`hostname -I`** – Show All IP Addresses of Your System  
Quickly see all the IP addresses assigned to your system.

```bash
hostname -I       # Displays all system IP addresses
```

---

## 🔐 **Accessing Linux via SSH**

### **`ssh`** – Secure Shell to Access Remote Systems  
Use this command to securely connect to another computer over a network. You’ll need the remote system’s IP address or hostname.

```bash
ssh user@hostname_or_ip           # Access a remote system via SSH
ssh -l username hostname_or_ip    # Specify the username explicitly
```

---

## ⏰ **Power Management** 
### **`sudo shutdown`** – Schedule or Perform System Shutdown
Use this command to schedule or immediately shut down the system.

```bash
sudo shutdown                      # Schedules shutdown 1 minute from now (default)
sudo shutdown +10                  # Schedules shutdown in 10 minutes
sudo shutdown 23:00                # Schedules shutdown at 11:00 PM
sudo shutdown now                  # Shut down the system immediately
sudo shutdown -c                   # Cancel a scheduled shutdown
```

### **`sudo reboot`** – Schedule or Perform System Reboot
Use this command to reboot the system immediately or schedule a reboot.

```bash
sudo reboot                         # Reboot immediately
sudo shutdown -r +10                # Schedule a reboot in 10 minutes
sudo shutdown -r 23:00              # Schedule a reboot at 11:00 PM
```

---

## ⎸️ **Interrupt a Running Command or Process**

### **`Ctrl + C`** – Stop a Running Command or Process  
If you accidentally run a command that takes too long or gets stuck, press `Ctrl + C` to regain control of the terminal.

```bash
# Press Ctrl + C to stop a running process
```

---

## 📁 **Navigating the File System**

### **`pwd`** – Print the Current Working Directory  
This shows the full path of the directory you’re currently in.

```bash
pwd
```


### **`cd`** – Change the Current Directory  
Navigate through folders in the file system using these commands:

```bash
cd /path/to/directory             # Go to a specific directory
cd ..                             # Go back one directory level
cd                                # Go to the home directory
cd /                              # Go to the root directory
```

### **`ls`** – List the Contents of a Directory  
View files and directories in your current location:

```bash
ls                                # Basic list of files
ls -l                             # Detailed listing
ls -lt                            # Sort by modification time
ls -ltr                           # Reverse order of modification time
```

---

## 📄 **Creating and Editing Files**

### **Creating Empty Files**

#### **`touch`** – Create a Blank File  
Use this command to create an empty file.

```bash
touch filename                     # Create an empty file
```


#### **`echo`** – Create a Blank File  
Another way to create a blank file using `echo`.

```bash
echo "" > filename                 # Create a blank file
```

### **Adding Content to Files**

#### **`echo`** – Create a File with Content  
Use this command to create a file and add content at the same time.

```bash
echo "Hello, World!" > filename    # Create a file with content
```

#### **`cat`** – Write or View File Content  
Use `cat` to write content to a file or view its content.

```bash
cat > filename                     # Write content to a file (Ctrl + D to save)
cat filename                       # View content of a file
cat >> filename                    # Append content to an existing file
```

### **Editing Files Directly**

#### **`nano`** – Beginner-Friendly Text Editor  
A simple text editor for beginners.

```bash
nano filename                      # Open a file in Nano editor
```

#### **`vi` / `vim`** – Advanced Text Editors  
`vi` and `vim` are powerful text editors for advanced users.

```bash
vi filename                        # Open a file in Vi editor
vim filename                       # Open a file in Vim editor
```

---

## 🔑 **Changing User Passwords**

### **`passwd`** – Change User Passwords  
Use this command to update your password or reset another user's password (requires `sudo` for other users).

```bash
passwd                             # Update your own password
sudo passwd username               # Update another user's password
```

---

## 📂 **Copying Directories**

### **`cp -R`** – Copy Directories and Their Contents  
Use the `-R` option to copy a directory along with all its files and subdirectories.

```bash
cp -R source_directory destination_directory   # Copy a directory and its contents
```

---

## 🔍 **Finding Files and Directories**

### **Using the `find` Command**  
The `find` command allows you to search for files and directories based on various criteria.

#### **Syntax:**

```bash
find [path] [expression]
```

- `path`: Directory to start the search (e.g., `.` for the current directory).
- `expression`: Search criteria (e.g., `-name`).

#### **Examples:**

```bash
find . -name "filename"             # Search for a file by name
find /path/to/search -type d -name "dirname"   # Search for a directory
sudo find / -name "filename"        # Search from the root directory
```

### **Using the `locate` Command**  
The `locate` command quickly searches for a file by referencing a pre-built database.

#### **Syntax:**

```bash
locate filename
```

#### **Examples:**

```bash
locate filename                     # Quickly search for a file
sudo updatedb                       # Update the database for accurate results
```

### **Key Differences: `find` vs `locate`**

| Feature              | `find`                              | `locate`                        |
|----------------------|-------------------------------------|---------------------------------|
| **Speed**            | Real-time, slower                   | Faster (uses a database)        |
| **Customization**    | Highly flexible search criteria     | Limited to filenames            |
| **Database Required**| No                                  | Yes                             |
| **Requires Update**  | No                                  | Yes (with `updatedb`)           |

---

## 🌟 **Wildcards in Linux**

Wildcards help match patterns in filenames and simplify tasks like searching, copying, and deleting files.

### **Types of Wildcards**

#### **`*` (Asterisk)** – Matches Any Number of Characters  
Use the asterisk to match any sequence of characters.

```bash
ls ABC*       # Lists files starting with "ABC"
rm ABC*       # Deletes files starting with "ABC"
```


#### **`?` (Question Mark)** – Matches Exactly One Character  
Use the question mark to match a single character.

```bash
ls A?.txt     # Matches files like A1.txt, A2.txt
```


#### **`{}` (Curly Braces)** – Creates Sequences or Multiple Options  
Use curly braces to create a sequence of files or specify multiple options.

```bash
touch file{1..5}.txt     # Creates file1.txt to file5.txt
```


#### **`[]` (Square Brackets)** – Matches One Character from a Set  
Use square brackets to match one character from a specified set.

```bash
ls file[A-C]*   # Matches fileA.txt, fileB.txt, fileC.txt
```

---

## 🔗 **Soft Links and Hard Links**

### **Soft Links (Symbolic Links)**

#### **`ln -s`** – Create a Symbolic (Soft) Link to a File or Directory  
A soft link is a reference to another file. If the source file is deleted or renamed, the soft link will break.

```bash
ln -s <source_file> <link_name>    # Create a soft link
```

#### **`ls -li`** – View Inode Information for Files and Links  
Use this command to view the inode details of the source file and the soft link. The soft link will show a different inode than the source file.

```bash
ls -li                             # View inode and details of files and links
```

#### **`cat`** – View the Content of the File or Link  
If the source file is deleted, the soft link will result in an error when you try to view its content.

```bash
cat <link_name>                    # View content of the soft link
```

### **Hard Links**

#### **`ln`** – Create a Hard Link to a File  
Both the source file and the hard link share the same inode. The content remains accessible even if the original file is deleted.

```bash
ln <source_file> <link_name>       # Create a hard link
```

#### **`ls -li`** – View Inode Information for Files and Links  
Both the source file and the hard link will have the same inode number.

```bash
ls -li                             # View inode of the hard link (same as source file)
```

#### **`cat`** – View the Content of the Hard Link  
The content of the hard link remains accessible even if the original file is deleted.

```bash
cat <link_name>                    # View content of the hard link
```

---

## 🛠️ **`chmod` Command - File and Directory Permissions**️

### **View File Permissions**

#### **`ls -l`** – View the Permissions and Details of Files and Directories  
Use this command to view the file permissions and additional details.

```bash
ls -l <file_or_directory>        # View file/directory permissions
```

### **Change Permissions with `chmod`**

#### **`chmod g-w`** – Remove Write Permission from the Group  
Use this command to remove write permission from the group.

```bash
chmod g-w <file_name>            # Remove write permission from the group
```

#### **`chmod a-r`** – Remove Read Permission for Everyone  
This removes read permission for the user, group, and others.

```bash
chmod a-r <file_name>            # Remove read permission for everyone
```

#### **`chmod ug+rw`** – Grant Read and Write Permissions to User and Group  
This command grants read and write permissions to both the user and the group.

```bash
chmod ug+rw <file_name>          # Grant read and write permissions to user and group
```

#### **`chmod u+x`** – Grant Execute Permission to the User  
Use this command to grant execute permission to the user.

```bash
chmod u+x <file_name>            # Grant execute permission to user
```

#### **`chmod a+x`** – Grant Execute Permission to Everyone  
This command grants execute permission to the user, group, and others.

```bash
chmod a+x <file_name>            # Grant execute permission to everyone
```

#### **`chmod -R u+rw`** – Grant Read and Write Permissions Recursively  
Grant read and write permissions to all files and subdirectories within a directory.

```bash
chmod -R u+rw <directory_name>   # Grant read and write permissions recursively
```

### **Directory Permissions**

#### **`chmod a-x`** – Remove Execute Permission from a Directory  
This prevents anyone from using `cd` to enter the directory.

```bash
chmod a-x <directory_name>       # Remove execute permission from a directory
```

#### **`chmod a+x`** – Restore Execute Permission for a Directory  
Restores the execute permission so that users can `cd` into the directory.

```bash
chmod a+x <directory_name>       # Restore execute permission for a directory
```

---

## 🔢 **chmod Command - File Permissions Using Numeric Mode**

### **Understanding Numeric Mode**

#### **Permission Types:**

- **No Permission:** `0` (---)
- **Execute:** `1` (--x)
- **Write:** `2` (-w-)
- **Write + Execute:** `3` (-wx)
- **Read:** `4` (r--)
- **Read + Execute:** `5` (r-x)
- **Read + Write:** `6` (rw-)
- **Read + Write + Execute:** `7` (rwx)

### **Structure of Numeric Permissions**

- **User (Owner):** First digit
- **Group:** Second digit
- **Others (Everyone):** Third digit

#### **Formula:**  
Add values for the desired permissions (e.g., Read = 4, Write = 2, Execute = 1)

### **Examples:**

#### **Assign `rwx` to Owner, `rw` to Group, and `r` to Others:**

```bash
chmod 764 filename
```
- **Owner:** `rwx = 7`
- **Group:** `rw- = 6`
- **Others:** `r-- = 4`
- **Output:** `-rwxrw-r-- filename`

#### **Remove All Permissions:**

```bash
chmod 000 filename
```
- **Owner, Group, Others:** `--- = 0`
- **Output:** `---------- filename`

#### **Assign `rw` to the Owner, and No Permissions to Group and Others:**

```bash
chmod 600 filename
```
- **Owner:** `rw- = 6`
- **Group, Others:** `--- = 0`
- **Output:** `-rw------- filename`

#### **Assign `rw` to Owner, and `r` to Others:**

```bash
chmod 604 filename
```
- **Owner:** `rw- = 6`
- **Group:** `--- = 0`
- **Others:** `r-- = 4`
- **Output:** `-rw----r-- filename`

#### **Assign Execute to Everyone:**

```bash
chmod 111 filename
```
- **Owner, Group, Others:** `--x = 1`
- **Output:** `--x--x--x filename`

#### **Assign `r-x` to Owner, Group, and Others:**

```bash
chmod 555 filename
```
- **Owner:** `r-x = 5`
- **Group:** `r-x = 5`
- **Others:** `r-x = 5`
- **Output:** `-r-xr-xr-x filename`

### **Using Online Tools**

You can use online `chmod` calculators to generate numeric values for desired permissions.  
These tools visualize the permission combinations and their corresponding numeric values, making it easier to understand and set the correct permissions.

---

## 👥 **`chown` and `chgrp` Commands - Managing File Ownership**️

### 1️⃣ **`chown` Command** 🛠️

#### **Purpose:**  
Change the owner (and optionally the group) of a file or directory.

#### **Syntax:**

```bash
chown [OPTION] OWNER[:GROUP] FILE
```
- **OWNER:** The new owner.
- **GROUP (Optional):** The new group.
- **FILE:** The file or directory.

#### **Common Options:**
- **-R:** Apply changes recursively.
- **-v:** Verbose output.

#### **Examples:**

##### **Change both owner and group:**

```bash
chown -v user1:group1 filename
```
**Output:**  
`changed ownership of 'filename' from user2:group2 to user1:group1`

##### **Change only the owner:**

```bash
chown -v user1 filename
```
**Output:**  
`changed ownership of 'filename' from user2 to user1`

##### **Change only the group:**

```bash
chown -v :group1 filename
```
**Output:**  
`changed group of 'filename' from group2 to group1`

##### **Recursively change ownership:**

```bash
chown -R user1:group1 /path/to/directory
```

### 2️⃣ **`chgrp` Command** 🔑

#### **Purpose:**  
Change the group ownership of a file or directory.

#### **Syntax:**

```bash
chgrp [OPTION] GROUP FILE
```
- **GROUP:** The new group.
- **FILE:** The file or directory.

#### **Common Options:**
- **-R:** Apply changes recursively.
- **-v:** Verbose output.

#### **Examples:**

##### **Change group ownership:**

```bash
chgrp -v group1 filename
```
**Output:**  
`changed group of 'filename' from group2 to group1`

##### **Recursively change group ownership:**

```bash
chgrp -v -R group1 /path/to/directory
```
**Output:**  
`changed group of '/path/to/directory/file1' from group2 to group1`

##### **Change group ownership for multiple files:**

```bash
chgrp -v group1 file1 file2 file3
```
**Output:**  
`changed group of 'file1' from group2 to group1`

### 📚 **Verifying Ownership Changes**

Use `ls -l` to verify ownership:

```bash
ls -l filename
```
**Output:**

```bash
-rw-r--r-- 1 user1 group1 1234 Dec 22 12:00 filename
```
- **user1** is the owner.
- **group1** is the group.

### 🔄 **Combining Commands, Options, and Arguments**

You can use `chown` and `chgrp` with options to modify ownership recursively or make changes efficiently.

### 💡 **Key Points**
- **`chown`:** Changes owner and optionally the group.
- **`chgrp`:** Changes the group only.
- Only **root** or users with **elevated privileges** can use `chown`.
- Regular users can use **`chgrp`** if they own the file and belong to the target group.
- Use the **-R** option to apply changes recursively.
- **Verify changes** with `ls -l`.

### 🔍 **Additional Tips**

#### **Using `sudo`:**
For non-root users with administrative privileges, prepend `sudo` to execute commands:

```bash
sudo chown user1:group1 filename
```

#### **Manual Pages:**
Use `man` to learn more about `chown` and `chgrp` options:

```bash
man chown
man chgrp
```

---

## 🔑 **Key Commands for ACL (Access Control List)** 🛡️

---

### 1️⃣ **`setfacl` Command** - Set or Modify ACL Entries

#### **Purpose:**  
Used to set or modify Access Control List (ACL) entries for files and directories.

#### **Syntax:**

```bash
setfacl [OPTION] ENTRY FILE
```

#### **Examples:**

##### **Grant permissions to a user:**

```bash
setfacl -m u:<username>:<permissions> <file>
```
Example:
```bash
setfacl -m u:user1:rw file.txt
```
This grants **read and write** permissions to `user1` on `file.txt`.

##### **Grant permissions to a group:**

```bash
setfacl -m g:<groupname>:<permissions> <file>
```
Example:
```bash
setfacl -m g:developers:r file.txt
```
This grants **read** permission to the group `developers` on `file.txt`.

##### **Apply permissions recursively to a directory:**

```bash
setfacl -R -m u:<username>:<permissions> <directory>
```
Example:
```bash
setfacl -R -m u:user1:rw /data
```
This grants **read and write** permissions to `user1` for all files in the `/data` directory.

##### **Remove a specific ACL entry:**

```bash
setfacl -x u:<username> <file>
```
Example:
```bash
setfacl -x u:user1 file.txt
```
This **removes** the ACL entry for `user1` on `file.txt`.

##### **Remove all ACL entries:**

```bash
setfacl -b <file>
```
Example:
```bash
setfacl -b file.txt
```
This **removes all ACL entries** from `file.txt`.

##### **Set ACL inheritance for a directory:**

```bash
setfacl -m d:u:<username>:<permissions> <directory>
```
Example:
```bash
setfacl -m d:u:user1:rw /data
```
This **sets default ACLs** for `user1` to **read and write** in the `/data` directory and any new files created inside it.

### 2️⃣ **`getfacl` Command** - View ACL Entries

#### **Purpose:**  
Used to view the ACL entries of a file or directory.

#### **Syntax:**

```bash
getfacl <file>
```

Example:
```bash
getfacl file.txt
```
This shows the **ACL entries** for `file.txt`.

---

## 🆘 **Key Commands for Linux Help**

### 1️⃣ **`whatis` Command** - Provides a One-Line Summary of Commands

#### **Purpose:**  
This command gives a concise, one-line description of the specified command.

#### **Syntax:**

```bash
whatis <command>
```

#### **Examples:**

##### **Get a description of the `ls` command:**

```bash
whatis ls
```
**Output:**
```bash
ls (1)             - list directory contents
```

##### **Get a description of the `cd` command:**

```bash
whatis cd
```
**Output:**
```bash
cd (1p)            - change working directory
cd (bash built-in) - change the shell working directory
```

##### **Get a description of the `pwd` command:**

```bash
whatis pwd
```
**Output:**
```bash
pwd (1)            - print name of current/working directory
```

### 2️⃣ **`help` Command** - Get Help for Built-In Shell Commands

#### **Purpose:**  
The `help` command provides information about built-in shell commands.

#### **Syntax:**

```bash
help <command>
```

#### **Examples:**

##### **Get help for the `cd` command:**

```bash
help cd
```
**Output:**
```bash
cd: cd [dir]
    Change the shell working directory.
    ...
```

##### **Get help for the `exit` command:**

```bash
help exit
```
**Output:**
```bash
exit: exit [n]
    Exit the shell.
    ...
```

### 3️⃣ **`man` Command** - Display Manual Pages for Commands

#### **Purpose:**  
The `man` command shows detailed documentation (manual pages) for commands, including their options, usage, and examples.

#### **Syntax:**

```bash
man <command>
```

#### **Examples:**

##### **View the manual page for the `ls` command:**

```bash
man ls
```
This opens a detailed manual with information about the `ls` command, including all available options.

##### **View the manual page for the `chmod` command:**

```bash
man chmod
```
This displays detailed documentation on changing file permissions with `chmod`.

### 🗂️ **Comparison of `whatis`, `help`, and `man`**

| **Command** | **Purpose**                                   | **Level of Detail**      | **Use Case**                              |
|-------------|-----------------------------------------------|--------------------------|-------------------------------------------|
| `whatis`    | Provides a one-line description of a command. | Low                      | Quickly check what a command does.        |
| `help`      | Explains built-in shell commands.             | Moderate                 | Learn about specific shell commands.      |
| `man`       | Displays detailed manual pages for commands.  | High                     | Explore full documentation for commands.  |

---
