# **Module 2: System Access and File Management**  
## **Chapter 11: Absolute and Relative Paths**  
![Navigation](https://img.shields.io/badge/Linux-Navigation-yellow)  

---

### **📖 Introduction**  
In Linux, navigating the file system efficiently is key to managing files and directories. This chapter explores the differences between **absolute** and **relative paths** and demonstrates how to use them with the `cd` command.

**What We Will Learn**:  
- The distinction between absolute and relative paths.  
- How to use `cd` to navigate directories using both path types.  
- Commands for verifying the current directory and moving up the directory tree.  

---

### **🛠️ 1. Understanding Absolute and Relative Paths**  

#### **Absolute Path**  
- An **absolute path** always begins with a forward slash `/`, indicating that the path starts from the **root directory**.  
- Example: To navigate directly to the Samba folder in `/var/log/`, use:  
   ```bash
   cd /var/log/samba
   ```  
- This path is fully qualified and independent of your current location in the file system.  

#### **Relative Path**  
- A **relative path** does not start with a slash. It refers to a location relative to your current directory.  
- Example: If you are currently in `/var`, you can navigate to the `logs` directory by using:  
   ```bash
   cd logs
   ```  
- Since `logs` is a subdirectory of `/var`, you don’t need to specify the full path.

#### **Key Differences**  
- **Absolute Path**: Complete path starting from the root directory (`/`).  
- **Relative Path**: Refers to a location relative to the current directory without specifying the root directory.  

#### **Screenshot Example**  
Below is an example of navigating using both absolute and relative paths:

![Navigating with Absolute and Relative Paths](screenshots/01-absolute-relative-paths.png)  
*Figure 1: Example of navigating directories using absolute and relative paths.*

---

### **⌨️ 2. Tab Completion**  

#### **Tab Completion**  
- **What is it?**: Tab completion allows you to automatically complete file and directory names by pressing the `Tab` key.
- **Why use it?**: It reduces the need for typing long file names and prevents typos.

**Example**:  
1. Type `cd /var/lo` and press `Tab`.
2. The terminal will automatically complete it to `cd /var/log/` if the directory exists.

---

### **🔚 Conclusion**  
Mastering absolute and relative paths is essential for effective navigation and management of the Linux file system. By understanding how to use `cd` with both types of paths, you can move around directories quickly and efficiently. Additionally, tab completion will help you reduce typing errors and streamline your workflow.

---
