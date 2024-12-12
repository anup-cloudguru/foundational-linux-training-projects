# **Linux Command Cheat Sheet**

## **Basic Commands**

- **`pwd`** – Print the current working directory.
  ```bash
  pwd
  ```

- **`cd`** – Change the current directory.
  ```bash
  cd /path/to/directory   # Navigate to a specific directory
  cd ..                    # Go back one directory level
  cd ~                     # Go to the home directory
  ```

- **`ls`** – List the contents of a directory.
  ```bash
  ls                     # List files in the current directory
  ls -l                  # List with detailed information
  ls -lt                 # List sorted by modification time
  ls -ltr                # List in reverse order of modification time
  ```

## **File and Directory Management**

- **`cp`** – Copy files and directories.
  ```bash
  cp file1.txt file2.txt  # Copy file1.txt to file2.txt
  cp -R dir1 /home/anupmoitra/dir2  # Copy dir1 to dir2, including all subdirectories and files
  ```

- **`mv`** – Move or rename files and directories.
  ```bash
  mv file1.txt /path/to/destination  # Move file1.txt to a new location
  mv old_dir new_dir                 # Rename directory
  ```

- **`rm`** – Remove files or directories.
  ```bash
  rm file1.txt                      # Remove a file
  rm -r dir1                         # Remove a directory and its contents
  ```

- **`mkdir`** – Create a new directory.
  ```bash
  mkdir new_directory               # Create a new directory
  ```

## **Finding IP Address**

- **`ip a`** – Show IP address information.
  ```bash
  ip a                             # Display all network interfaces and their IP addresses
  ```

- **`ifconfig`** – (Deprecated but still works) Display network interfaces and their IP addresses.
  ```bash
  ifconfig                         # Show network interfaces and IP details
  ```

## **Accessing Linux via SSH**

- **`ssh`** – Secure Shell to access remote systems.
  ```bash
  ssh user@hostname_or_ip         # Access a remote system via SSH (replace 'user' and 'hostname_or_ip')
  ssh username@192.168.1.100      # Example with IP address
  ```

- **`whoami`** – Display the current logged-in username.
  ```bash
  whoami
  ```

## **Directory Navigation and Exploration**

- **`ls`** – List the contents of a directory.
  ```bash
  ls /home/anupmoitra              # List the contents of /home/anupmoitra
  ls -l                            # Detailed list of files and directories
  ```

- **`cd`** – Change directory.
  ```bash
  cd /path/to/directory            # Navigate to a specific directory
  ```

## **Copying Directories**

- **`cp -R`** – Copy directories and their contents recursively.
  ```bash
  cp -R source_directory destination_directory
  cp -R dir1 /home/anupmoitra/dir2  # Copy dir1 to /home/anupmoitra/dir2
  ```

---
