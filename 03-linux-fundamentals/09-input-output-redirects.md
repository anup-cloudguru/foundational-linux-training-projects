# **Module 3: Linux Fundamentals**  

## **Chapter 9: Input and Output Redirects (>, >>, <, stdin, stdout, and stderr)**  

![Linux](https://img.shields.io/badge/Linux-Fundamentals-green) ![Redirects](https://img.shields.io/badge/Topic-Redirects-blue)  

---

### **🔑 Introduction**  
In Linux, **input and output redirection** is a powerful feature that allows users to control where data is sent and received. By default, commands interact with three standard streams:  

1. **Standard Input (stdin)**: Receives input from the keyboard or a file.  
2. **Standard Output (stdout)**: Displays the output of a command on the screen.  
3. **Standard Error (stderr)**: Shows error messages on the screen.  

With redirection, you can reroute these streams to files, devices, or other commands.  

---

### **🔍 Input and Output Streams Overview**  

1. **Standard Input (stdin)**: File Descriptor `0`. Receives input for commands (e.g., a file).  
2. **Standard Output (stdout)**: File Descriptor `1`. Sends normal output to the terminal.  
3. **Standard Error (stderr)**: File Descriptor `2`. Displays error messages.  

#### **Key Operators for Redirection**  
- `>`: Redirects stdout and **overwrites** a file.  
- `>>`: Redirects stdout and **appends** to a file.  
- `<`: Redirects stdin from a file.  
- `2>`: Redirects stderr to a file.  
- `2>&1`: Combines stdout and stderr into a single stream.  

---

### **⚙️ Standard Output Redirect (>)**  
The `>` operator sends the normal output of a command to a file, overwriting its contents if it already exists.  

#### **Example: Overwriting Output**  
```bash
ls -l > output.txt
```  
- Saves the output of `ls -l` into `output.txt`.  
- If `output.txt` exists, its contents are replaced.  

```bash
cat output.txt
```  
- Displays the contents of `output.txt`.  

---

### **⚙️ Append Output Redirect (>>)**
The `>>` operator appends command output to an existing file, preserving its current contents.  

#### **Example: Appending Output**  
```bash
ls -la >> output.txt
```  
- Appends the output of `ls -la` to `output.txt`.  

---

### **⚙️ Standard Input Redirect (<)**  
The `<` operator feeds a file’s content as input to a command.  

#### **Example: Redirect Input from File**  
```bash
cat < output.txt
```  
- Reads and displays the content of `output.txt` using `cat`.  

---

### **⚙️ Standard Error Redirect (2>)**  
The `2>` operator redirects error messages (stderr) to a file.  

#### **Example: Redirecting Errors**  
```bash
ls /invalidpath > stdout.txt 2> stderr.txt
```  
- Normal output is saved in `stdout.txt`.  
- Error messages are redirected to `stderr.txt`.  

---

### **⚙️ Combine stdout and stderr (2>&1)**  
To merge both stdout and stderr into a single file, use the `2>&1` syntax.  

#### **Example: Merging Streams**  
```bash
ls -l /root > combined.txt 2>&1
```  
- Both successful output and error messages are saved in `combined.txt`.  

---

### **📂 Practical Examples**  

1. **Redirect stdout to a File**:  
   ```bash
   echo "Hello, World!" > hello.txt
   ```  

2. **Append stdout to a File**:  
   ```bash
   echo "Appended Text" >> hello.txt
   ```  

3. **Redirect stderr to a File**:  
   ```bash
   ls nonexistentfile 2> errorlog.txt
   ```  

4. **Redirect stdout and stderr Together**:  
   ```bash
   ls /invalidpath > output.txt 2>&1
   ```  

5. **Use stdin to Read a File**:  
   ```bash
   cat < hello.txt
   ```  

---

### **✅ Summary**  

- **Input and Output Streams**: Linux commands use stdin (input), stdout (output), and stderr (errors).  
- **Key Operators**: `>`, `>>`, `<`, `2>`, and `2>&1`.  
- **Practical Applications**:  
  - Save command output to files.  
  - Capture error messages for debugging.  
  - Automate input using files.  

Mastering these redirection techniques is essential for efficient file handling and troubleshooting in Linux.  

---

### **📖 Further Reading**  
- [Linux I/O Redirection Tutorial](https://linuxize.com/post/bash-redirect-stderr-stdout/)  
- [GNU Documentation on Redirection](https://www.gnu.org/software/bash/manual/html_node/Redirections.html)  

---
