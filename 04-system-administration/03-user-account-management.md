# Module 4: Linux Command Line Tools

## Chapter 3: User Account Management

![Linux](https://img.shields.io/badge/Linux-Command--Line-blue) ![User](https://img.shields.io/badge/User-Management-orange)

---

### **🔑 Introduction**

User account management is a crucial aspect of Linux system administration. This chapter covers fundamental commands for managing user accounts and groups in Linux, as well as the system files where user and group information is stored.

---

### **🔍 Commands for User and Group Management**

#### **1. Creating a User**

Use the `useradd` command to create a new user:
```bash
useradd <username>
```
Example:
```bash
useradd spiderman
```
This creates a new user `spiderman` with a unique User ID (UID) and Group ID (GID), a corresponding group, and an entry in `/etc/passwd`.

#### **2. Verifying a User**

Check if a user exists using the `id` command:
```bash
id <username>
```
Example:
```bash
id spiderman
```
This displays the UID, GID, and group memberships of the user.

#### **3. Creating a Group**

Create a new group with the `groupadd` command:
```bash
groupadd <groupname>
```
Example:
```bash
groupadd superheroes
```
Verify the group’s creation:
```bash
cat /etc/group | grep <groupname>
```

#### **4. Adding a User to a Group**

Add a user to an existing group using `usermod` with the `-aG` option:
```bash
usermod -aG <groupname> <username>
```
Example:
```bash
usermod -aG superheroes spiderman
```
Verify the user’s group membership:
```bash
cat /etc/group | grep <username>
```

#### **5. Deleting a User**

Remove a user with the `userdel` command:
```bash
userdel <username>
```
To delete the user’s home directory:
```bash
userdel -r <username>
```
Example:
```bash
userdel -r spiderman
```

#### **6. Deleting a Group**

Remove a group with the `groupdel` command:
```bash
groupdel <groupname>
```
Example:
```bash
groupdel superheroes
```

---

### **📂 System Files for User and Group Management**

#### **1. `/etc/passwd`**

This file contains information about user accounts. Each line includes fields like:
- Username
- Password placeholder (`x` for encrypted password in `/etc/shadow`)
- UID and GID
- User description
- Home directory path
- Default shell

To view a specific user’s details:
```bash
grep <username> /etc/passwd
```

#### **2. `/etc/group`**

This file contains group information. Each line includes:
- Group name
- Encrypted group password
- GID
- List of users in the group

To view a specific group’s details:
```bash
grep <groupname> /etc/group
```

#### **3. `/etc/shadow`**

This file stores encrypted passwords and password-related settings, such as expiration and minimum/maximum age.

To view a specific user’s password details:
```bash
grep <username> /etc/shadow
```

---

### **⚙️ Advanced User Management with `usermod`**

The `usermod` command allows modification of existing user accounts. Common options include:

- **`-aG`**: Add the user to supplementary groups.
- **`-c`**: Add or modify the user’s description.
- **`-d`**: Change the user’s home directory.
- **`-s`**: Change the user’s default shell.

Example:
```bash
usermod -aG superheroes spiderman
```

---

### **🛠️ Creating a User with All Parameters**

Use the `useradd` command to create a user with specific parameters:
```bash
useradd -g <groupname> -s <shell> -c <description> -m -d <home_directory> <username>
```
Example:
```bash
useradd -g superheroes -s /bin/bash -c "Iron Man" -m -d /home/ironman ironman
```
This command:
- Assigns the user to the `superheroes` group.
- Sets the shell to `/bin/bash`.
- Adds a description ("Iron Man").
- Creates a home directory `/home/ironman`.

Set a password for the user:
```bash
passwd <username>
```
Example:
```bash
passwd ironman
```

---

### **✅ Key Takeaways**

- Linux provides commands like `useradd`, `usermod`, `userdel`, `groupadd`, and `groupdel` for user and group management.
- Critical system files include `/etc/passwd`, `/etc/group`, and `/etc/shadow`.
- Combining these commands with file inspection ensures secure and organized system administration.

---

### **📖 Exercises**

1. Create a user named `thor` with a home directory `/home/thor` and assign them to a group named `avengers`.
2. Verify the user and group details using the `id` and `cat` commands.
3. Delete the user `thor` and the group `avengers`.
4. Create a user named `blackwidow` with the description "Black Widow" and set a password for the user.

---
