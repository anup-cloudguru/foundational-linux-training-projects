# **🐧 Beginner's Guide to Linux Commands** 🛠️

---

## **🔧 Basic Network Commands**

- **`ip a`** (or **`ip addr`**) – View your network interfaces and IP addresses.  
  These commands help you see details about your computer's network connections.
  ```bash
  ip a              # Shows network details using the shorthand 'ip a'
  ip addr           # The full version of 'ip a', shows the same information
  ```

- **`ifconfig`** – (Old command, still works) View your network interfaces and IP addresses.  
  Although it's outdated, it’s still used on some systems. It’s being replaced by `ip`.
  ```bash
  ifconfig          # Displays network details
  ```

- **`hostname -I`** – Show all the IP addresses of your system.  
  This command is useful when you want to quickly see all the network addresses your computer has.
  ```bash
  hostname -I       # Shows the system’s IP addresses
  ```

---

## **🔐 Accessing Linux via SSH**

- **`ssh`** – Secure Shell to access remote systems.  
  Use this to connect securely to another computer over a network. You'll need the remote system’s IP address or hostname.
  ```bash
  ssh user@hostname_or_ip           # Access a remote system via SSH
  ssh -l username hostname_or_ip    # Specify the username explicitly
  ```

---

## **⎸️ Interrupt a Running Command or Process**

- **`Ctrl + C`** – Stop a running command or process.  
  If you accidentally run a command that’s taking too long or is stuck, you can regain control of the terminal by pressing `Ctrl + C`.
  ```bash
  # Press Ctrl + C to stop a running process
  ```

---

## **📁 Navigating the File System**

- **`pwd`** – Print the current working directory.  
  Use this command to see the full path of the directory you’re currently in.
  ```bash
  pwd
  ```

- **`cd`** – Change the current directory.  
  Navigate to different directories in the file system using these commands:
  ```bash
  cd /path/to/directory             # Navigate to a specific directory
  cd ..                             # Go back one directory level
  cd                                # Go to the home directory
  cd /                              # Go to the root directory
  ```

- **`ls`** – List the contents of a directory.  
  View files and directories in the current location. You can use these options for more details:
  ```bash
  ls                                # List files in the current directory
  ls -l                             # Detailed listing
  ls -lt                            # Sort by modification time
  ls -ltr                           # Reverse order of modification time
  ```

---

## **🔑 Changing User Passwords**

- **`passwd`** – Change user passwords.  
  Use this to change your own password or another user’s password (requires sudo for other users).
  ```bash
  passwd                            # Change your own password
  sudo passwd username              # Change another user's password (requires sudo)
  ```

---
