# **🐧 Beginner's Guide to Linux Network Commands** 🛠️

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
