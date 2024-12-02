*Module 2: System Access and File Management*
# Accessing Linux Machine via SSH

## Introduction  
In this chapter, we will explore how to access a Linux machine remotely through different platforms: Windows SSH client, Mac Terminal, and Linux Terminal. SSH (Secure Shell) is a protocol used to securely access and manage remote systems.

**What We Will Learn:**  
- How to access a Linux machine from Windows, macOS, and Linux.
- Finding your Linux machine's IP address.

---

### **1. Accessing Linux Machine via Windows SSH Client**

If you are using Windows 10 or later, you can use the built-in SSH client from the command prompt:

1. **Open the Windows Command Prompt**: Type `cmd` in the search bar and hit Enter.
2. **Verify SSH Installation**: Type `ssh` and press Enter. If you see a list of options, SSH is installed.
3. **Connect to the Linux Machine**:
   - **Option 1** (using `-l`):
     ```bash
     ssh -l <username> <IP_address>
     ```
   - **Option 2** (using `@`):
     ```bash
     ssh <username>@<IP_address>
     ```
   - **Example**:
     - Using `-l`:
       ```bash
       ssh -l anupmoitra 10.253.1.22
       ```
     - Using `@`:
       ```bash
       ssh anupmoitra@10.253.1.22
       ```

   - Enter your password when prompted, and you will be logged into the Linux machine.

**Screenshot Example**:  
*Windows Command Prompt for SSH connection*  
![Windows SSH Command](screenshots/04-windows-ssh-connection.png)  
*The terminal prompt showing successful login.*

---

### **2. Accessing Linux Machine via Mac Terminal**

For Mac users, follow these steps to connect using Terminal:

1. **Open Terminal**: Use the Spotlight search (Cmd + Space) and type `Terminal`, then hit Enter.
2. **Connect to the Linux Machine**:
   - **Option 1** (using `-l`):
     ```bash
     ssh -l <username> <IP_address>
     ```
   - **Option 2** (using `@`):
     ```bash
     ssh <username>@<IP_address>
     ```
   - **Example**:
     - Using `-l`:
       ```bash
       ssh -l anupmoitra 10.253.1.22
       ```
     - Using `@`:
       ```bash
       ssh anupmoitra@10.253.1.22
       ```

   - Enter your password when prompted, and you will be connected to the Linux machine.

**Screenshot Example**:  
*Mac Terminal showing the SSH command*  
![Mac Terminal SSH Command](screenshots/04-mac-terminal-ssh.png)  
*Connected session in Terminal.*

---

### **3. Accessing Linux Machine via Linux Terminal**

If you are using Linux, the process is similar to macOS:

1. **Open Terminal**: Press Ctrl + Alt + T or search for Terminal in your applications.
2. **Connect to the Linux Machine**:
   - **Option 1** (using `-l`):
     ```bash
     ssh -l <username> <IP_address>
     ```
   - **Option 2** (using `@`):
     ```bash
     ssh <username>@<IP_address>
     ```
   - **Example**:
     - Using `-l`:
       ```bash
       ssh -l anupmoitra 10.253.1.22
       ```
     - Using `@`:
       ```bash
       ssh anupmoitra@10.253.1.22
       ```

   - Enter your password when prompted to complete the connection.

**Screenshot Example**:  
*Linux Terminal displaying SSH connection*  
![Linux Terminal SSH Command](screenshots/04-linux-terminal-ssh.png)  
*Successful login to the Linux machine.*

---

### **4. Finding the IP Address of the Linux Machine**

Before connecting, you need to find the IP address of your Linux machine:

1. **Access the Linux Console**: Open your virtual machine or physical machine running Linux.
2. **Run the Command**:
   - For most recent Linux distributions, use:
     ```bash
     ip addr
     ```
   - Older distributions may use:
     ```bash
     ifconfig
     ```
3. **Identify the IP Address**:
   - Look for the `enp0S3` or equivalent interface and note the IP address (e.g., `10.253.1.22`).
   - If `ifconfig` is not available, install it using:
     ```bash
     sudo yum install net-tools
     ```

**Screenshot Example**:  
*Command output displaying the IP address*  
![Find IP Address](screenshots/04-find-ip-address.png)  
*Identify the correct network interface and IP address.*

---

## **Conclusion**

Accessing a Linux machine is seamless, whether you’re on Windows, macOS, or Linux. You can use either `ssh -l <username> <IP_address>` or `ssh <username>@<IP_address>` formats, and both will work for your remote connection needs. Ensure that you have the correct IP address and credentials for a successful connection.

**Note**: Always use a strong password or consider setting up SSH keys for better security.

---
