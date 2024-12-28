# **Module 3: Linux Fundamentals**  

## **Chapter 10: Using the `tee` Command for Output Redirection**  

![Linux](https://img.shields.io/badge/Linux-Fundamentals-green) ![tee](https://img.shields.io/badge/Topic-tee-blue)  

---

### **🔑 Introduction**  
In Linux, the `tee` command is a useful tool for simultaneously displaying the output of a command and saving it to a file. It works like a "T-splitter" in plumbing, where the output of a command is both displayed on the screen and written to a file. This is an enhancement over using the `>` operator, which only outputs data to a file without showing it on the screen.

As an aspiring cloud engineer, mastering tools like `tee` is essential for managing data streams and automating tasks efficiently in a Linux environment.

---

### **🔍 How the `tee` Command Works**  

The `tee` command is used to redirect the output of a command to both the screen and one or more files. This allows users to view the output while also storing it in a file for further use.  

#### **Key Features**:  
- **Simultaneous Output and File Storage**: The `tee` command allows you to view the output on the screen while saving it to a file.  
- **Works with Pipes**: It can be used in conjunction with pipes (`|`) to process the output of commands.  
- **Append Mode**: The `tee -a` option allows you to append to an existing file instead of overwriting it.  

---

### **⚙️ Basic Usage of `tee`**  
To use `tee`, simply pipe the output of a command into it. For example, to echo a statement to both the screen and a file, you can use:  

```bash
echo "Anup Moitra is learning cloud engineering" | tee cloud-engineer-info.txt
```  

- This will display the text on the screen and save it to `cloud-engineer-info.txt`.

#### **Example: Viewing and Saving Output**  
```bash
echo "Anup Moitra is learning cloud engineering" | tee cloud-engineer-info.txt
```  
- Displays: "Anup Moitra is learning cloud engineering" on the screen.  
- Saves the output to `cloud-engineer-info.txt`.  

---

### **⚙️ Redirecting and Appending Output**  

When using the `tee` command, you can also append the output to a file by using the `-a` option.  

#### **Example: Appending to a File**  
```bash
echo "Anup is making progress with his Linux skills" | tee -a cloud-engineer-info.txt
```  
- This command appends "Anup is making progress with his Linux skills" to the file `cloud-engineer-info.txt`, preserving the previous content.  

To verify the content:  
```bash
cat cloud-engineer-info.txt
```  
- Displays both lines in the file:  
  - "Anup Moitra is learning cloud engineering"  
  - "Anup is making progress with his Linux skills"

---

### **⚙️ Using `tee` with Other Commands**  

You can use `tee` with various commands to capture their output while still viewing it on the screen. For example, to list the contents of a directory and save the output:  

#### **Example: Using `tee` with `ls`**  
```bash
ls -l | tee directory-listing.txt
```  
- Displays the directory listing on the screen.  
- Saves the output to `directory-listing.txt`.  

#### **Example: Using `tee` with Multiple Files**  
```bash
ls -l | tee file1.txt file2.txt file3.txt
```  
- Saves the output of `ls -l` to `file1.txt`, `file2.txt`, and `file3.txt`.  
- You can use `cat` to display the contents of each file:  
  ```bash
  cat file1.txt
  cat file2.txt
  cat file3.txt
  ```

---

### **⚙️ Viewing Help for `tee`**  

To see more options and usage examples for the `tee` command, use the `--help` flag:  

```bash
tee --help
```  
- This will display a list of available options for `tee`.  

For example:  
- `-a` for appending to a file.  
- `-i` to ignore interruptions.  
- `--version` to check the version of `tee`.  

---

### **📂 Practical Examples**  

1. **Echo Output to a File**:  
   ```bash
   echo "Hello, Cloud World!" | tee greeting.txt
   ```  
   - Displays "Hello, Cloud World!" and saves it to `greeting.txt`.

2. **Append Output to a File**:  
   ```bash
   echo "Anup is exploring cloud services" | tee -a cloud-engineer-info.txt
   ```  
   - Appends "Anup is exploring cloud services" to `cloud-engineer-info.txt`.

3. **List Directory and Save Output**:  
   ```bash
   ls -l | tee cloud-project-files.txt
   ```  
   - Displays and saves the output of `ls -l` to `cloud-project-files.txt`.

4. **Display and Save Multiple Outputs**:  
   ```bash
   echo "Cloud technologies are advancing rapidly" | tee cloud-tech1.txt cloud-tech2.txt
   ```  
   - Saves "Cloud technologies are advancing rapidly" to both `cloud-tech1.txt` and `cloud-tech2.txt`.

---

### **✅ Summary**  

- The `tee` command allows users to redirect command output to both the screen and a file.  
- **Appended Output**: Use `tee -a` to append data to an existing file without overwriting it.  
- **Multi-File Output**: Redirect output to multiple files simultaneously.  
- Mastering the `tee` command is valuable for cloud engineers who need to manage data streams and logs efficiently in a Linux environment.

---

### **📖 Further Reading**  
- [Linux tee Command Guide](https://www.gnu.org/software/coreutils/manual/html_node/tee-invocation.html)  
- [Learn More About Pipes and Redirection](https://www.gnu.org/software/bash/manual/html_node/Pipelines.html)  

---
