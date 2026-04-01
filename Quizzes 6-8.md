## Quiz 6: Boot Process & Virtualization

**Question 1: What does POST stand for in the context of the boot process?**

- **Answer:** Power-On Self-Test
    

**Question 2: What is the purpose of the bootloader in the boot process?**

- **Answer:** Load the operating system kernel into memory
    

**Question 3: Which of the following is the correct order of the boot process steps in a typical PC?**

- **Answer:** POST, BIOS/UEFI initialization, bootloader, kernel initialization
    

**Question 4: Which keyboard key is commonly used to access the BIOS/UEFI setup utility during the boot process?**

- **Answer:** Del / Delete
    

**Question 5: Match the statements to whether they associate with BIOS or UEFI**

- Supports MBR partitioning scheme: **1 (BIOS)**
    
- Supports GPT partitioning scheme: **2 (UEFI)**
    
- Typically has a text-based interface with limited options: **1 (BIOS)**
    
- Offers a graphical user interface (GUI) with mouse support: **2 (UEFI)**
    
- Offers secure boot to validate bootloader and driver signatures: **2 (UEFI)**
    
- Limited security features: **1 (BIOS)**
    

**Question 6: Which type of hypervisor runs directly on the physical hardware without the need for a host operating system?**

- **Answer:** Type 1
    

**Question 7: I have a host system with 12 (virtual) CPU cores and 16 GB of RAM. My host OS needs a minimum of 2 CPU cores and 4 GB of RAM. I am building virtual machines that require 2 CPU cores and 4 GB of RAM. How many virtual machines can my host host (have turned on) at once?**

- **Answer:** 3
    
    > _Calculation: (16GB total - 4GB host) / 4GB per VM = 3 VMs._
    

**Question 8: What technology allows and manages one or more virtual machines to run concurrently on a single physical machine?**

- **Answer:** Hypervisor
    

**Question 9: Virtual machines can still access the Internet via the host machine.**

- **Answer:** True
    

**Question 10: I have a host system with 1 TB (~1000 GB) of disk space. My host needs 100 GB of disk space. I am building virtual machines that require 20 GB of disk space. How many virtual machines can I create on my host?**

- **Answer:** 45
    
    > _Calculation: (1000GB total - 100GB host) / 20GB per VM = 45 VMs._
    

---

## Quiz 7: Disks & Filesystems

**Question 2: Which command-line utilities can view and manage partition tables in Linux systems?**

- **Answers:** fdisk, parted, gdisk
    

**Question 3: What is a partition table in the context of computer systems?**

- **Answer:** It is a table that stores information about disk partitions
    

**Question 4: Select the facts about each partition table type (1: GPT, 2: MBR)**

- Supports a maximum of 4 primary partitions: **2 (MBR)**
    
- Support disks sizes less than 2 TB: **2 (MBR)**
    
- Common to BIOS based motherboards: **2 (MBR)**
    
- Supports up to 128 partitions: **1 (GPT)**
    
- GUID (Globally Unique Identifier) Partition Table: **1 (GPT)**
    
- Separately stores the bootloader on an EFI partition: **1 (GPT)**
    
- Master Boot Record: **2 (MBR)**
    
- Common to UEFI based motherboards: **1 (GPT)**
    
- Stored in first sector (512 bytes) of a disk: **2 (MBR)**
    
- Supports disk sizes greater than 2 TB: **1 (GPT)**
    

**Question 5: In the context of disks, what is a partition?**

- **Answer:** A section of a hard disk or storage device
    

**Question 6: Correctly order the unit sizes of data from smallest (1) to largest (6)**

1. bit
    
2. byte
    
3. kilobyte
    
4. megabyte
    
5. gigabyte
    
6. terabyte
    

**Question 7: What is fragmentation in the context of filesystems?**

- **Answer:** The process of files becoming scattered across a disk
    

**Question 8: Which filesystem is commonly used in macOS and OS X?**

- **Answer:** HFS+
    

**Question 9: Which filesystem is commonly used in Windows operating systems?**

- **Answer:** NTFS
    

**Question 10: Which filesystem is commonly used in Linux operating systems?**

- **Answer:** Ext4
    

**Question 11: All filesystems store metadata, such as user / group ownership and permissions as well as created and modified dates.**

- **Answer:** False
    

**Question 12: Once a file is removed from the filesystem, using a command like `rm`, it can no longer be read from the disk - the data is automatically overwritten on the disk.**

- **Answer:** False
    

**Question 13: Select the information that inodes store**

- **Answers:** File size, File permissions, Last file access & file creation time, File links (hard links) pointing to the inode, File pointers to data blocks on the disk where the actual file contents are stored.
    

---

## Quiz 8: Linux Processes

**Question 1: In Linux, what is the unique identifier for a process?**

- **Answer:** Process ID (PID)
    

**Question 2: Select the metadata items associated with processes**

- **Answers:** process state, parent process ID, user & group ID, process ID, memory & cpu usage.
    

**Question 3: Match the process state with its definition**

- Process waiting for an event: **2 (S - Sleeping)**
    
- Process is in a stopped state: **4 (T - Stopped)**
    
- Process is in an uninterruptable state while waiting on an event: **5 (D - Uninterruptible Sleep)**
    
- Process is running: **1 (R - Running)**
    
- Process is terminated, but has not been cleaned up by parent process: **3 (Z - Zombie)**
    

**Question 4: If a child's parent process is terminated, what process adopts it?**

- **Answer:** systemd
    

**Question 5: Match the signal type to its description and ways to send the signal to the process**

- kill PID: **1 (SIGINT / SIGTERM)**
    
- Signal to interrupt process and gracefully terminate: **1 (SIGINT / SIGTERM)**
    
- Signal to stop a process - process can be resumed: **3 (SIGSTOP / SIGTSTP)**
    
- kill -19 PID: **3 (SIGSTOP / SIGTSTP)**
    
- With process in foreground, use CTRL + C: **1 (SIGINT / SIGTERM)**
    
- Signal to forcefully terminate a process: **2 (SIGKILL)**
    
- kill -9 PID: **2 (SIGKILL)**
    
- With process in foreground, use CTRL + Z: **3 (SIGSTOP / SIGTSTP)**
    

**Question 6: How can you start a background process in Linux?**

- **Answer:** Using the & symbol at the end of a command
    

**Question 7: Background processes continue running if the controlling terminal is exited.**

- **Answer:** False
    

**Question 8: What is the tmux prefix key combination to manage the session?**

- **Answer:** CTRL + B
    

**Question 9: Match the systemctl command with its definition**

- Adjust the system's behavior regarding service initiation during the boot process: **4 (systemctl enable / disable)**
    
- Useful for applying configuration changes or refreshing the service without rebooting: **3 (systemctl reload / restart)**
    
- Control the operational state of services: **2 (systemctl start / stop)**
    
- Provides detailed information about a service: **1 (systemctl status)**