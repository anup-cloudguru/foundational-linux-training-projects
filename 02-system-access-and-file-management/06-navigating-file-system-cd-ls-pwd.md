# **Module 2: System Access and File Management**

## **Chapter 6: Navigating the File System (cd, ls, pwd)**

### **Introduction**  
In this chapter, we will explore the basic Linux commands for navigating the file system:  
- **`cd`**: Used to change the current directory.  
- **`pwd`**: Prints the full path of the current working directory.  
- **`ls`**: Lists the contents of a directory.  

Mastering these commands will help you efficiently move between directories, locate files, and explore the Linux file system structure.  

---

#### **1.1 `pwd`: Print Working Directory**  
The `pwd` command displays the full path of your current location in the file system. It helps confirm which directory you are currently working in.  

**Example Command**:  
```bash
pwd
```  

**Example Output** (Text Output):  
```
/home/anupmoitra
```

**Example Screenshot** (Terminal Output):  
![Output of pwd](screenshots/01-output-of-pwd.png)  
*Figure 1: Displaying the current directory using `pwd`.*

---

#### **1.2 `cd`: Change Directory**  
The `cd` command is used to navigate between directories.  

**Common Usage Examples**:  
- **Navigate to a specific directory**:  
  ```bash
  cd /etc
  ```  
- **Go back one directory level**:  
  ```bash
  cd ..
  ```  
- **Return to the home directory**:  
  ```bash
  cd ~
  ```

---

#### **1.3 `ls`: List Directory Contents**  
The `ls` command lists the contents of a directory. It supports various options to display additional details.  

**Common Options**:  
- **`ls`**: Lists files and directories.  
- **`ls -l`**: Displays detailed information such as file permissions, ownership, and size.  
- **`ls -a`**: Includes hidden files in the output.  

**Example Command**:  
```bash
ls -l /var/log
```

**Example Output**:  
```
-rw-r--r--  1 root root  1234 Dec 04  2024 syslog
drwxr-xr-x  2 root root  4096 Dec 03  2024 apache2
```

---

### **2. Practical Demonstration**

#### **Step 1: Identify Your Current Location**  
1. Open the terminal.  
2. Run the `pwd` command to verify your current working directory.  

#### **Step 2: Navigate Between Directories**  
1. Use the `cd` command to switch to a specific directory, such as `/var/log`.  
2. Use `cd ..` to move up one level in the directory tree.  

#### **Step 3: Explore Directory Contents**  
1. Run `ls` to list files in your current directory.  
2. Experiment with options like `ls -l` and `ls -a` for additional details.

---

### **3. Importance of Navigation Commands**  
- **Efficiency**: Quickly move between directories and locate files.  
- **Clarity**: Always know your current location within the file system.  
- **Flexibility**: Combine navigation and listing commands for seamless exploration of the Linux environment.  

---

### **Screenshots**  

#### **1. Output of `pwd`**  
![Output of pwd](screenshots/06-output-of-pwd.png)  
*Figure 1: Displaying the current directory using `pwd`.*

#### **2. Navigating to `/var/log` with `cd`**  
![Navigating to /var/log](screenshots/06-navigating-to-var-log.png)  
*Figure 2: Changing to the `/var/log` directory using `cd`.*

#### **3. Listing Contents of `/var/log` with `ls -l`**  
![Listing /var/log](screenshots/06-listing-var-log.png)  
*Figure 3: Viewing detailed contents of the `/var/log` directory using `ls -l`.*

---

## **Conclusion**  
By mastering `cd`, `pwd`, and `ls`, you can efficiently navigate and explore the Linux file system. These commands form the foundation of system administration and file management tasks in Linux environments.  

---
