*Module 2: System Access and File Management*
# Accessing Linux Systems

In this chapter, we will delve into the two primary methods of accessing a Linux system: **Console Access** and **Remote Access**.

---

### **What We Will Learn**  
- The distinctions between Console Access and Remote Access.  
- How to use the console for direct access to a Linux system.  
- The process of connecting to a Linux system remotely using tools like PuTTY and SSH.  

---

### **Types of Access**

#### 1. **Console Access**  
Console access involves directly interacting with the operating system through a physical connection to the machine.

- **Example Setup**:  
  - Connect the system to a monitor using cables such as VGA, HDMI, or DVI.  
  - This method is applicable to both physical machines and virtual machines (via virtual console).

- **Use Cases**:  
  - Accessing the system during initial installation.  
  - Conducting direct troubleshooting or system maintenance when remote access isn’t feasible.

- **Console Access in Virtual Machines**:  
  - For virtual machines, the hypervisor (e.g., VirtualBox) provides a virtual console.  
  - This interface allows direct interaction with the Linux VM.

---

#### 2. **Remote Access**  
Remote access refers to connecting to a Linux system over a network from another computer.

- **Why Remote Access Is Important**:  
  - It is the primary mode of connection in corporate environments.  
  - Enables server management without needing physical access.

- **Requirements for Remote Access**:  
  1. **IP Address**: Ensure you have the IP address of the Linux machine you intend to connect to.  
  2. **SSH Client**: Utilize tools like PuTTY (for Windows) or the native SSH clients available in Windows 10+, macOS, and Linux.

---

### **How to Connect Remotely**

#### **Using PuTTY (Windows)**  
1. Download and install **PuTTY** from the [PuTTY Official Website](https://www.putty.org/).  
2. Open PuTTY and:  
   - Enter the **IP address** of the Linux machine in the "Host Name" field.  
   - Keep the default port as **22** (for SSH).  
3. Click **Open** to initiate the SSH session.  
4. Log in with the username and password for the Linux system.  

#### **Using Built-in SSH (Windows 10+/macOS/Linux)**  
1. Open the **Command Prompt (Windows)** or **Terminal (macOS/Linux)**.  
2. Use the following command to connect:
   ```bash
   ssh <username>@<IP_address>
   ```
   - Replace `<username>` with your Linux system’s username.
   - Replace `<IP_address>` with the system’s IP address.
3. Enter the password when prompted to establish the SSH connection.

**Example Command**:
```bash
ssh root@192.168.1.100
```

**Important Notes**:
- **No GUI in Remote Access**: When connecting via SSH, interaction is limited to the command line (CLI).
- **Default SSH Port**: The default port for SSH is 22. Ensure this port is open in the firewall.
- **Built-in SSH Support**:
  - Windows 10 and newer versions come with a built-in SSH client, eliminating the need for PuTTY.
  - macOS and Linux also include native SSH support.

---

### **Conclusion**  
In this chapter, we examined the fundamentals of accessing a Linux system through console and remote methods. Remote access, especially via SSH, is a crucial practice in professional settings for efficient server management.

In the next chapter, we will dive into the Linux File System Structure, covering how to navigate and manage files and directories.

---
