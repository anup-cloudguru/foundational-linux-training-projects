# **Module 2: System Access and File Management**

## **Chapter 15: Wildcards (`*`, `?`, `{}`, `[]`)**

### **What Are Wildcards?**

Wildcards are special characters in Linux that help you match patterns in filenames or directories. Instead of typing out every file name, you can use wildcards to work with many files at once. This makes tasks like searching, listing, copying, or deleting files much faster and more efficient.

> **Note**: Wildcards are different from regular expressions. Wildcards are primarily used for matching filenames, while regular expressions are used for searching patterns in text files.

---

### **Types of Wildcards and How They Work**

#### **1. Asterisk (`*`)**
- **What it does**: Matches **any number of characters**, including none. It’s like saying, "Match everything."

- **Examples**:

  Imagine you have these files:
  ```txt
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
- **What it does**: Matches **exactly one character**. Think of it as filling in a single blank.

- **Examples**:

  Imagine these files:
  ```txt
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
- **What it does**: Used for creating patterns in **sequences** or **specific choices**. It simplifies repetitive tasks by reducing the need to type multiple commands.

- **Examples**:
  - `touch file{1..10}.txt`  
    Creates 10 files: `file1.txt, file2.txt, ..., file10.txt`
  
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
- **What it does**: Matches **one character from a set or range**. It’s like saying, "Choose one from this group."

- **Examples**:

  Imagine you have these files:
  ```txt
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
- **What it does**: Used in **regular expressions** (not as a wildcard) to match strings that **start with specific characters**. It’s commonly used with tools like `grep`.

- **Examples**:

  If you have a file `names.txt` with these lines:
  ```txt
  abc123  
  123abc  
  abcdef  
  xyzabc
  ```

  - `grep '^abc' names.txt`  
    Finds lines that **start with "abc"**.  
    **Output**:
    ```txt
    abc123  
    abcdef
    ```

> **Note**: The caret (`^`) is not a wildcard. It is a regular expression operator and is included here for completeness.

---

### **Why Wildcards Are Useful**

- **Save time** when working with lots of files.
- **Simplify** complex tasks like searching, copying, and deleting files.
- **Reduce repetitive typing** by matching patterns.

> **Limitations**:  
> - Wildcards do not match hidden files (starting with `.`) unless explicitly specified.  
> - Files with special characters (e.g., spaces) may require escaping or quoting.

---

### **Quick Summary Table**

| Wildcard | What It Matches                            | Example               | Output                                      |
|----------|--------------------------------------------|-----------------------|---------------------------------------------|
| `*`      | Any number of characters (including none)  | `ls ABC*`             | `ABC123.txt, ABC_Notes.txt, ABC.txt`        |
| `?`      | Exactly one character                     | `ls A?.txt`           | `A1.txt, A2.txt, AB.txt`                   |
| `{}`     | A sequence or set of choices              | `echo {A,B,C}123`     | `A123, B123, C123`                          |
| `[]`     | One character from a set or range         | `ls file[1-2]*`       | `file1.txt, file2.txt`                     |
| `^`      | Start of a string (for `grep`)            | `grep '^abc' names`   | Lines starting with "abc" (e.g., `abc123`) |

---

### **Practice Tasks**

#### **For `*`**
1. **Prepare the environment**:  
   ```bash
   touch report1.txt report2.txt report_final.txt summary.docx log2023.log temp.bak
   ```

2. List all `.txt` files:  
   ```bash
   ls *.txt
   ```

3. Copy all files with "report" in the name:  
   ```bash
   cp *report* /home/username/
   ```

---

#### **For `?`**
1. **Prepare the environment**:  
   ```bash
   touch file1.txt file2.txt fileA.txt fileAB.txt fileXYZ.txt
   ```

2. List files with exactly one character before `.txt`:  
   ```bash
   ls file?.txt
   ```

---

#### **For `{}`**
1. **Create month-specific files**:  
   ```bash
   touch report_{jan,feb,mar}.txt
   ```

2. Copy files:  
   ```bash
   cp report_{jan,mar}.txt /home/username/
   ```

---

#### **For `[]`**
1. **Prepare the environment**:  
   ```bash
   touch fileA.txt fileB.txt fileC.txt file1.txt file2.txt
   ```

2. List files starting with "file" and a specific letter:  
   ```bash
   ls file[A-B]*.txt
   ```

---

#### **For `^`**
1. **Prepare the environment**:  
   ```bash
   echo -e "abc123\n123abc\nabcdef\nxyzabc" > names.txt
   ```

2. Find lines starting with "abc":  
   ```bash
   grep '^abc' names.txt
   ```

3. **Find lines starting with a digit**:  
   ```bash
   grep '^[0-9]' names.txt
   ```  
   **Explanation**: Matches lines where the first character is a number (0-9).

4. **Find lines starting with a specific letter (e.g., `x`)**:  
   ```bash
   grep '^x' names.txt
   ```  
   **Explanation**: Matches lines where the first character is the letter `x`.

5. **Find lines starting with any lowercase letter**:  
   ```bash
   grep '^[a-z]' names.txt
   ```  
   **Explanation**: Matches lines starting with any lowercase alphabetic character.

6. **Extract only the matching starting pattern**:  
   ```bash
   grep -o '^abc' names.txt
   ```  
   **Explanation**: Outputs only the matching portion (`abc`) for lines starting with "abc".

---

### **Key Takeaways**
- Wildcards are an essential tool in Linux file management. They allow you to simplify tasks and reduce manual effort.
- Using wildcards correctly can help you automate repetitive tasks, such as copying, deleting, or finding files.
- Combining wildcards with other Linux commands (e.g., `ls`, `cp`, `rm`, `grep`) makes file and directory operations more efficient.
- While wildcards work on filenames, regular expressions like `^` are used for text pattern matching in commands like `grep`.

By mastering wildcards, you can significantly enhance your productivity in Linux file management and system navigation.

---
