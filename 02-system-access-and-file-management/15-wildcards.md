# **Module 2: System Access and File Management**  
## **Chapter 15: Wildcards (`*`, `?`, `{}`, `[]`)**

### **What Are Wildcards?**  
Wildcards are special characters in Linux that act like "shortcuts" to match patterns in filenames or directories. Instead of typing out every file name, you can use wildcards to work with multiple files at once. This makes tasks like searching, listing, copying, or deleting files much faster.

---

### **Types of Wildcards and How They Work**

#### **1. Asterisk (`*`)**
- **What it does**: Matches **any number of characters** (including none).  
  Think of it like saying, "I don't care what's here – match everything."

- **Examples**:  
  Imagine you have these files:
  ```
  ABC123.txt, ABC_Notes.txt, ABC.txt, XYZ.txt
  ```
  - `ls ABC*`  
    This lists all files starting with "ABC".  
    **Output**: `ABC123.txt, ABC_Notes.txt, ABC.txt`

  - `rm ABC*`  
    This deletes all files starting with "ABC".  
    **Output**: Only `XYZ.txt` remains.

---

#### **2. Question Mark (`?`)**
- **What it does**: Matches **exactly one character**.  
  Think of it as saying, "Match something with one missing piece."

- **Examples**:  
  Imagine these files:
  ```
  A1.txt, A2.txt, AB.txt, ABC.txt, A123.txt
  ```
  - `ls A?.txt`  
    This matches files with **A + one character + .txt**.  
    **Output**: `A1.txt, A2.txt, AB.txt`

  - `ls A??.txt`  
    This matches files with **A + two characters + .txt**.  
    **Output**: `ABC.txt`

---

#### **3. Curly Braces (`{}`)**
- **What it does**: Used for creating patterns in **sequences** or **specific choices**.  
  Think of it like saying, "Match this OR that."

- **Examples**:  
  - `touch file{1..10}.txt`  
    This creates 10 files:  
    `file1.txt, file2.txt, file3.txt, ..., file10.txt`

  - `ls file{1..3}.txt`  
    This lists files:  
    `file1.txt, file2.txt, file3.txt`

  - `touch report_{jan,feb,mar}.txt`  
    This creates:  
    `report_jan.txt, report_feb.txt, report_mar.txt`

  - `echo {A,B,C}123`  
    This outputs:  
    `A123, B123, C123`

---

#### **4. Square Brackets (`[]`)**
- **What it does**: Matches **one character from a set or range**.  
  Think of it like saying, "Choose one from this group."

- **Examples**:  
  Imagine you have these files:
  ```
  fileA.txt, fileB.txt, fileC.txt, file1.txt, file2.txt
  ```
  - `ls file[A-C]*`  
    This matches files starting with "file" and followed by **A, B, or C**.  
    **Output**: `fileA.txt, fileB.txt, fileC.txt`

  - `ls file[1-2]*`  
    This matches files starting with "file" and followed by **1 or 2**.  
    **Output**: `file1.txt, file2.txt`

---

#### **5. Caret (`^`)**
- **What it does**: Used in **regular expressions** (not file matching) to mean "starts with."  
  Think of it like saying, "Match things that begin with this."

- **Examples**:  
  If you have a file `names.txt` with these lines:  
  ```
  abc123  
  123abc  
  abcdef  
  xyzabc
  ```
  - `grep '^abc' names.txt`  
    This finds lines that **start with "abc"**.  
    **Output**:  
    ```
    abc123  
    abcdef
    ```

> **Note**: The caret (`^`) is primarily used in tools like `grep` for searching inside files, not for matching filenames.

---

### **Why Wildcards Are Useful**
- They save time when working with lots of files.
- You don’t need to type every single file name.
- They make searching, copying, and deleting files much easier.

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
