# **Module 2: System Access and File Management**  
## **Chapter 13: Copying Directories**

### **Overview**
In this chapter, we will learn how to copy directories in Linux, an important skill when working with configuration files or backing up directories. Copying directories is similar to copying files, but it requires the use of the `cp` command with a special option for recursion.

### **Learning Objectives**
By the end of this chapter, you should be able to:
1. Use the `cp` command to copy directories.
2. Understand the significance of the `-R` (recursive) option when copying directories.
3. Create and verify copied directories and their contents.

### **Concepts Covered**
1. **Copying Directories with the `cp` Command**:
    - To copy a directory, we use the same `cp` command that we use to copy files, but with the `-R` option to handle directories recursively.
    - Without the `-R` option, the `cp` command will fail, stating that the source is a directory and not a file.
  
2. **Recursive Copying**:
    - The `-R` flag tells the system to copy not only the directory but also its contents, including all subdirectories and files.

### **Commands Used**
- `cp -R [source_directory] [destination_directory]`  
  This command will copy the source directory to the destination directory.
  
- `cd`  
  Changes the current working directory.

- `ls -ltr`  
  Lists the contents of the directory in long format, sorted by modification time.

- `touch`  
  Creates an empty file.

### **Steps to Copy Directories**

1. **Creating a Directory and Files**:
    - Start by creating a new directory, e.g., `config`, where we will store configuration files.
    - Use `touch` to create some configuration files within the directory:
      ```bash
      mkdir config
      cd config
      touch a.com b.com c.com
      ```

2. **Copying the Directory**:
    - Navigate back to the home directory:
      ```bash
      cd ~
      ```
    - Attempt to copy the `config` directory to the `/temp` directory:
      ```bash
      cp config /temp
      ```
      This will fail because `cp` without `-R` can't copy directories.

3. **Copying the Directory with the `-R` Option**:
    - To copy the directory recursively, use the `-R` option:
      ```bash
      cp -R config /temp/config-backup
      ```
    - This command will copy the entire `config` directory and its contents to `/temp/config-backup`.

4. **Verifying the Copy**:
    - Use `ls -ltr` to verify the directory has been copied:
      ```bash
      cd /temp
      ls -ltr
      ```
      You should see `config-backup` in the list of directories.

    - To verify the contents, go into the `config-backup` directory:
      ```bash
      cd config-backup
      ls -ltr
      ```
      You will see that the files (`a.com`, `b.com`, `c.com`) have been copied as well.

### **Example Session**
```bash
# Create a new directory called "config"
mkdir config
cd config

# Create some configuration files
touch a.com b.com c.com

# Verify files are created
ls -l

# Go back to the home directory
cd ~

# Copy the "config" directory to /temp with recursive option
cp -R config /temp/config-backup

# Verify the copied directory in /temp
cd /temp
ls -ltr

# Verify the files inside the copied directory
cd config-backup
ls -ltr
```

### **Important Notes**
- The `-R` option is essential when copying directories. It ensures that not only the directory is copied, but also all files and subdirectories contained within it.
- You can rename the destination directory while copying by specifying a new name (e.g., `/temp/config-backup`).

---

### **Conclusion**
In this chapter, you learned how to copy directories in Linux using the `cp` command with the `-R` option. This is a vital skill when managing configuration files or performing backups. You can apply this knowledge to safely copy directories before making any modifications, ensuring that you can restore them if necessary.

---
