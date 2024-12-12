# **Module 2: System Access and File Management**  
## **Chapter 13: Copying Directories**

### **Introduction**  
In this chapter, we’ll explore how to copy directories in Linux. While we’ve previously covered file management techniques, copying directories is an essential skill, particularly when managing configuration files or backups. The `cp -R` command ensures that all contents, including subdirectories and files, are copied over correctly, preserving the directory structure.

---

## **The `cp` Command for Copying Directories**

The `cp` command is used to copy files, but when dealing with directories, we must add the `-R` (recursive) option. This tells the system to copy not only the directory but also all of its contents, including files and subdirectories.

### 1. **Using the `cp` Command with the `-R` Option**  
To copy a directory, you use the `cp` command with the `-R` option. The basic syntax is:

```
cp -R dir1 /home/anupmoitra/dir2
```

- **`-R`**: This option copies the directory and all its contents (subdirectories and files), ensuring that the entire directory structure is preserved. Without this option, only files would be copied, and directories would be omitted.
- **`source_directory`**: The directory you want to copy.
- **`destination_directory`**: The location where you want the directory to be copied to. If the destination directory does not exist, it will be created.

### **Example**:  
```bash
cp -R dir1 /home/anupmoitra/dir2
```

This command will copy the `dir1` directory, along with all its contents, to the `/home/anupmoitra/dir2` directory. If `dir2` does not exist, it will be created.

**Screenshot Example**:  
![Copying a directory using the cp command](screenshots/01-cp-copy-directory.png)  
*Figure 1: Copying the `dir1` directory to `/home/anupmoitra/dir2` using the `cp -R` command.*

---

### 2. **Renaming the Destination Directory**  
You can also specify a new name for the copied directory by adding the desired name after the destination path. If you want to copy the `config_files` directory to `/tmp` and rename it to `config_backup`, the command would be:

```bash
cp -R config_files /tmp/config_backup
```

This command will copy the directory and its contents into `/tmp` under the new name `config_backup`.

---

### 3. **What Happens Without the `-R` Option?**  
If you try to copy a directory without using the `-R` option, you will encounter an error because `cp` will assume that you are trying to copy a file, not a directory.

For example, running this command:

```bash
cp config_files /tmp
```

will produce an error like:

```
cp: omitting directory 'config_files'
```

This is because `cp` cannot copy a directory unless you specify `-R` to handle the recursive copy. The `-R` option tells `cp` to copy all files and subdirectories within the source directory.

**Screenshot Example**:  
![Error without the -R option](screenshots/cp-error-without-R.png)  
*Figure 2: Error message when trying to copy a directory without using the `-R` option.*

---

## **Verifying the Copied Directory**

After you run the `cp -R` command, it’s important to verify that the directory and its contents were copied successfully.

### 1. **Listing the Contents of the Destination Directory**  
To verify the copied directory, navigate to the destination directory and list its contents using the `ls -l` command:

```bash
cd /tmp
ls -l
```

This will display the `config_files` (or `config_backup`, if renamed) directory in the `/tmp` location.

**Screenshot Example**:  
![Verifying the copied directory](screenshots/verifying-copied-directory.png)  
*Figure 3: Verifying the copied directory in `/tmp`.*

### 2. **Navigating into the Copied Directory**  
To check the contents inside the copied directory, use the `cd` command to navigate into it and list the files:

```bash
cd /tmp/config_files
ls -l
```

You should see the same files that were in the original `config_files` directory.

---

## **Important Notes**

- **Recursive Copy**: The `-R` option is essential when copying directories. It ensures that subdirectories and files within the directory are included. Without `-R`, only files are copied, and subdirectories will be omitted, resulting in an incomplete copy.
- **Permissions**: You need the necessary permissions to copy directories into certain locations. For system directories, you may need to use `sudo` to ensure you have the required privileges to perform the operation.

**Example with Elevated Privileges**:  
```bash
sudo cp -R config_files /etc/backup
```

This command copies the `config_files` directory to `/etc/backup` with elevated privileges, which may be necessary when copying to system directories or restricted locations.

---

## **Summary**

In this chapter, we covered:  
- How to copy directories using the `cp` command with the `-R` option.  
- How to specify a different name for the copied directory.  
- Verifying that the directory and its contents were copied successfully.

Mastering the `cp` command with the `-R` option is crucial for managing directories and creating backups or duplicating files within a Linux system.

---
