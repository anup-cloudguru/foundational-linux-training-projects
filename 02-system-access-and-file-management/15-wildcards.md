# **Module 2: System Access and File Management**  
## **Chapter 15: Wildcards (`*`, `?`, `{}`, `[]`)**  

---

### **What Are Wildcards?**  
Wildcards are special characters in Linux that help you match patterns in filenames or directories. Instead of typing out every file name, you can use wildcards to work with multiple files at once. This makes tasks like searching, listing, copying, or deleting files faster and more efficient.  

---

### **Types of Wildcards and How They Work**  

#### **1. Asterisk (`*`)**  
- **What it does**: Matches **any number of characters** (including none) at **any position** in a filename.  
- Think of it like saying, “Match anything here.”  

- **Examples**:  
  Imagine you have these files:  
  ```  
  ABC123.txt, ABC_Notes.txt, ABC.txt, XYZ_log.txt  
  ```  
  - `ls ABC*`  
    Lists all files starting with “ABC”.  
    **Output**: `ABC123.txt, ABC_Notes.txt, ABC.txt`  

  - `ls *.txt`  
    Lists all `.txt` files.  
    **Output**: `ABC123.txt, ABC_Notes.txt, ABC.txt, XYZ_log.txt`  

  - `ls *log`  
    Lists all files ending with "log".  
    **Output**: `XYZ_log.txt`  

  - `rm ABC*`  
    Deletes all files starting with “ABC”.  
    **Output**: Only `XYZ_log.txt` remains.  

---

#### **2. Question Mark (`?`)**  
- **What it does**: Matches **exactly one character** at a specific position.  
- Think of it like saying, “Match something with one missing piece.”  

- **Examples**:  
  Imagine these files:  
  ```  
  A1.txt, A2.txt, AB.txt, ABC.txt, A123.txt  
  ```  
  - `ls A?.txt`  
    Matches files with **A + one character + .txt**.  
    **Output**: `A1.txt, A2.txt, AB.txt`  

  - `ls A??.txt`  
    Matches files with **A + two characters + .txt**.  
    **Output**: `ABC.txt`  

---

#### **3. Curly Braces (`{}`)**  
- **What it does**: **Not a wildcard**, but a tool for creating patterns in **sequences** or **specific choices**.  
- Think of it like saying, “Match this OR that.”  

- **Examples**:  
  - `touch file{1..10}.txt`  
    Creates 10 files: `file1.txt, file2.txt, ..., file10.txt`.  

  - `ls file{1..3}.txt`  
    Lists files: `file1.txt, file2.txt, file3.txt`.  

  - `touch report_{jan,feb,mar}.txt`  
    Creates: `report_jan.txt, report_feb.txt, report_mar.txt`.  

  - `echo {A,B,C}123`  
    Outputs: `A123, B123, C123`.  

---

#### **4. Square Brackets (`[]`)**  
- **What it does**: Matches **one character from a set or range**.  
- Think of it like saying, “Choose one from this group.”  

- **Examples**:  
  Imagine these files:  
  ```  
  fileA.txt, fileB.txt, fileC.txt, file1.txt, file2.txt  
  ```  
  - `ls file[A-C]*`  
    Matches files starting with "file" followed by **A, B, or C**.  
    **Output**: `fileA.txt, fileB.txt, fileC.txt`  

  - `ls file[1-2]*`  
    Matches files starting with "file" followed by **1 or 2**.  
    **Output**: `file1.txt, file2.txt`  

---

#### **5. Caret (`^`)**  
- **What it does**: Used in **regular expressions** (not wildcards) to mean “starts with”.  
- Think of it like saying, “Match lines that begin with this.”  

- **Examples**:  
  If you have a file `names.txt` with these lines:  
  ```  
  abc123  
  123abc  
  abcdef  
  xyzabc  
  ```  
  - `grep '^abc' names.txt`  
    Finds lines that **start with "abc"**.  
    **Output**:  
    ```  
    abc123  
    abcdef  
    ```  

> **Note**: The caret (`^`) is mainly used in tools like `grep` for searching text inside files and not for matching filenames.  

---

### **Why Wildcards Are Useful**  
- Wildcards save time by letting you work with multiple files at once.  
- You don’t need to type every single file name.  
- They make searching, copying, moving, and deleting files much easier.  

---

### **Quick Summary Table**  

| Wildcard | What It Matches                            | Example               | Output                                      |  
|----------|--------------------------------------------|-----------------------|---------------------------------------------|  
| `*`      | Any number of characters (including none)  | `ls ABC*`            | `ABC123.txt, ABC_Notes.txt, ABC.txt`        |  
| `?`      | Exactly one character                     | `ls A?.txt`          | `A1.txt, A2.txt, AB.txt`                   |  
| `{}`     | A sequence or set of choices              | `echo {A,B,C}123`    | `A123, B123, C123`                         |  
| `[]`     | One character from a set or range         | `ls file[1-2]*`      | `file1.txt, file2.txt`                     |  
| `^`      | Start of a string (for `grep` and search) | `grep '^abc' names`  | Lines starting with "abc" (e.g., `abc123`) |  

---
