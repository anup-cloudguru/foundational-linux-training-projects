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
