# **Module 3: Linux Fundamentals**

## **Chapter 5: Access Control List (ACL)**

![Linux](https://img.shields.io/badge/Linux-Fundamentals-green) ![ACL](https://img.shields.io/badge/Command-ACL-blue) ![setfacl](https://img.shields.io/badge/Command-setfacl-orange) ![getfacl](https://img.shields.io/badge/Command-getfacl-orange)

---

### **🔑 Introduction**
In this chapter, we will explore **Access Control List (ACL)**, an advanced mechanism to manage permissions for files and directories in Linux. While traditional UNIX permissions limit flexibility, ACL provides a way to define **more granular, user-specific permissions**. By the end of this chapter, you will understand how to set and manage ACL permissions using the commands **`setfacl`** and **`getfacl`**.

---

### **📚 What is ACL?**
ACL stands for **Access Control List**, a feature that:
- Adds an **additional layer of permissions** on top of standard UNIX file permissions.
- Allows assigning specific permissions to **individual users** or **groups** for a file or directory.
- Provides a more **flexible permission mechanism** for managing access rights in Linux.

---

### **🛠 Why Use ACL?**
Standard file permissions are often not enough in scenarios like:
- Granting access to a **single user** without modifying group membership.
- Granting specific permissions to a **particular group** without affecting other groups.
- Managing permissions for **nested directories** with inheritance.

For example:
- If a file is owned by `root` and a user `user1` needs read/write access, ACL allows this **without making `user1` part of the `root` group**.

---

### **1️⃣ Key ACL Commands**
The two primary commands for managing ACLs are:

#### **`setfacl`**
- Used to **set or modify ACL entries**.
- Syntax:
  ```bash
  setfacl [OPTION] ENTRY FILE
  ```

#### **`getfacl`**
- Used to **view ACL entries**.
- Syntax:
  ```bash
  getfacl FILE
  ```

---

### **2️⃣ Setting ACL Permissions**

#### **Granting Permissions to a User**
Use `setfacl` with the `-m` (modify) option:

**Syntax**:
```bash
setfacl -m u:<username>:<permissions> <file>
```

- **`u:<username>`**: Specifies the user.
- **`<permissions>`**: Permissions to grant (`r` for read, `w` for write, `x` for execute).
- **`<file>`**: The target file or directory.

**Example**:
```bash
setfacl -m u:user1:rw file.txt
```
This grants `user1` read and write permissions for `file.txt`.

---

#### **Granting Permissions to a Group**
Use `setfacl` with the `-m` option and specify the group:

**Syntax**:
```bash
setfacl -m g:<groupname>:<permissions> <file>
```

**Example**:
```bash
setfacl -m g:developers:r file.txt
```
This grants the `developers` group read permissions for `file.txt`.

---

#### **Applying Permissions Recursively**
To apply ACLs to all files and subdirectories:

**Syntax**:
```bash
setfacl -R -m u:<username>:<permissions> <directory>
```

**Example**:
```bash
setfacl -R -m u:user1:rw /data
```
This grants `user1` read and write permissions for all files and subdirectories in `/data`.

---

### **3️⃣ Viewing ACL Permissions**
To view existing ACL permissions for a file or directory, use the `getfacl` command:

**Syntax**:
```bash
getfacl <file>
```

**Example**:
```bash
getfacl file.txt
```
**Output**:
```
# file: file.txt
# owner: root
# group: root
user::rw-
user:user1:rw-
group::r--
mask::rw-
other::r--
```
This output shows that:
- `root` (owner) has `rw` (read/write) permissions.
- `user1` has `rw` permissions.
- The `root` group has `r` (read) permissions.

---

### **4️⃣ Removing ACL Permissions**

#### **Removing a Specific ACL Entry**
Use `setfacl` with the `-x` (remove) option:

**Syntax**:
```bash
setfacl -x u:<username> <file>
```

**Example**:
```bash
setfacl -x u:user1 file.txt
```
This removes all ACL entries for `user1` on `file.txt`.

---

#### **Removing All ACL Entries**
To clear all ACL permissions for a file or directory:

**Syntax**:
```bash
setfacl -b <file>
```

**Example**:
```bash
setfacl -b file.txt
```
This removes all ACL permissions for `file.txt` and reverts to default UNIX permissions.

---

### **5️⃣ Inheriting ACLs**
To set ACL inheritance for a directory, use the `-d` (default) option:

**Syntax**:
```bash
setfacl -m d:u:<username>:<permissions> <directory>
```

**Example**:
```bash
setfacl -m d:u:user1:rw /data
```
This ensures that all files created within `/data` will automatically inherit `rw` permissions for `user1`.

---

### **🔍 Key Observations**
1. Files or directories with ACLs have a **`+` sign** at the end of their permission listing:
   ```bash
   ls -l
   -rw-r--r--+ 1 root root 1234 Dec 22 file.txt
   ```
2. **Write Permission Caveat**:
   - ACLs with `w` (write) permission allow modifying a file but **do not allow deleting** it. File deletion is controlled by directory permissions.

---

### **✅ Summary of Key Points**
- **ACLs** provide a flexible way to manage permissions for specific users and groups.
- Use **`setfacl`** to add, modify, or remove ACL entries.
- Use **`getfacl`** to view current ACL entries.
- ACL permissions can be applied recursively or set to inherit.
- Clearing ACLs with `-b` reverts to standard UNIX permissions.

---

### **🐛 Conclusion**
Access Control Lists enhance the Linux permission model by allowing **fine-grained access control**. Mastering ACL commands like **`setfacl`** and **`getfacl`** is essential for managing multi-user environments and securing resources effectively.

**Practice Tip**: Experiment with ACL commands on sample files and directories to understand their behavior, especially inheritance and cascading permissions.

---
