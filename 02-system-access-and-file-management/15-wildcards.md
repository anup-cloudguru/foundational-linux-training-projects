# **Module 2: System Access and File Management**

## **Chapter 15: Wildcards (`*`, `?`, `{}`, `[]`)**

![Linux](https://img.shields.io/badge/Linux-Fundamentals-green) ![Wildcard_Types](https://img.shields.io/badge/Wildcards-Types-blue)

---

### **📌 Introduction**
Wildcards are powerful tools in Linux that help match patterns in filenames or directories, making tasks like searching, listing, copying, or deleting files faster and more efficient.  

> 📝 **Difference**:  
> - **Wildcards**: Used for filename patterns.  
> - **Regular Expressions**: Used for searching text patterns in files.  

---

### **🛠️ Types of Wildcards**

#### **1. Asterisk (`*`)**  
**Matches**: Any number of characters (including none).  
**Examples**:  

Files:  
```txt
ABC123.txt, ABC_Notes.txt, ABC.txt, XYZ.txt
```  

| Command              | Matches Files                      | Output                          |
|----------------------|-------------------------------------|---------------------------------|
| `ls ABC*`            | Starts with "ABC"                 | `ABC123.txt, ABC_Notes.txt, ABC.txt` |
| `ls *.txt`           | Ends with `.txt`                  | `ABC123.txt, ABC_Notes.txt, ABC.txt, XYZ.txt` |
| `rm ABC*`            | Deletes files starting with "ABC" | Remaining: `XYZ.txt`            |

---

#### **2. Question Mark (`?`)**  
**Matches**: Exactly one character.  

Files:  
```txt
A1.txt, A2.txt, AB.txt, ABC.txt, A123.txt
```  

| Command              | Matches Files                      | Output                          |
|----------------------|-------------------------------------|---------------------------------|
| `ls A?.txt`          | `A + one character + .txt`        | `A1.txt, A2.txt, AB.txt`       |
| `ls A??.txt`         | `A + two characters + .txt`       | `ABC.txt`                      |

---

#### **3. Curly Braces (`{}`)**  
**Matches**: A sequence or specific set of options.  

**Examples**:  

| Command                              | Explanation                             | Output                                    |
|--------------------------------------|-----------------------------------------|------------------------------------------|
| `touch file{1..3}.txt`               | Creates files: file1, file2, file3      | `file1.txt, file2.txt, file3.txt`        |
| `touch report_{jan,feb,mar}.txt`     | Creates specific files                  | `report_jan.txt, report_feb.txt, report_mar.txt` |
| `cp file{1,2}.txt destination/`      | Copies `file1` and `file2`              | N/A                                      |

---

#### **4. Square Brackets (`[]`)**  
**Matches**: A single character from a set or range.  

Files:  
```txt
fileA.txt, fileB.txt, fileC.txt, file1.txt, file2.txt
```  

| Command              | Matches Files                      | Output                          |
|----------------------|-------------------------------------|---------------------------------|
| `ls file[A-C]*`      | Starts with `file` + A/B/C         | `fileA.txt, fileB.txt, fileC.txt` |
| `ls file[1-2]*`      | Starts with `file` + 1/2           | `file1.txt, file2.txt`          |

---

#### **5. Caret (`^`)** *(Regular Expression)*  
Used with commands like `grep` to match the **start of a string**.  

Text file (`names.txt`):  
```txt
abc123  
123abc  
abcdef  
xyzabc
```  

| Command               | Matches Lines                     | Output                          |
|-----------------------|------------------------------------|---------------------------------|
| `grep '^abc' names`   | Lines starting with "abc"         | `abc123, abcdef`               |
| `grep '^[0-9]' names` | Lines starting with digits (0-9)  | `123abc`                       |

---

### **✨ Practical Scenarios**

#### **Wildcard Use Cases**
1. **List All `.txt` Files**:  
   ```bash
   ls *.txt
   ```

2. **Create Monthly Reports**:  
   ```bash
   touch report_{jan,feb,mar}.txt
   ```

3. **Search Files by Range**:  
   ```bash
   ls file[1-3]*.txt
   ```

4. **Find Lines Matching a Pattern**:  
   ```bash
   grep '^abc' names.txt
   ```

---

### **📊 Comparison Table**

| Wildcard | Function                                   | Example               | Output                                      |
|----------|-------------------------------------------|-----------------------|---------------------------------------------|
| `*`      | Matches any number of characters          | `ls ABC*`             | `ABC123.txt, ABC_Notes.txt, ABC.txt`        |
| `?`      | Matches exactly one character             | `ls A?.txt`           | `A1.txt, A2.txt, AB.txt`                   |
| `{}`     | Matches a sequence or set of choices      | `echo {A,B,C}123`     | `A123, B123, C123`                          |
| `[]`     | Matches one character from a set or range | `ls file[1-2]*`       | `file1.txt, file2.txt`                     |
| `^`      | Matches the start of a string (regex)     | `grep '^abc' names`   | Lines starting with "abc" (`abc123`)       |

---
