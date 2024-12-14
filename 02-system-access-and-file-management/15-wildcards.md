# **Module 2: System Access and File Management**  
## **Chapter 15: Wildcards (`*`, `?`, `^`, `[]`)**

### **Overview**
In Linux, wildcards are special characters used to match one or more characters in filenames or directories. Wildcards help you search for files, manage them efficiently, and execute commands on multiple files at once. This chapter introduces the basic wildcard characters used in Linux, including the asterisk (`*`), question mark (`?`), caret (`^`), and square brackets (`[]`).

### **Key Wildcards**

#### **1. Asterisk (`*`)**
- **What it does**:  
  The `*` wildcard matches **any number of characters** (including zero characters). Think of it as saying, "I don't care what's after this."

- **Examples**:  
  Imagine you have files like:
  ```
  ABC123.txt, ABC_Notes.txt, ABC.txt, XYZ.txt
  ```
  1. `ls ABC*`  
     - This will list all files starting with "ABC".  
     - **Output**: `ABC123.txt, ABC_Notes.txt, ABC.txt`

  2. `rm ABC*`  
     - This will delete all files starting with "ABC".  
     - After running this, only `XYZ.txt` will remain.

#### **2. Question Mark (`?`)**
- **What it does**:  
  The `?` wildcard matches **exactly one character**. It doesn't care what that one character is, but there must be one.

- **Examples**:  
  Imagine these files:
  ```
  A1.txt, A2.txt, AB.txt, ABC.txt, A123.txt
  ```
  1. `ls A?.txt`  
     - This matches files with **A + one character + .txt**.  
     - **Output**: `A1.txt, A2.txt, AB.txt`

  2. `ls A??.txt`  
     - This matches files with **A + two characters + .txt**.  
     - **Output**: `ABC.txt`

#### **3. Curly Braces (`{}`)**
- **What it does**:  
  Curly braces `{}` are used for creating patterns in a **sequence** or for **specific choices**.

- **Examples**:
  1. `touch file{1..10}.txt`  
     - Creates files: `file1.txt, file2.txt, file3.txt, ..., file10.txt`.

  2. `ls file{1..3}.txt`  
     - Lists files: `file1.txt, file2.txt, file3.txt`.

  3. `echo {A,B,C}123`  
     - Outputs: `A123, B123, C123`.

  4. `touch report_{jan,feb,mar}.txt`  
     - Creates files: `report_jan.txt, report_feb.txt, report_mar.txt`.

#### 4. **Caret (`^`)**
   - **Description**: The caret is often used in regular expressions to denote the start of a string. In the context of filename matching, it's less commonly used directly.
   - **Usage Example**:  
     - In the command `grep '^abc'`, the caret ensures that the line starts with "abc".
   - This wildcard is primarily used in regular expressions rather than direct filename matching.

#### 5. **Square Brackets (`[]`)**
   - **Description**: Square brackets are used to match one character from a set or range of characters.
   - **Usage Example**:  
     - `ls file[A-C]*` – This command lists all files starting with "file" followed by any of the letters A, B, or C.
     - `ls file[0-9]*` – This command lists all files starting with "file" followed by a digit.

### **Practical Examples**
In this section, we will demonstrate how to use these wildcards to perform efficient file operations.

#### 1. **Creating Multiple Files Using Wildcards**
To create multiple files with similar naming conventions, you can use the curly brace expansion along with the wildcard.
   - **Command**:  
     ```bash
     touch ABC{1..9}.txt XYZ{1..9}.txt
     ```
   - This creates nine files: `ABC1.txt`, `ABC2.txt`, ..., `ABC9.txt` and `XYZ1.txt`, `XYZ2.txt`, ..., `XYZ9.txt`.

#### 2. **Listing Files Using Asterisk**
   - **Command**:  
     ```bash
     ls ABC*
     ```
   - This lists all files starting with "ABC". For example, it will list `ABC1.txt`, `ABC2.txt`, etc.

#### 3. **Removing Files Using Asterisk**
   - **Command**:  
     ```bash
     rm ABC*
     ```
   - This removes all files starting with "ABC". The asterisk helps you avoid removing files one by one.

#### 4. **Using Question Mark for Single Character Match**
   - **Command**:  
     ```bash
     ls A?C*
     ```
   - This lists all files that start with "A", followed by exactly one character, and then "C". For example, it will list `A1C.txt` or `ABC.txt`.

#### 5. **Using Brackets for Character Range**
   - **Command**:  
     ```bash
     ls file[A-C]*.txt
     ```
   - This lists all files starting with "file" followed by any of the letters A, B, or C.

#### 6. **Removing Files Matching a Specific Pattern**
   - **Command**:  
     ```bash
     rm *XYZ*.txt
     ```
   - This removes all files that have "XYZ" in the filename.

### **Why Wildcards Are Useful**
Wildcards are incredibly useful when you need to:
- Search for specific files without knowing the exact names.
- Remove multiple files without typing them one by one.
- Perform batch operations on groups of files based on naming patterns.

Using wildcards enhances your productivity as a system administrator and helps in managing large numbers of files efficiently.

### **Conclusion**
In this chapter, you've learned how to use wildcards in Linux for file manipulation. Wildcards can help you save time by enabling batch operations, such as listing, creating, or deleting multiple files at once.

### **Next Steps**
Try using wildcards with different commands such as `cp`, `mv`, and `find`. Practice with your own files to get familiar with their usage. Wildcards are a powerful tool in Linux and will help you become more efficient in system administration tasks.

---

### **Resources**
- [Linux Wildcard Documentation](https://linux.die.net/man/7/glob)  
- [Learn More About Wildcards in Bash](https://tldp.org/LDP/abs/html/globbingref.html)

---
