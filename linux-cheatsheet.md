# 🐧 **Beginner's Guide to Linux Commands**

---

## 🔧 **Basic Network Commands**

### **`ip a`** or **`ip addr`** – View Your Network Interfaces & IP Addresses
A modern command to check your network details.

```bash
ip a              # Short form for network details
ip addr           # Full form for network details
```

### **`ifconfig`** – (Legacy Command) View Your Network Interfaces & IP Addresses  
Though older, `ifconfig` still works but is being replaced by `ip` on modern systems.

```bash
ifconfig          # Legacy command to show network details
```

### **`hostname -I`** – Show All IP Addresses of Your System  
Quickly see all the IP addresses assigned to your system.

```bash
hostname -I       # Displays all system IP addresses
```

---

## 🔐 **Accessing Linux via SSH**

### **`ssh`** – Secure Shell to Access Remote Systems  
Use this command to securely connect to another computer over a network. You’ll need the remote system’s IP address or hostname.

```bash
ssh user@hostname_or_ip           # Access a remote system via SSH
ssh -l username hostname_or_ip    # Specify the username explicitly
```

---

## ⏰ **Power Management** 
### **`sudo shutdown`** – Schedule or Perform System Shutdown
Use this command to schedule or immediately shut down the system.

```bash
sudo shutdown                      # Schedules shutdown 1 minute from now (default)
sudo shutdown +10                  # Schedules shutdown in 10 minutes
sudo shutdown 23:00                # Schedules shutdown at 11:00 PM
sudo shutdown now                  # Shut down the system immediately
sudo shutdown -c                   # Cancel a scheduled shutdown
```

### **`sudo reboot`** – Schedule or Perform System Reboot
Use this command to reboot the system immediately or schedule a reboot.

```bash
sudo reboot                         # Reboot immediately
sudo shutdown -r +10                # Schedule a reboot in 10 minutes
sudo shutdown -r 23:00              # Schedule a reboot at 11:00 PM
```

---

## ⎸️ **Interrupt a Running Command or Process**

### **`Ctrl + C`** – Stop a Running Command or Process  
If you accidentally run a command that takes too long or gets stuck, press `Ctrl + C` to regain control of the terminal.

```bash
# Press Ctrl + C to stop a running process
```

---

## 📁 **Navigating the File System**

### **`pwd`** – Print the Current Working Directory  
This shows the full path of the directory you’re currently in.

```bash
pwd
```


### **`cd`** – Change the Current Directory  
Navigate through folders in the file system using these commands:

```bash
cd /path/to/directory             # Go to a specific directory
cd ..                             # Go back one directory level
cd                                # Go to the home directory
cd /                              # Go to the root directory
```

### **`ls`** – List the Contents of a Directory  
View files and directories in your current location:

```bash
ls                                # Basic list of files
ls -l                             # Detailed listing
ls -lt                            # Sort by modification time
ls -ltr                           # Reverse order of modification time
```

---

## 📄 **Creating and Editing Files** ✍️

### **Creating Empty Files**

#### **`touch`** – Create a Blank File  
Use this command to create an empty file.

```bash
touch filename                     # Create an empty file
```

---

#### **`echo`** – Create a Blank File  
Another way to create a blank file using `echo`.

```bash
echo "" > filename                 # Create a blank file
```

---

### **Adding Content to Files**

#### **`echo`** – Create a File with Content  
Use this command to create a file and add content at the same time.

```bash
echo "Hello, World!" > filename    # Create a file with content
```

#### **`cat`** – Write or View File Content  
Use `cat` to write content to a file or view its content.

```bash
cat > filename                     # Write content to a file (Ctrl + D to save)
cat filename                       # View content of a file
cat >> filename                    # Append content to an existing file
```

### **Editing Files Directly**

#### **`nano`** – Beginner-Friendly Text Editor  
A simple text editor for beginners.

```bash
nano filename                      # Open a file in Nano editor
```

#### **`vi` / `vim`** – Advanced Text Editors  
`vi` and `vim` are powerful text editors for advanced users.

```bash
vi filename                        # Open a file in Vi editor
vim filename                       # Open a file in Vim editor
```

---
