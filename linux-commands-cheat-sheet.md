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

## 🖥️ **User Information**

### **`whoami`** – Show the Current Logged-in User  
After logging into the system, use `whoami` to confirm which user you're logged in as.

```bash
whoami                       # Displays the current logged-in user
```

---

## 🧹 **Terminal Management**

### **`clear`** – Clear the Terminal Screen  
Use this command to clear all the previous commands and output from the terminal screen.

```bash
clear                       # Clears the terminal screen
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

## 📂 **Copying Files and Directories**

### **`cp`** – Copy Files  
Use this command to copy files from one location to another.

```bash
cp source_file destination_file               # Copy a file to a new location
cp source_file /path/to/destination_directory # Copy a file into a directory
```

### **`cp -R`** – Copy Directories and Their Contents  
Use the `-R` (recursive) option to copy a directory along with all its files and subdirectories.

```bash
cp -R source_directory destination_directory  # Copy a directory and its entire contents
```

### **`cp`** with Multiple Files  
You can also copy multiple files into a directory.

```bash
cp file1 file2 file3 /path/to/destination_directory # Copy multiple files into a directory
```

---

## ✏️ **Renaming Files and Directories**

### **`mv`** – Rename Files or Directories  
The `mv` command is used to rename files or directories. Essentially, it moves the source file or directory to the destination with a new name.

#### **Usage:**

- Rename a file:
  ```bash
  mv old_filename new_filename
  ```

- Rename a directory:
  ```bash
  mv old_directory_name new_directory_name
  ```

- Move and rename simultaneously:
  ```bash
  mv file_or_directory /new/path/new_name
  ```

---

## 📂 **Copying Files and Directories**

### **`cp` – Copy Files**  
Use this command to copy files from one location to another.  

```bash
cp source_file destination_file               # Copy a file to a new location  
cp source_file /path/to/destination_directory # Copy a file into a directory  
```  

### **`cp -R` – Copy Directories and Their Contents**  
Use the `-R` (recursive) option to copy a directory along with all its files and subdirectories.  

```bash
cp -R source_directory destination_directory  # Copy a directory and its entire contents  
```  

### **Copy Multiple Files**  
You can also copy multiple files into a directory.  

```bash
cp file1 file2 file3 /path/to/destination_directory # Copy multiple files into a directory  
```  

---

## 📂 **Renaming Files and Directories**

### **`mv` – Rename or Move Files and Directories**  
The `mv` command can be used to rename files or directories by specifying the new name as the destination.  

```bash
mv old_file_name new_file_name                # Rename a file  
mv old_directory_name new_directory_name      # Rename a directory  
```  

---

## 📂 **Adding Text to Files Using Redirects**

### **`>` – Overwrite File Content**  
Writes or overwrites text to a file.  

```bash
echo "Linux is powerful." > file.txt          # Overwrites file content  
```  

### **`>>` – Append Text to a File**  
Adds new content to an existing file without overwriting.  

```bash
echo "It powers servers." >> file.txt         # Appends content to the file  
```  

### **Redirect Command Outputs to Files**  

#### **Overwrite Command Output**  
Save the output of a command to a file (overwrites the file content).  

```bash
ls -ltr > directory_listing.txt               # Save command output to a file  
```  

#### **Append Command Output**  
Add the output of a command to an existing file without overwriting.  

```bash
date >> directory_listing.txt                 # Append the current date to the file  
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

### 1️⃣ **`chown` Command** 

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

### 2️⃣ **`chgrp` Command** 

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

## 🔑 **Key Commands for ACL (Access Control List)** 

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

## 🔄 **Input and Output Redirection**

### **`>`** – Redirect Standard Output to a File  
Use this command to redirect the output of a command to a file, overwriting its contents.

```bash
command > file             # Redirect standard output to a file, overwriting its contents
ls -l > output.txt         # Save the output of `ls -l` into `output.txt`, overwriting if exists
```

### **`>>`** – Append Standard Output to a File  
Use the `>>` operator to append the output of a command to a file without overwriting its existing contents.

```bash
command >> file            # Append standard output to a file
ls -la >> output.txt       # Append the output of `ls -la` to `output.txt`
```

### **`<`** – Redirect Standard Input from a File  
Use this command to feed a file's contents as input to a command.

```bash
command < file             # Feed input from a file to a command
cat < output.txt           # Display the contents of `output.txt` using `cat`
```

### **`2>`** – Redirect Standard Error to a File  
Use `2>` to redirect error messages (stderr) to a file.

```bash
command 2> file            # Redirect standard error to a file
ls /invalidpath 2> error.txt # Save error messages to `error.txt`
```

### **`2>&1`** – Combine Standard Output and Standard Error  
Use this command to combine both standard output (stdout) and standard error (stderr) into a single stream, usually redirected to a file.

```bash
command > file 2>&1        # Combine stdout and stderr, redirecting both to a file
ls -l /root > combined.txt 2>&1 # Save both output and errors to `combined.txt`
```

---

## 🔄 **Redirecting and Viewing Output with `tee`**

### **`tee`** – Simultaneously Display and Save Output  
The `tee` command allows you to display the output of a command on the terminal while saving it to a file. By default, it overwrites the content of the file, but it can also append output using the `-a` option.

```bash
command | tee filename               # Display and save output to a file
command | tee -a filename            # Append output to an existing file
command | tee file1 file2            # Save output to multiple files
```

#### **Examples**:
- **View and Save Output**:  
   ```bash
   echo "Learning Linux is fun!" | tee output.txt
   ```
   Displays: `Learning Linux is fun!`  
   Saves the output to `output.txt`.

- **Append to a File**:  
   ```bash
   echo "This is appended text." | tee -a output.txt
   ```
   Adds `This is appended text.` to the existing `output.txt`.

- **Capture Output of a Command**:  
   ```bash
   ls -l | tee directory-listing.txt
   ```
   Displays the directory listing on the terminal and saves it to `directory-listing.txt`.

- **Save to Multiple Files**:  
   ```bash
   echo "Linux is powerful!" | tee linux1.txt linux2.txt
   ```
   Saves the same output to both `linux1.txt` and `linux2.txt`.

---

## 🔄 **Using `more`, `tail`, and `head` with Pipes**

### **`more`** – View Output One Page at a Time  
The `more` command allows you to view large outputs one page at a time. It’s particularly useful when the output from a command exceeds the size of the terminal window.

```bash
command | more               # Display output one page at a time
```

#### **Examples**:
- **View Long Directory Listings**:  
   ```bash
   ls -l | more
   ```
   Displays the output of `ls -l` one page at a time.

- **View Detailed Directory Listings**:  
   ```bash
   ll | more
   ```
   Displays the detailed directory listing (`ll` is an alias for `ls -l` in many Linux systems) one page at a time.


### **`tail`** – View the Last Part of the Output  
The `tail` command displays the last part of the output, typically useful for viewing the end of files, logs, or outputs from long-running processes.

```bash
command | tail               # Display the last 10 lines (default)
command | tail -n 20         # Display the last 20 lines
```

#### **Examples**:
- **View the Last 10 Entries of a Directory Listing**:  
   ```bash
   ls -l | tail
   ```
   Displays the last 10 lines of the directory listing.

- **View the Last 20 Entries of a Detailed Directory Listing**:  
   ```bash
   ll | tail -n 20
   ```
   Displays the last 20 lines of the detailed directory listing.


### **`head`** – View the First Part of the Output  
The `head` command displays the first part of the output, typically useful when you want to view the initial lines of files or command results.

```bash
command | head               # Display the first 10 lines (default)
command | head -n 5          # Display the first 5 lines
```

#### **Examples**:
- **View the First 10 Entries of a Directory Listing**:  
   ```bash
   ls -l | head
   ```
   Displays the first 10 lines of the directory listing.

- **View the First 5 Entries of a Detailed Directory Listing**:  
   ```bash
   ll | head -n 5
   ```
   Displays the first 5 lines of the detailed directory listing.


### **Combining `more`, `tail`, and `head` with Pipes**

You can combine these commands with pipes to view and manipulate outputs in more specific ways.

#### **Examples**:
- **View the First 20 Entries of a Directory Listing, Then Scroll Through the Rest**:  
   ```bash
   ls -l | head -n 20 | more
   ```
   Displays the first 20 lines of the directory listing and allows you to scroll through the rest.

- **View the Last 10 Entries and Pipe to `more` for Scrolling**:  
   ```bash
   ls -l | tail | more
   ```
   Displays the last 10 lines of the directory listing and allows you to scroll through the output.

---

## 🔄 **Using the `cut` Command (Text Processors)**

### **`cut` Command** - Extract Sections of Text from Files

#### **Purpose:**  
The `cut` command is used to extract sections from each line of a file or input based on delimiters, positions, or characters. It's widely used for processing columns in text files or output.

#### **Syntax:**

```bash
cut -<option> <file>
```

#### **Common Options:**
- `-f <field>`: Select the specific field or column to cut (based on delimiters).
- `-d <delimiter>`: Specify the delimiter for column separation (default is tab).
- `-c <characters>`: Specify the character positions to extract.

#### **Examples:**

##### **Extract the First Column from a CSV File:**

```bash
cut -d ',' -f 1 data.csv
```
**Output:**
```
Name
John
Jane
...
```

##### **Extract the First 10 Characters of Each Line:**

```bash
cut -c 1-10 filename.txt
```
**Output:**
```
First 10 characters from each line
```

---

### **🔧 `vi` Editor Quick Reference**  

#### **Modes**  
- **Command Mode**: Default mode for actions (e.g., saving, quitting). Press `Esc` to enter.  
- **Insert Mode**: For editing text. Press `i` to enter.  

#### **Basic Commands**  
- **Open a File**:  
  ```bash
  vi filename
  ```  

- **Save and Exit**:  
  - Save changes and exit: `:wq`  
  - Save without exiting: `:w`  
  - Exit without saving: `:q!`  

#### **Navigation**  
- **Move Cursor**:  
  - Left: `h`  
  - Right: `l`  
  - Up: `k`  
  - Down: `j`  
- **Start of line**: `0`  
- **End of line**: `$`  

#### **Editing**  
- **Delete**:  
  - Character: `x`  
  - Line: `dd`  
  - From cursor to end of line: `d$`  
- **Copy & Paste**:  
  - Copy line: `yy`  
  - Paste after cursor: `p`  
  - Paste before cursor: `P`  

#### **Search**  
- **Search forward**: `/pattern`  
- **Search backward**: `?pattern`  
- **Repeat search**:  
  - Forward: `n`  
  - Backward: `N`  

#### **Undo & Redo**  
- Undo: `u`  
- Redo: `Ctrl + r`  

---

### **🔄 Using the `sed` Command (Stream Editor)**

#### **Purpose**  
The `sed` command performs text transformations like search-and-replace, deletion, and insertion on files or streams.

---

#### **Basic Syntax**  
```bash
sed 'command' file.txt
```

---

#### **Key Commands**
1. **Substitute (`s`)**: Replace text.  
   ```bash
   sed 's/old/new/' file.txt      # Replace first match in each line  
   sed 's/old/new/g' file.txt     # Replace all matches in each line
   ```

2. **Delete Lines (`d`)**: Remove lines matching a pattern.  
   ```bash
   sed '/pattern/d' file.txt
   ```

3. **Print (`p`)**: Print matching lines (with `-n`).  
   ```bash
   sed -n '/pattern/p' file.txt
   ```

4. **Insert (`i`)**: Add text before a matching line.  
   ```bash
   sed '/pattern/i\New Text' file.txt
   ```

5. **Append (`a`)**: Add text after a matching line.  
   ```bash
   sed '/pattern/a\New Text' file.txt
   ```

---

#### **Quick Examples**
- **Replace "foo" with "bar":**  
  ```bash
  sed 's/foo/bar/' file.txt
  ```

- **Delete lines containing "ERROR":**  
  ```bash
  sed '/ERROR/d' file.txt
  ```

- **Print lines with "Linux":**  
  ```bash
  sed -n '/Linux/p' file.txt
  ```

- **Extract lines 5 to 10:**  
  ```bash
  sed -n '5,10p' file.txt
  ```

---
