# **Module 3: Linux Command Basics**

## **Chapter 4: File Ownership Commands (chown, chgrp)**  
![Linux](https://img.shields.io/badge/Linux-Fundamentals-green)  
![chown](https://img.shields.io/badge/Command-chown-orange)  
![chgrp](https://img.shields.io/badge/Command-chgrp-orange)

---

📘 In this chapter, we will explore how to change file ownership and group ownership in Linux using the `chown` and `chgrp` commands. This will allow you to manage file access and security more effectively.**

---

### 👤 **Understanding File Ownership**

In Linux, every file or directory is owned by two entities:
1. **User (Owner)**: The individual who created the file.
2. **Group**: A set of users that share permissions for the file.

Ownership is crucial in managing access, and you can change both the **user** and **group** ownerships using the following commands:

---

### 🔑 **The `chown` Command - Changing User Ownership**

The `chown` command changes the **user** ownership of a file or directory.

#### **Syntax**: 
```bash
chown [user][:group] file
```
- **user**: The new owner of the file.
- **group** (optional): The new group for the file.
- **file**: The file or directory to change ownership for.

---

#### 📋 **Examples:**

**Example 1: Change the user to `john` and leave the group as is**  
```bash
chown john filename.txt
```
- This will change the owner of the file `filename.txt` to `john`.

**Example 2: Change both the user and the group to `john` and `admin`**  
```bash
chown john:admin filename.txt
```
- This will change the owner to `john` and the group to `admin`.

**Example 3: Change only the group ownership (leaving the user unchanged)**  
```bash
chown :admin filename.txt
```
- This changes only the group to `admin`, while leaving the user ownership unchanged.

---

### 🧑‍🤝‍🧑 **The `chgrp` Command - Changing Group Ownership**

The `chgrp` command changes the **group** ownership of a file or directory.

#### **Syntax**: 
```bash
chgrp [group] file
```
- **group**: The new group for the file.
- **file**: The file or directory to change group ownership for.

---

#### 📋 **Examples:**

**Example 1: Change the group to `admin`**  
```bash
chgrp admin filename.txt
```
- This will change the group ownership of `filename.txt` to `admin`.

---

### 🔄 **Recursive Ownership Change**

To apply ownership changes to a directory and all its contents, you can use the **recursive** option `-R`.

#### **Syntax**:
```bash
chown -R [user]:[group] directory/
chgrp -R [group] directory/
```

#### 📋 **Example**:

**Example: Change ownership for all files and subdirectories within a directory**  
```bash
chown -R john:admin /home/john/documents/
```
- This will change the user to `john` and the group to `admin` for all files and subdirectories inside `/home/john/documents/`.

---

### 🛠️ **Practical Usage Scenarios**

#### 📂 **Scenario 1: Changing ownership after file transfer**  
You may want to change the owner after transferring files:
```bash
chown newuser file.txt
```
- This changes the file `file.txt` ownership to `newuser`.

#### 👥 **Scenario 2: Changing group ownership for shared access**  
```bash
chgrp developers file.txt
```
- This will change the group ownership of `file.txt` to `developers`.

---

### 📂 **How to Check Ownership**

To check file ownership, you can use the `ls -l` command:
```bash
ls -l filename.txt
```
The output will show the user and group ownership:
```
-rw-r--r-- 1 john developers 0 Dec 22 12:00 filename.txt
```
In this example, the owner is `john` and the group is `developers`.

---

### 🗝️ **Key Takeaways**

- 🔑 The `chown` command is used to change file user and group ownership.
- 🧑‍🤝‍🧑 The `chgrp` command is used to change file group ownership.
- 🔄 The `-R` option allows you to change ownership recursively for directories and their contents.
- 📊 Use `ls -l` to view the current user and group ownership of files and directories.

By mastering these commands, you will have greater control over file access and security in Linux systems.

---
