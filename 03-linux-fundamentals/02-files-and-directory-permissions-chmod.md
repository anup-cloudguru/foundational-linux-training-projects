# **Module 3: Linux Fundamentals**

## **Chapter 2: Files and Directory Permissions (chmod)**

![Linux](https://img.shields.io/badge/Linux-Fundamentals-green) 
![chmod](https://img.shields.io/badge/Command-chmod-orange)

---

### **🔑 Introduction**
In this chapter, we will explore **file permissions** and how to change them using the `chmod` command. Understanding file permissions is crucial for protecting your environment, files, and directories from unauthorized access or accidental deletion. In UNIX-based systems like Linux, which are multi-user environments, every file and directory in your account can be protected or made accessible by changing its access permissions.

---

### **🔍 Types of Permissions**

In UNIX, file and directory permissions are categorized into three main types:

1. **Read (r)**: Allows the user to view the contents of a file.
2. **Write (w)**: Allows the user to modify or delete the contents of a file.
3. **Execute (x)**: Allows the user to run a file, if it's a program or script.

> **💡 Note**: Not all files need the `execute` permission. For instance, if the file is a document or image, execute permissions are unnecessary. However, if it’s a script or program, execute permissions allow it to be run as a program.

---

### **⚙️ Levels of Permissions**

Permissions can be set at three different levels:

- **User (u)**: The owner of the file.
- **Group (g)**: Users who belong to the same group as the file owner.
- **Others (o)**: All other users on the system.

---

### **👀 Viewing File Permissions**

To see the permissions of a file or directory, you can use the `ls -l` command. Here’s an example of what you might see when running `ls -l`:

```bash
$ ls -l
-rw-r--r-- 1 user1 user1 1048576 Dec 17 10:00 example.txt
```

In this output:
- The first column shows the file type and permissions.
  - The first character (`-`) indicates it is a file (a `d` would indicate a directory).
  - The next three characters (`rw-`) indicate that the owner has read and write permissions.
  - The second set of three characters (`r--`) shows that the group has read permission only.
  - The final set (`r--`) shows that others also have read permission.

```plaintext
-rw-r--r--
|  |  |  |
|  |  |  +-- Others: Read
|  |  +----- Group: Read
|  +-------- User: Read & Write
+----------- File Type
```

---

### **🛠️ Changing Permissions with `chmod`**

The **`chmod`** command is used to modify the permissions of files and directories. It works by specifying a permission (read, write, or execute) for the user, group, or others.

#### **Example 1: Removing Write Permission from the Group**

```bash
# Command
chmod g-w example.txt

# Verify the change
ls -l example.txt
```

#### **Example 2: Removing Read Permission for Everyone**

```bash
# Command
chmod a-r example.txt

# Verify the change
ls -l example.txt
```

#### **Example 3: Granting Read and Write Permissions to User and Group**

```bash
# Command
chmod ug+rw example.txt

# Verify the change
ls -l example.txt
```

#### **Example 4: Granting Execute Permission**

To allow a script to be executed, you would add execute (`x`) permission. 

```bash
# Command
chmod u+x script.sh

# Verify the change
ls -l script.sh
```

If you want everyone to be able to execute the file, use:

```bash
chmod a+x script.sh
```

#### **Example 5: Changing Permissions Recursively**

If you want to change the permissions of all files and subdirectories within a directory, you can use the `-R` (recursive) option:

```bash
chmod -R u+rw directory/
```

> **⚠️ Warning**: Use `chmod -R` carefully, as it applies changes to all subdirectories and files.

---

### **📂 Directory Permissions**

The execute permission for directories is particularly important. It allows you to **enter** (i.e., `cd`) into the directory. For example, if a directory has execute permission for the user, you can use `cd` to navigate into it. If not, you will get a **permission denied** message.

#### **Example: Removing Execute Permission from a Directory**

```bash
# Command
chmod a-x projects

# Verify the change
ls -ld projects
```

To restore the permission:

```bash
chmod a+x projects
```

---

### **✅ Verifying Permission Changes**

After making changes to a file or directory’s permissions, always verify by running the `ls -l` command to ensure the changes took effect.

```bash
ls -l example.txt
```

---

### **📖 Summary**

- **Permissions**: Control who can read, write, or execute a file.
- **Levels**: User, group, and others can have different permissions.
- **chmod**: The command used to modify file and directory permissions.
- **`ls -l`**: A command to view permissions and other details of files and directories.

By managing permissions carefully, you can protect your files and directories from unauthorized access or modifications. It is important to understand how permissions work to avoid accidental data loss or exposure.

---

### **📖 Further Reading**
- [Official GNU chmod Documentation](https://www.gnu.org/software/coreutils/manual/html_node/chmod-invocation.html)

---
