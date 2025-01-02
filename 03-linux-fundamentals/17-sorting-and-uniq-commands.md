# **Module 3: Linux Fundamentals**

## **Chapter 17: Sorting and Uniq Commands in Linux**

![Linux](https://img.shields.io/badge/Linux-Fundamentals-green) ![Text Processing](https://img.shields.io/badge/Text-Processing-blue)

---

### **🔑 Introduction**

In this chapter, we will explore two essential Linux commands: `sort` and `uniq`. These commands are part of text processing tools and help in organizing and filtering data from files or command outputs. The `sort` command arranges lines in alphabetical or reverse order, while the `uniq` command removes duplicate lines from sorted files or input streams. Let’s dive into their usage with practical examples.

---

### **📚 Understanding Sorting and Uniq Commands**

#### **1️⃣ Setting Up the Environment**

Before we start using these commands, let’s set up our environment.

1. **Log in to your Linux system:**
   - Use your preferred method (e.g., PuTTY, terminal) to log in.

2. **Navigate to the directory with the required file:**
   - Use the following commands:
     ```bash
     whoami  # Check your username
     pwd      # Confirm the current working directory
     cd /home/Seinfeld  # Navigate to the Seinfeld directory
     ```

3. **Verify the content of the file:**
   - Use the `cat` command to view the file named `seinfeld-characters`:
     ```bash
     cat seinfeld-characters
     ```

   Example contents of the file:
   ```
   Jerry Seinfeld
   Elaine Benes
   Cosmo Kramer
   George Costanza
   Newman
   Jerry Seinfeld
   ```

---

#### **2️⃣ Using the `sort` Command**

The `sort` command organizes the lines in a file in alphabetical order by default. Let’s try it out:

1. **Sort the contents of the file:**
   ```bash
   sort seinfeld-characters
   ```

   **Output:**
   ```
   Cosmo Kramer
   Elaine Benes
   George Costanza
   Jerry Seinfeld
   Jerry Seinfeld
   Newman
   ```

2. **Sort in reverse order:**
   - Use the `-r` option for reverse order:
     ```bash
     sort -r seinfeld-characters
     ```

   **Output:**
   ```
   Newman
   Jerry Seinfeld
   Jerry Seinfeld
   George Costanza
   Elaine Benes
   Cosmo Kramer
   ```

3. **Sort by a specific field:**
   - Use the `-k` option to specify the field number to sort by. For example, to sort by the second field:
     ```bash
     sort -k2 seinfeld-characters
     ```

   **Output:**
   ```
   Elaine Benes
   George Costanza
   Cosmo Kramer
   Newman
   Jerry Seinfeld
   Jerry Seinfeld
   ```

4. **Sort the output of another command:**
   - Combine the `ls` command with `sort` to organize the output alphabetically:
     ```bash
     ls -l | sort
     ```

---

#### **3️⃣ Using the `uniq` Command**

The `uniq` command filters out duplicate lines but works only on sorted data. Always use `sort` before `uniq` to ensure proper functioning.

1. **Remove duplicate lines:**
   ```bash
   sort seinfeld-characters | uniq
   ```

   **Output:**
   ```
   Cosmo Kramer
   Elaine Benes
   George Costanza
   Jerry Seinfeld
   Newman
   ```

2. **Count occurrences of each line:**
   - Use the `-c` option to display the count of each line:
     ```bash
     sort seinfeld-characters | uniq -c
     ```

   **Output:**
   ```
     1 Cosmo Kramer
     1 Elaine Benes
     1 George Costanza
     2 Jerry Seinfeld
     1 Newman
   ```

3. **Show only repeated lines:**
   - Use the `-d` option to display duplicate lines:
     ```bash
     sort seinfeld-characters | uniq -d
     ```

   **Output:**
   ```
   Jerry Seinfeld
   ```

---

### **🔄 Key Takeaways**

- The `sort` command organizes data alphabetically or in reverse order and can be combined with other commands for output sorting.
- The `uniq` command removes duplicate lines from a sorted file or input and provides options for counting or displaying duplicates.
- Always use `sort` before `uniq` to ensure accurate results.
- Both commands are powerful tools for text processing and data organization.

---

### **🔍 Practice Tip**

Create your own text files and experiment with sorting and filtering. Try sorting by specific fields, using reverse order, or counting duplicates with `uniq`. These exercises will help solidify your understanding of these commands.

---

### **🐛 Conclusion**

In this chapter, we explored the `sort` and `uniq` commands, their options, and practical examples of their usage. These commands are invaluable for organizing and processing text files efficiently. Mastering them will enhance your ability to manage and manipulate data in Linux.

---
