# Module 3: Linux Command Basics

## Chapter 3: File Permissions Using Numeric Mode
![Linux](https://img.shields.io/badge/Linux-Fundamentals-green) 
![chmod](https://img.shields.io/badge/Command-chmod-orange)

---

📘 **In this chapter, we will explore how to assign file and directory permissions using numerical values.** This method is an alternative to the letter-based approach discussed earlier and provides a concise way to define permissions.

---

### 🔢 Numerical Representation of Permissions

Each permission type is represented by a specific numerical value:

| Permission Type             | Numerical Value | Symbol  |
|-----------------------------|-----------------|---------|
| ❌ No permission             | 0               | ---     |
| 🏃 Execute                   | 1               | --x     |
| ✍️ Write                     | 2               | -w-     |
| ✍️➕🏃 Write + Execute         | 3               | -wx     |
| 📖 Read                      | 4               | r--     |
| 📖➕🏃 Read + Execute          | 5               | r-x     |
| 📖➕✍️ Read + Write            | 6               | rw-     |
| 📖➕✍️➕🏃 Read + Write + Execute | 7               | rwx     |

In this table:
- `---` means no permission.
- `--x` means only execute permission.
- `-w-` means only write permission.
- `-wx` means write and execute permissions.
- `r--` means read permission.
- `r-x` means read and execute permissions.
- `rw-` means read and write permissions.
- `rwx` means read, write, and execute permissions.

---

### 📂 Structure of Permissions

A file or directory’s permissions are divided into three groups:

1. **👤 User (Owner)** - The first digit in the numeric mode.
2. **👥 Group** - The second digit.
3. **🌍 Others (Everyone else)** - The third digit.

---

### 🛠️ Using `chmod` with Numeric Mode

To assign permissions using numerical values, use the `chmod` command followed by the numeric representation and the file or directory name.

#### 📋 Examples:

**Example 1: Assign `read`, `write`, and `execute` to the owner; `read` and `write` to the group; and `read` to others**

```bash
chmod 764 filename
```

- **7**: `read`, `write`, and `execute` for the owner.
- **6**: `read` and `write` for the group.
- **4**: `read` for others.

Run `ls -l filename` to verify the permissions. You should see:

```
-rwxrw-r-- filename
```

---

**Example 2: Remove all permissions**

```bash
chmod 000 filename
```

- ❌ No permissions for the owner, group, or others.

Run `ls -l filename` to verify the permissions:

```
---------- filename
```

---

**Example 3: Assign `read` and `write` to the owner, and no permissions to group and others**

```bash
chmod 600 filename
```

- **6**: `read` and `write` for the owner.
- **0**: ❌ No permissions for the group.
- **0**: ❌ No permissions for others.

Run `ls -l filename` to verify the permissions:

```
-rw------- filename
```

---

**Example 4: Assign `read` and `write` to the owner, and `read` to others**

```bash
chmod 604 filename
```

- **6**: `read` and `write` for the owner.
- **0**: ❌ No permissions for the group.
- **4**: `read` for others.

Run `ls -l filename` to verify the permissions:

```
-rw----r-- filename
```

---

**Example 5: Assign `execute` to everyone**

```bash
chmod 111 filename
```

- **1**: `execute` for the owner.
- **1**: `execute` for the group.
- **1**: `execute` for others.

Run `ls -l filename` to verify the permissions:

```
--x--x--x filename
```

---

**Example 6: Assign `read` and `execute` to the owner, group, and others**

```bash
chmod 555 filename
```

- **5**: `read` and `execute` for the owner.
- **5**: `read` and `execute` for the group.
- **5**: `read` and `execute` for others.

Run `ls -l filename` to verify the permissions:

```
-r-xr-xr-x filename
```

---

### 🌐 Using Online Tools

If you find it challenging to remember the numerical values, you can use online `chmod` calculators. Simply search for “Linux chmod calculator,” select the desired permissions, and the tool will generate the numeric representation for you.

---

### 🗝️ Key Takeaways

- 🔢 The numeric mode provides a concise way to assign permissions.
- 📊 The first digit represents the owner, the second digit represents the group, and the third digit represents others.
- 🎯 Each permission type has a specific numerical value, which can be combined to assign multiple permissions.
- 🧰 Use tools like `ls -l` to verify changes in permissions.

By understanding both the letter-based and numeric-based approaches, you can efficiently manage permissions on files and directories in Linux.

---
