# Module 3: Linux Fundamentals

## Chapter 3: File Permissions Using Numeric Mode  
![Linux](https://img.shields.io/badge/Linux-Fundamentals-green)  ![chmod](https://img.shields.io/badge/Command-chmod-orange)

---

📘 **In this chapter, we will explore how to assign file and directory permissions using numerical values.** This method is an alternative to the letter-based approach discussed earlier and provides a concise way to define permissions.

---

### 🔢 Numerical Representation of Permissions

Each permission type is represented by a specific numerical value. These values are **added together** to create the numeric mode for each user (owner), group, and others.

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

You add these values together to assign multiple permissions. For example:
- `4` (Read) + `2` (Write) = `6` (Read + Write)
- `4` (Read) + `1` (Execute) = `5` (Read + Execute)

---

### 📂 Structure of Permissions

A file or directory’s permissions are divided into three groups:
1. **👤 User (Owner)**: The first digit in the numeric mode.
2. **👥 Group**: The second digit.
3. **🌍 Others (Everyone else)**: The third digit.

Each digit is the sum of the permission values (Read = 4, Write = 2, Execute = 1). For example, if you want the owner to have `read` and `write` permissions, the numeric value would be **6** (4 for read + 2 for write).

---

### 🛠️ Using `chmod` with Numeric Mode

To assign permissions using numerical values, use the `chmod` command followed by the numeric representation and the file or directory name.

#### 📋 Examples:

**Example 1: Assign `read`, `write`, and `execute` to the owner; `read` and `write` to the group; and `read` to others**

```bash
chmod 764 filename
```

- **7**: `read` (4), `write` (2), and `execute` (1) for the owner.
- **6**: `read` (4) and `write` (2) for the group.
- **4**: `read` (4) for others.

Run `ls -l filename` to verify the permissions:

```
-rwxrw-r-- filename
```

---

**Example 2: Remove all permissions**

```bash
chmod 000 filename
```

- **0**: No permissions for the owner, group, or others.

Run `ls -l filename` to verify the permissions:

```
---------- filename
```

---

**Example 3: Assign `read` and `write` to the owner, and no permissions to group and others**

```bash
chmod 600 filename
```

- **6**: `read` (4) and `write` (2) for the owner.
- **0**: No permissions for the group.
- **0**: No permissions for others.

Run `ls -l filename` to verify the permissions:

```
-rw------- filename
```

---

**Example 4: Assign `read` and `write` to the owner, and `read` to others**

```bash
chmod 604 filename
```

- **6**: `read` (4) and `write` (2) for the owner.
- **0**: No permissions for the group.
- **4**: `read` (4) for others.

Run `ls -l filename` to verify the permissions:

```
-rw----r-- filename
```

---

**Example 5: Assign `execute` to everyone**

```bash
chmod 111 filename
```

- **1**: `execute` (1) for the owner.
- **1**: `execute` (1) for the group.
- **1**: `execute` (1) for others.

Run `ls -l filename` to verify the permissions:

```
--x--x--x filename
```

---

**Example 6: Assign `read` and `execute` to the owner, group, and others**

```bash
chmod 555 filename
```

- **5**: `read` (4) and `execute` (1) for the owner.
- **5**: `read` (4) and `execute` (1) for the group.
- **5**: `read` (4) and `execute` (1) for others.

Run `ls -l filename` to verify the permissions:

```
-r-xr-xr-x filename
```

---

### 🌐 Using Online Tools

If you find it challenging to remember the numerical values, you can use online `chmod` calculators. Simply search for “Linux chmod calculator,” select the desired permissions, and the tool will generate the numeric representation for you. These tools allow you to easily visualize the permission combinations and their corresponding numeric values.

---

### 🗝️ Key Takeaways

- 🔢 The numeric mode provides a concise way to assign permissions using digits.
- 📊 The first digit represents the owner, the second digit represents the group, and the third digit represents others.
- 🎯 Each permission type has a specific numerical value, and you can combine them to assign multiple permissions to each group.
- 🧰 Use tools like `ls -l` to verify changes in permissions.

By understanding both the letter-based and numeric-based approaches, you can efficiently manage permissions on files and directories in Linux.

---
