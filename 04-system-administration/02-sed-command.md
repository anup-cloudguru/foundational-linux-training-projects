# **Module 4: Linux Command Line Tools**

## **Chapter 2: Text Manipulation with `sed` Command**

![Linux](https://img.shields.io/badge/Linux-Command--Line-blue) ![sed](https://img.shields.io/badge/Command-sed-orange)

---

### **🔑 Introduction**

The **`sed` command** is a versatile and powerful stream editor in Linux, allowing users to perform advanced text manipulation. It can be used for tasks such as substituting text, deleting lines, and transforming file content without needing to open the file in an editor. Its efficiency shines when processing large datasets or automating repetitive tasks.

---

### **🔍 Common Use Cases of `sed`**

#### **1. Replacing Text**

Substitute all occurrences of a word in a file:
```bash
sed 's/old_word/new_word/g' datafile.txt
```
- **`s`**: Stands for substitution.
- **`g`**: Ensures all occurrences in a line are replaced.

Save the changes directly to the file:
```bash
sed -i 's/old_word/new_word/g' datafile.txt
```
- **`-i`**: Performs in-place editing.

---

#### **2. Deleting Lines**

Remove all lines containing a specific word:
```bash
sed '/unwanted_word/d' datafile.txt
```

Delete a specific line by its number (e.g., line 3):
```bash
sed '3d' datafile.txt
```

Delete a range of lines (e.g., lines 5 to 10):
```bash
sed '5,10d' datafile.txt
```

---

#### **3. Removing Blank Lines**

Delete all empty lines from a file:
```bash
sed '/^$/d' datafile.txt
```
- **`^$`**: Matches empty lines (lines with no content).

---

#### **4. Replacing Tabs with Spaces**

Replace all tab characters with spaces:
```bash
sed 's/\t/ /g' datafile.txt
```
- **`\t`**: Represents a tab character.

---

#### **5. Viewing Specific Lines**

Display lines 8 to 15:
```bash
sed -n '8,15p' datafile.txt
```
- **`-n`**: Suppresses automatic printing.
- **`p`**: Prints only the specified lines.

Exclude lines 8 to 15:
```bash
sed '8,15d' datafile.txt
```

---

#### **6. Adding Blank Lines**

Insert a blank line after each line:
```bash
sed 'G' datafile.txt
```
- **`G`**: Appends a newline after every line.

---

### **🛠️ Practical Examples**

#### **Example 1: Replace Text in a File**
Change all occurrences of "Apple" to "Orange" in `fruits_list.txt`:
```bash
sed -i 's/Apple/Orange/g' fruits_list.txt
```

#### **Example 2: Delete Lines Containing a Word**
Remove lines containing "Banana":
```bash
sed '/Banana/d' fruits_list.txt
```

#### **Example 3: Remove Blank Lines**
Clean up a file by deleting all empty lines:
```bash
sed -i '/^$/d' fruits_list.txt
```

#### **Example 4: Replace Tabs with Spaces**
Convert tabs to spaces in a file:
```bash
sed -i 's/\t/ /g' fruits_list.txt
```

#### **Example 5: View Specific Lines**
Display lines 3 to 7 from the file:
```bash
sed -n '3,7p' fruits_list.txt
```

---

### **✅ Key Takeaways**

- The **`sed` command** is ideal for automating text transformations.
- Use `-i` for in-place edits or redirect output for safer experimentation.
- Combine `sed` with other commands like `grep` or `awk` for advanced data processing.

By mastering `sed`, you can efficiently edit and manage text files, saving valuable time in your workflows.

---

### **📖 Further Reading**

- [GNU sed Documentation](https://www.gnu.org/software/sed/manual/sed.html)
- [Linux `sed` Command Examples](https://www.linuxcommand.org/lc3_adv_sed.php)

---

