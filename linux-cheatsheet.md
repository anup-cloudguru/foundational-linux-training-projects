# 🐧 **Beginner's Guide to Linux Commands**

---

## 🔧 **Basic Network Commands**

### **`ip a`** or **`ip addr`** – View Your Network Interfaces & IP Addresses
A modern command to check your network details.

```bash
ip a              # Short form for network details
ip addr           # Full form for network details
```

---

### **`ifconfig`** – (Legacy Command) View Your Network Interfaces & IP Addresses  
Though older, `ifconfig` still works but is being replaced by `ip` on modern systems.

```bash
ifconfig          # Legacy command to show network details
```

---

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
