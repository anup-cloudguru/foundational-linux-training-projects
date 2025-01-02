# **Module 3: Linux Fundamentals**

## **Chapter 18: Counting Lines, Words, and Bytes with WC**

![Linux](https://img.shields.io/badge/Linux-Fundamentals-green) ![Text Processing](https://img.shields.io/badge/Text-Processing-blue)

---

### **🔑 Introduction**

In this chapter, we will explore the `wc` command, one of the most commonly used text-processing tools in Linux. The name `wc` stands for **Word Count**, but the command does more than count words. It can also count lines, words, and bytes in a file or input. Let’s dive into its usage with practical examples.

---

### **📚 Understanding the WC Command**

#### **1️⃣ What is the WC Command?**

The `wc` command is used to read either the standard input or a list of files and generate counts for:  
- **Lines**  
- **Words**  
- **Bytes (or characters)**  

Here’s the general syntax:  
```bash
wc [OPTIONS] [FILE...]
```

Commonly used options include:  
- `-l` to count lines  
- `-w` to count words  
- `-c` to count bytes  

#### **2️⃣ Setting Up the Environment**

Before we start using the `wc` command, let’s log in to the Linux system and set up a sample file.

1. **Log in to your Linux system using PuTTY:**
   - Use the IP address of your machine to connect via PuTTY.
   - After logging in, confirm your username, hostname, and current directory:
     ```bash
     whoami
     hostname
     pwd
     ```

2. **Navigate to your desired directory:**
   ```bash
   cd /home/your-username
   ```

3. **Create a sample file:**
   - Use the `echo` command to create a file named `seinfeld-characters`:
     ```bash
     echo "Jerry Seinfeld" > seinfeld-characters
     echo "Elaine Benes" >> seinfeld-characters
     echo "George Costanza" >> seinfeld-characters
     echo "Cosmo Kramer" >> seinfeld-characters
     ```
   - Verify the contents of the file:
     ```bash
     cat seinfeld-characters
     ```

---

### **🔍 Using the WC Command**

#### **1️⃣ Basic Usage**

The simplest way to use the `wc` command is to run it on a file without any options:  
```bash
wc seinfeld-characters
```

**Output:**
```
4 8 79 seinfeld-characters
```
This indicates:  
- **4** lines  
- **8** words  
- **79** bytes  

---

#### **2️⃣ Count Lines, Words, or Bytes Individually**

- **Count Lines:**  
  To display only the number of lines, use the `-l` option:  
  ```bash
  wc -l seinfeld-characters
  ```  
  **Output:**  
  ```
  4 seinfeld-characters
  ```

- **Count Words:**  
  To display only the number of words, use the `-w` option:  
  ```bash
  wc -w seinfeld-characters
  ```  
  **Output:**  
  ```
  8 seinfeld-characters
  ```

- **Count Bytes:**  
  To display the number of bytes, use the `-c` option:  
  ```bash
  wc -c seinfeld-characters
  ```  
  **Output:**  
  ```
  79 seinfeld-characters
  ```

---

#### **3️⃣ Counting Output from Other Commands**

The `wc` command can also process output from other commands by using a pipe (`|`).

- **Count Files in a Directory:**  
  Run the following to count the number of files and directories:  
  ```bash
  ls -l | wc -l
  ```  
  **Note:** The output includes the `total` line, so subtract 1 from the result to get the actual count.

- **Count Specific Matches in a File:**  
  Use `grep` to search for a term and count its occurrences:  
  ```bash
  grep "Seinfeld" seinfeld-characters | wc -l
  ```  
  **Output:**  
  ```
  1
  ```

---

### **🔄 Key Takeaways**

- The `wc` command is versatile and can count lines, words, and bytes in files or standard input.  
- Use options like `-l`, `-w`, and `-c` to filter specific counts.  
- Combine `wc` with pipes to analyze output from other commands.  

---

### **🔍 Practice Tip**

Try creating your own files with random text and use the `wc` command to practice counting lines, words, and bytes. Additionally, experiment with `grep` and pipes to perform more advanced operations.

---

### **🐛 Conclusion**

The `wc` command is an essential tool in Linux for text processing. It simplifies counting lines, words, and bytes, helping you analyze files and command outputs efficiently. Practice using `wc` in different scenarios to understand its full potential and integrate it into your daily Linux workflow.

--- 
