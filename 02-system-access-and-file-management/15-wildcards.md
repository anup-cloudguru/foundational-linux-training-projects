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

### **Practice Tasks**

#### **Practice Tasks for `*`**

1. **List all `.txt` files in a directory:**
   - **Command**:
     ```bash
     ls *.txt
     ```
   - **Outcome**: Lists all files ending with `.txt`.

2. **List files starting with "log" and ending in `.log`:**
   - **Command**:
     ```bash
     ls log*.log
     ```
   - **Outcome**: Lists all files like `logfile.log`, `log2023.log`.

3. **Copy all files with "report" in the name:**
   - **Command**:
     ```bash
     cp *report* /home/username/
     ```
   - **Outcome**: Copies all files with "report" in the name to `/home/username/`.

4. **Delete all `.bak` files:**
   - **Command**:
     ```bash
     rm *.bak
     ```
   - **Outcome**: Deletes all files ending in `.bak`.

---

#### **Practice Tasks for `?`**

1. **List files with exactly one character before `.txt`:**
   - **Command**:
     ```bash
     ls file?.txt
     ```
   - **Outcome**: Matches `file1.txt`, `file2.txt`, `fileA.txt`.

2. **List files with exactly two characters in the name:**
   - **Command**:
     ```bash
     ls ??.txt
     ```
   - **Outcome**: No output if no file has two-character names.

3. **Copy `.log` files with one character after "read":**
   - **Command**:
     ```bash
     cp read?.log /home/username/
     ```
   - **Outcome**: Copies files like `read1.log`, `read2.log`.

4. **Delete `.log` files with one character after "error":**
   - **Command**:
     ```bash
     rm error?.log
     ```
   - **Outcome**: Deletes files like `error1.log`, `errorA.log`.

---

#### **Practice Tasks for `{}`**

1. **Create sequence-based files:**
   - **Command**:
     ```bash
     touch report_{1..5}.txt
     ```
   - **Outcome**: Creates `report_1.txt`, `report_2.txt`, ..., `report_5.txt`.

2. **List specific files:**
   - **Command**:
     ```bash
     ls file{1,3,5}.txt
     ```
   - **Outcome**: Lists `file1.txt`, `file3.txt`, `file5.txt`.

3. **Copy month-specific files:**
   - **Command**:
     ```bash
     cp report_{jan,feb,mar}.txt /home/username/
     ```
   - **Outcome**: Copies files like `report_jan.txt` to `/home/username/`.

4. **Delete sequence-based files:**
   - **Command**:
     ```bash
     rm data_{01..10}.csv
     ```
   - **Outcome**: Deletes files `data_01.csv`, ..., `data_10.csv`.

---

#### **Practice Tasks for `[]`**

1. **List files starting with "file" and followed by a range (1-3):**
   - **Command**:
     ```bash
     ls file[1-3].txt
     ```
   - **Outcome**: Matches `file1.txt`, `file2.txt`, `file3.txt`.

2. **List files starting with "file" and followed by specific letters (A, B):**
   - **Command**:
     ```bash
     ls file[A-B]*
     ```
   - **Outcome**: Matches `fileA.txt`, `fileB.txt`.

3. **Copy files matching range or set:**
   - **Command**:
     ```bash
     cp file[1-3A-C].txt /home/username/
     ```
   - **Outcome**: Copies files like `file1.txt`, `fileA.txt`.

4. **Delete files ending with numbers in a range (1-5):**
   - **Command**:
     ```bash
     rm file[1-5].log
     ```
   - **Outcome**: Deletes files like `file1.log`, `file5.log`.

---

#### **Practice Tasks for `^`**

1. **Find lines starting with "abc" in a text file:**
   - **Command**:
     ```bash
     grep '^abc' names.txt
     ```
   - **Outcome**: Matches lines starting with `abc`.

2. **Find lines starting with a digit:**
   - **Command**:
     ```bash
     grep '^[0-9]' names.txt
     ```
   - **Outcome**: Matches lines like `123abc`, `456def`.

3. **Filter log entries starting with a timestamp:**
   - **Command**:
     ```bash
     grep '^[0-9][0-9][0-9]' logs.txt
     ```
   - **Outcome**: Matches lines starting with a 3-digit timestamp.

4. **List files not starting with a specific letter:**
   - **Command**:
     ```bash
     ls [^a]*
     ```
   - **Outcome**: Matches files not starting with `a`.

---
