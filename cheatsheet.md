# **🐧 Beginner's Guide to Linux Commands** 🛠️

---

## **🔧 Basic Network Commands**

- **`ip a`** – View your network interfaces and IP addresses.  
  ```bash
  ip a              # Shows all network details
  ```

- **`hostname -I`** – Show your system’s IP addresses.  
  ```bash
  hostname -I       # Displays your system’s IP addresses
  ```

- **`ssh`** – Connect securely to another computer.  
  ```bash
  ssh user@hostname_or_ip           # Connect to a remote system
  ```

---

## **⎸️ Stopping a Running Command**

- **`Ctrl + C`** – Stop a command or process that’s running.  
  Simply press `Ctrl + C` on your keyboard to interrupt a command or process.

---

## **📁 Navigating the File System**

- **`pwd`** – Find out where you are.  
  ```bash
  pwd                                # Prints the current directory path
  ```

- **`cd`** – Move to a different directory.  
  ```bash
  cd /path/to/directory             # Go to a specific folder
  cd                                # Go to your home folder
  cd ..                             # Go back one level
  cd /                              # Go to the root folder
  ```

- **`ls`** – List files and folders.  
  ```bash
  ls                                # Show what's in the current folder
  ls -l                             # Show more details about files
  ls -lt                            # Sort files by date (newest first)
  ```

---

## **📄 Creating and Editing Files**

### **Creating Empty Files**
- **`touch`**  
  ```bash
  touch filename                    # Create an empty file
  ```

- **`echo`**  
  ```bash
  echo "" > filename                # Create an empty file
  ```

### **Adding Content to Files**
- **`echo`**  
  ```bash
  echo "Hello, World!" > filename   # Create a file with content
  ```

- **`cat`**  
  ```bash
  cat > filename                    # Create a file and add content (Press Ctrl + D to save)
  ```

### **Editing Files Directly**
- **`nano`**  
  ```bash
  nano filename                     # Open the file in Nano (easy to use)
  ```

- **`vi`** / **`vim`**  
  ```bash
  vi filename                       # Open the file in Vi editor (advanced users)
  vim filename                      # Open in Vim (an improved version of Vi)
  ```

---

## **🔑 Changing Passwords**

- **`passwd`** – Update your password.  
  ```bash
  passwd                            # Change your own password
  sudo passwd username              # Change another user’s password (requires sudo)
  ```

---

### **Explanation for Beginners**

1. **Network Commands**  
   Use `ip a` to check your computer’s network setup and `hostname -I` to find your IP address. Use `ssh` to connect securely to another computer.

2. **Stopping Commands**  
   If you run a command that gets stuck or takes too long, press `Ctrl + C` to stop it.

3. **Navigating Folders**  
   - `pwd` tells you where you are in the file system.
   - `cd` lets you move between folders. For example, `cd ..` moves you up one level.
   - `ls` shows the files and folders in your current location.

4. **Working with Files**  
   - Use `touch` or `echo ""` to create empty files.
   - Use `echo "text"` or `cat >` to create files with content.
   - Edit files directly with `nano` (best for beginners) or `vi/vim` (for advanced users).

5. **Changing Passwords**  
   Use `passwd` to change your password. Admins can use `sudo passwd username` to reset another user’s password.

---
