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

#### **For `*`**
1. **Prepare the environment:**
   ```bash
   touch report1.txt report2.txt report_final.txt summary.docx log2023.log temp.bak
   ```
   **Outcome**: Creates some sample files to work with.

2. **List all `.txt` files:**
   ```bash
   ls *.txt
   ```

3. **List files starting with "log" and ending in `.log`:**
   ```bash
   ls log*.log
   ```

4. **Copy all files with "report" in the name:**
   ```bash
   cp *report* /home/username/
   ```

5. **Delete all `.bak` files:**
   ```bash
   rm *.bak
   ```

---

#### **For `?`**
1. **Prepare the environment:**
   ```bash
   touch file1.txt file2.txt fileA.txt fileAB.txt fileXYZ.txt
   ```

2. **List files with exactly one character before `.txt`:**
   ```bash
   ls file?.txt
   ```

3. **List files with exactly two characters in the name:**
   ```bash
   ls ??.txt
   ```

4. **Copy `.log` files with one character after "read":**
   ```bash
   cp read?.log /home/username/
   ```

5. **Delete `.log` files with one character after "error":**
   ```bash
   rm error?.log
   ```

---

#### **For `{}`**
1. **List specific files:**
   ```bash
   ls file{1,3,5}.txt
   ```

2. **Copy month-specific files:**
   ```bash
   cp report_{jan,feb,mar}.txt /home/username/
   ```

3. **Delete sequence-based files:**
   ```bash
   rm data_{01..10}.csv
   ```

---

#### **For `[]`**
1. **Prepare the environment:**
   ```bash
   touch fileA.txt fileB.txt fileC.txt file1.txt file2.txt file3.log
   ```

2. **List files starting with "file" and followed by a range (1-3):**
   ```bash
   ls file[1-3].txt
   ```

3. **List files starting with "file" and followed by specific letters (A, B):**
   ```bash
   ls file[A-B]*.txt
   ```

4. **Copy files matching range or set:**
   ```bash
   cp file[1-3A-C].txt /home/username/
   ```

5. **Delete files ending with numbers in a range (1-5):**
   ```bash
   rm file[1-5].log
   ```

---

#### **For `^`**
1. **Prepare the environment:**
   ```bash
   echo -e "abc123\n123abc\nabcdef\nxyzabc" > names.txt
   ```

2. **Find lines starting with "abc":**
   ```bash
   grep '^abc' names.txt
   ```

3. **Find lines starting with a digit:**
   ```bash
   grep '^[0-9]' names.txt
   ```

4. **Find lines starting with a specific letter (e.g., `x`):**
   ```bash
   grep '^x' names.txt
   ```

5. **Find lines starting with a lowercase letter:**
   ```bash
   grep '^[a-z]' names.txt
   ```

6. **Find lines starting with "abc" but exclude the rest:**
   ```bash
   grep -o '^abc' names.txt
   ```

---
