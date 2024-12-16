# **Module 2: System Access and File Management**  

## **Chapter 15: Wildcards (`*`, `?`, `{}`, `[]`)**

### **What Are Wildcards?**
Wildcards are special characters in Linux that help you match patterns in filenames or directories. Instead of typing out every file name, you can use wildcards to work with many files at once. This makes tasks like searching, listing, copying, or deleting files much faster.

---

### **Types of Wildcards and How They Work**

#### **1. Asterisk (`*`)**
- **What it does**: Matches **any number of characters** (including none). Think of it like saying, "Match everything."

- **Examples**:  
  Imagine you have these files:
  ```
  ABC123.txt, ABC_Notes.txt, ABC.txt, XYZ.txt
  ```
  - `ls ABC*`  
    Lists all files starting with "ABC".  
    **Output**: `ABC123.txt, ABC_Notes.txt, ABC.txt`
  - `ls *`  
    Lists all files in the directory.  
    **Output**: All files in the current directory

  - `rm ABC*`  
    Deletes all files starting with "ABC".  
    **Output**: Only `XYZ.txt` remains.

---

#### **2. Question Mark (`?`)**
- **What it does**: Matches **exactly one character**. Think of it like saying, "Match something with one missing piece."

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

  - `ls "A ?.txt"`  
    Matches files like **A .txt** (one character including space).  
    **Output**: `A1.txt, A .txt`

---

### **Practice Tasks for `?`**

#### **Task 1: List files with exactly one character before `.txt`**
- **Command:**
  ```bash
  ls file?.txt
  ```
- **Outcome:**
  ```
  file1.txt
  file2.txt
  fileA.txt
  fileB.txt
  file_.txt
  ```
- **Explanation:** The `?` matches exactly one character, so `file12.txt` is excluded because it has two characters before `.txt`.

#### **Task 2: List files with two characters in the name**
- **Command:**
  ```bash
  ls ??.txt
  ```
- **Outcome:**
  No output (empty).
- **Explanation:** None of the files match the pattern `??.txt` because all filenames are longer than two characters.

#### **Task 3: List `.log` files with one character after "read"**
- **Command:**
  ```bash
  ls read?.log
  ```
- **Outcome:**
  ```
  read1.log
  read2.log
  readA.log
  ```
- **Explanation:** The `?` matches exactly one character after "read", so it lists all `.log` files with one extra character.

#### **Task 4: Copy `.txt` files with one character before `.txt` to the home directory**
- **Command:**
  ```bash
  cp file?.txt ~/  # Assumes your home directory is /home/<username>
  ```
- **Outcome:**
  Copies the following files to the home directory:
  ```
  file1.txt
  file2.txt
  fileA.txt
  fileB.txt
  file_.txt
  ```
- **Explanation:** The `?` matches exactly one character in filenames, so `file12.txt` is not included.

#### **Task 5: Delete files with one character before `.log`**
- **Command:**
  ```bash
  rm read?.log
  ```
- **Outcome:** Deletes:
  ```
  read1.log
  read2.log
  readA.log
  ```

---

#### **3. Curly Braces (`{}`)**
- **What it does**: Used for creating patterns in **sequences** or **specific choices**. Think of it like saying, "Match this OR that."

- **Examples**:  
  - `touch file{1..10}.txt`  
    Creates 10 files: `file1.txt, file2.txt, file3.txt, ..., file10.txt`

  - `ls file{1..3}.txt`  
    Lists files: `file1.txt, file2.txt, file3.txt`

  - `touch report_{jan,feb,mar}.txt`  
    Creates: `report_jan.txt, report_feb.txt, report_mar.txt`

  - `echo {A,B,C}123`  
    Outputs: `A123, B123, C123`

  - `cp file{1,2}.txt destination/`  
    Copies `file1.txt` and `file2.txt` to the `destination` folder.

---

#### **4. Square Brackets (`[]`)**
- **What it does**: Matches **one character from a set or range**. Think of it like saying, "Choose one from this group."

- **Examples**:  
  Imagine you have these files:
  ```
  fileA.txt, fileB.txt, fileC.txt, file1.txt, file2.txt
  ```
  - `ls file[A-C]*`  
    Matches files starting with "file" followed by **A, B, or C**.  
    **Output**: `fileA.txt, fileB.txt, fileC.txt`

  - `ls file[1-2]*`  
    Matches files starting with "file" followed by **1 or 2**.  
    **Output**: `file1.txt, file2.txt`

  - `ls file[1-2A-C]*`  
    Matches files starting with "file" followed by **1, 2, A, B, or C**.  
    **Output**: `fileA.txt, fileB.txt, fileC.txt, file1.txt, file2.txt`

---

#### **5. Caret (`^`)**
- **What it does**: Used in **regular expressions** to mean "starts with." Think of it like saying, "Match things that begin with this."

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

> **Note**: The caret (`^`) is mainly used in tools like `grep` for searching inside files, not for matching filenames.

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
