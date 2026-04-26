# Exam 2 Study Guide: Questions and Answers

## 1. Shells

**Q1: Which of the following is a shell used in Linux?**

- **Answer:** bash / Z shell
    

**Q2: Which shell is commonly used in Windows for command-line operations?**

- **Answer:** PowerShell
    

**Q3: What is the default shell for most modern Linux distributions?**

- **Answer:** bash
    

---

## 2. SSH (Secure Shell)

**Q4: What is the primary use of SSH?**

- **Answer:** To establish a secure, encrypted connection to remote systems
    

**Q5: Which of the following is a requirement for SSH authentication?**

- **Answer:** Public and private key pairs
    

**Q6: When using SSH key authentication, which key should NEVER be shared?**

- **Answer:** Private key
    

**Q7: What is the default port for SSH connections?**

- **Answer:** 22
    

---

## 3. Files, Directories, and OS Structure

**Q8: What command is used to list files and directories in Linux?**

- **Answer:** ls
    

**Q9: What command creates a new directory in Linux?**

- **Answer:** mkdir
    

**Q10: What command is used to remove a file in Linux?**

- **Answer:** rm
    

**Q11: Which command in Linux is used to copy files?**

- **Answer:** cp
    

**Q12: What does the `pwd` command do?**

- **Answer:** Prints the working directory
    

**Q13: Which command would you use to move a file from one location to another?**

- **Answer:** mv
    

---

## 4. Scripting

**Q14: Which of the following is a common shell used in Linux scripting?**

- **Answer:** Bash
    

**Q15: What is the correct syntax to define a variable in Bash?**

- **Answer:** `name="John"`
    

**Q16: What line should appear at the beginning of a bash script to specify the interpreter?**

- **Answer:** `#!/bin/bash`
    

**Q17: What is the correct syntax for an if-else statement in Bash?**

- **Answer:** ```bash if [ "$var" -eq 1 ] then echo "True" else echo "False" fi
    

**Q18: Which operator is used for string comparison in Bash?**

- **Answer:** `==` (or `!=` for inequality)
    

**Q19: Which test operator checks if a number is greater than another in bash?**

- **Answer:** `-gt`
    

**Q20: What is the correct syntax for a `for` loop in Bash?**

- **Answer:** ```bash for i in {1..5}; do echo $i done
    

**Q21: What does a `while` loop do in bash?**

- **Answer:** Repeats commands as long as a condition is true
    

**Q22: How do you check if a file exists in a Bash script?**

- **Answer:** `[ -e filename ]`
    

**Q23: Which command appends output to a file instead of overwriting it?**

- **Answer:** `echo "Hello" >> file.txt`
    

**Q24: What test flag checks if a path is a directory?**

- **Answer:** `-d`
    

**Q25: Which command is used to take user input in a Bash script?**

- **Answer:** `read`
    

**Q26: How would you store user input into a variable called `username` in Bash?**

- **Answer:** `read username`
    

**Q27: What does the `getopts` command do in a bash script?**

- **Answer:** Parses command-line options and arguments
    

---

## 5. Git (Version Control)

**Q28: What does the `git commit -m "message"` command do?**

- **Answer:** Commits staged changes with a descriptive message
    

**Q29: What command is used to check the status of a Git repository?**

- **Answer:** git status
    

**Q30: What does the `git pull` command do?**

- **Answer:** Downloads and merges changes from a remote repository
    

**Q31: Which command would you use to stage files for commit in Git?**

- **Answer:** git add
    

**Q32: What does the `git clone` command do?**

- **Answer:** Downloads a remote repository
    

**Q33: What command shows the commit history of a repository?**

- **Answer:** git log
    

**Q34: If you want to undo changes in your working directory, which command should you use?**

- **Answer:** git restore
    

---

## 6. Linux Commands and Permissions

**Q35: What is the default file extension for bash scripts?**

- **Answer:** .sh
    

**Q36: What does the `chmod` command do in Linux?**

- **Answer:** Changes the permissions of a file
    

**Q37: How can you make a bash script executable?**

- **Answer:** chmod +x script.sh
    

**Q38: What does the `cat` command do in Linux?**

- **Answer:** Displays the content of a file
    

**Q39: What does the `chown` command do?**

- **Answer:** Changes file ownership
    

**Q40: In the permission string `-rwxr-xr--`, what permissions does the group have?**

- **Answer:** Read and execute
    

---

## 7. Command Functionality

**Q41: What does `ls -l` do?**

- **Answer:** Lists files in a long format with detailed information
    

**Q42: What does `chmod 755 script.sh` do?**

- **Answer:** Grants execute permission to everyone, but write permission only to the owner
    

**Q43: What does `grep "error" logfile.txt` do?**

- **Answer:** Searches for the word "error" in logfile.txt and displays matching lines
    

**Q44: What does `df -h` do?**

- **Answer:** Displays disk space usage in human-readable format
    

**Q45: What does `sed 's/cat/dog/g' animals.txt` do?**

- **Answer:** Replaces all occurrences of "cat" with "dog" in animals.txt
    

**Q46: What does `echo "Hello World" > greetings.txt` do?**

- **Answer:** Overwrites greetings.txt with "Hello World"
    

**Q47: What does `head -n 5 myfile.txt` do?**

- **Answer:** Displays the first 5 lines of myfile.txt
    

**Q48: What does the command `tail -f logfile.txt` do?**

- **Answer:** Continuously monitors and displays new lines added to the file
    

**Q49: What does `du -sh /home/user` display?**

- **Answer:** Disk usage summary of /home/user in human-readable format
    

---

## 8. Text Processing Practice (grep, sed, awk)

**Q50: Find all employees in the "Engineering" department.**

- **Answer:** `grep "Engineering" employees.csv`
    

**Q51: Display lines containing "HR" employees.**

- **Answer:** `grep "HR" employees.csv`
    

**Q52: Find employees whose name contains "John".**

- **Answer:** `grep "John" employees.csv`
    

**Q53: Show lines with a salary greater than 70000.**

- **Answer:** `awk -F',' '$4 > 70000' employees.csv`
    

**Q54: Search for employees who joined in the year 2019.**

- **Answer:** `grep "2019" employees.csv`
    

**Q55: What does the `-v` flag do in grep?**

- **Answer:** Inverts the match (shows non-matching lines)
    

**Q56: Replace "HR" with "Human Resources" in the dataset.**

- **Answer:** `sed 's/HR/Human Resources/g' employees.csv`
    

**Q57: Remove the "Marketing" department from the dataset.**

- **Answer:** `sed '/Marketing/d' employees.csv`
    

**Q58: Add a "USD" suffix to all salary values.**

- **Answer:** `sed 's/$/ USD/' employees.csv`
    

**Q59: Swap the "Name" and "Department" columns.**

- **Answer:** `sed -E 's/([^,]+),([^,]+),([^,]+),(.+)/\1,\3,\2,\4/' employees.csv`
    

**Q60: Remove the header row from the file.**

- **Answer:** `sed '1d' employees.csv`
    

**Q61: What does the `-i` flag do in sed?**

- **Answer:** Edits the file in-place
    

**Q62: Print only the names of the employees.**

- **Answer:** `awk -F',' '{print $2}' employees.csv`
    

**Q63: Show the name and salary of employees from the "Engineering" department.**

- **Answer:** `awk -F',' '$3=="Engineering" {print $2, $4}' employees.csv`
    

**Q64: Calculate and print the average salary of all employees.**

- **Answer:** `awk -F',' 'NR > 1 {total+=$4; count++} END {print total/count}' employees.csv`
    

**Q65: Find the highest salary in the dataset.**

- **Answer:** `awk -F',' 'NR > 1 {if($4>max) max=$4} END {print max}' employees.csv`
    

**Q66: Print the names of employees who joined after 2020.**

- **Answer:** `awk -F',' '$5 ~ /^202[1-9]/ {print $2}' employees.csv`
    

**Q67: What does the `-F` flag specify in awk?**

- **Answer:** Field separator
    

**Q68: In awk, what does `NF` represent?**

- **Answer:** Number of fields in current record
    

---

## 9. Process Management

**Q69: What command shows currently running processes?**

- **Answer:** `ps`
    

**Q70: What does the `kill` command do?**

- **Answer:** Sends a signal to a process (typically to terminate it)
    

**Q71: Given a process with PID 1234, write the command to terminate it forcefully.**

- **Answer:** `kill -9 1234`
    

**Q72: What does a zombie process indicate?**

- **Answer:** A process that has completed but still has an entry in the process table
    

**Q73: What does the `top` command do?**

- **Answer:** Displays real-time system resource usage and processes
    

**Q74: In `ps` output, what does the STAT column show?**

- **Answer:** Process state/status
    

---

## 11. Hardware and System Information

**Q83: What does RAM stand for?**

- **Answer:** Random Access Memory
    

**Q84: Which component is responsible for executing program instructions?**

- **Answer:** CPU
    

---

## 13. Disk and Storage Management

**Q89: What command lists block devices?**

- **Answer:** `lsblk`
    

**Q91: Write a command to view the partition table of `/dev/xvda`.**

- **Answer:** `sudo fdisk -l /dev/xvda`
    

**Q93: Which storage technology is typically fastest?**

- **Answer:** NVMe SSD
    

---

## 14. Partition Tables (MBR vs GPT)

**Q94: What is the primary function of a partition table?**

- **Answer:** To define how disk space is divided
    

**Q95: What is the maximum number of primary partitions in MBR?**

- **Answer:** 4
    

**Q96: What is the maximum disk size that MBR supports?**

- **Answer:** 2 TB
    

**Q97: What partition scheme should be used for disks larger than 2TB?**

- **Answer:** GPT
    

**Q98: How does GPT provide redundancy?**

- **Answer:** It stores multiple copies of the partition table
    

**Q99: Which partitioning tool works with both MBR and GPT?**

- **Answer:** `parted`
    

**Q100: What command checks if a disk uses MBR or GPT?**

- **Answer:** `parted -l`
    

**Q101: Which boot firmware is typically paired with GPT?**

- **Answer:** UEFI
    

---

## 15. Filesystems

**Q102: What must you do before creating a filesystem on a partition?**

- **Answer:** Create a partition table and partition
    

**Q103: What command creates an ext4 filesystem on `/dev/sdb1`?**

- **Answer:** `mkfs.ext4 /dev/sdb1`
    

**Q104: What does the `mount` command do?**

- **Answer:** Attaches a filesystem to a directory
    

**Q105: When you unmount a filesystem, is the data deleted?**

- **Answer:** No
    

**Q106: What file contains permanent mount configurations for filesystems to mount at boot?**

- **Answer:** `/etc/fstab`
    

**Q107: What are three common filesystem types?**

- **Answer:** NTFS, FAT32, ext4
    

**Q108: What is the standard filesystem for modern Linux?**

- **Answer:** ext4
    

---

## 16. BIOS and UEFI

**Q110: What does BIOS stand for?**

- **Answer:** Basic Input Output System
    

**Q111: Where does BIOS store the bootloader?**

- **Answer:** In the MBR (first sector of disk)
    

**Q112: Which boot firmware supports Secure Boot?**

- **Answer:** UEFI
    

**Q114: What partition scheme does BIOS typically use?**

- **Answer:** MBR
    

**Q115: Where are bootloaders stored in a UEFI system?**

- **Answer:** EFI System Partition (ESP)
    

---

## 17. Linux Boot Process

**Q116: What is the first process that starts in Linux?**

- **Answer:** systemd/init
    

**Q117: What loads the Linux kernel into memory?**

- **Answer:** Bootloader (GRUB)
    

**Q118: What is the role of initramfs during boot?**

- **Answer:** Provides drivers and tools to mount the root filesystem
    

**Q119: In what order do these boot steps occur?**

- **Answer:** BIOS/UEFI → Bootloader → Kernel → Init system
    

---

## 18. Package Management

**Q121: What does `apt update` do?**

- **Answer:** Refreshes the package list from repositories
    

**Q123: Write a command to install a package named "nginx" using apt.**

- **Answer:** `sudo apt install nginx`
    

---

## 19. PATH and Command Execution

**Q127: What is the PATH environment variable?**

- **Answer:** A list of directories where the system looks for executables
    

**Q128: How do you view the PATH variable?**

- **Answer:** `echo $PATH` or `printenv PATH`
    

**Q129: What character separates directories in the PATH variable?**

- **Answer:** Colon (:)
    

**Q130: If a command is not in your PATH, how can you execute it from the current directory?**

- **Answer:** `./command_name`
    

**Q131: What does the `which` command do?**

- **Answer:** Shows the full path to an executable
    

---

## 20. Aliases and Shortcuts

**Q133: What is an alias in bash?**

- **Answer:** A shortcut name for a command or series of commands
    

**Q134: Write a command to create an alias called "ll" that runs "ls -la".**

- **Answer:** `alias ll='ls -la'`
    

**Q135: Where should you save aliases permanently?**

- **Answer:** `~/.bashrc` (standard) or `~/.bash_aliases`
    

**Q137: If you have a program called "shivermetimbers" but want to type "timbers" instead, what's a good solution?**

- **Answer:** Create an alias
    

---

## 22. Additional System Commands

**Q143: What does the `df` command show?**

- **Answer:** Disk free space
    

**Q146: What does `history | grep ssh` do?**

- **Answer:** Searches command history for lines containing "ssh"
    

**Q147: What does the `man` command do?**

- **Answer:** Shows manual pages for commands
    

---

## 23. File Operations

**Q149: What is the difference between `>` and `>>` in output redirection?**

- **Answer:** `>` overwrites; `>>` appends
    

**Q152: What does the `find` command do?**

- **Answer:** Searches for files and directories
    

---

## 25. Permissions and Security

**Q159: What do the numbers in `chmod 644` represent?**

- **Answer:** Owner: rw-, Group: r--, Other: r--
    

**Q160: What does `sudo` do?**

- **Answer:** Runs a command with superuser privileges
    

**Q161: How do you switch to the root user?**

- **Answer:** `sudo su`, `su root`, or `su -`
    

**Q162: What permission is needed to execute a script?**

- **Answer:** Execute
    

**Q163: What does `chmod u+x file.sh` do?**

- **Answer:** Adds execute permission for the user (owner)
    

---

## 26. BONUS Questions

**Q164: [BONUS] Write a complete command pipeline that lists all `.log` files in `/var/log`, searches for lines containing "ERROR", and counts how many matches are found.**

- **Answer:** `find /var/log -name "*.log" | xargs grep "ERROR" | wc -l`
    

**Q165: [BONUS] Explain what this command does: `sudo find / -name "*.tmp" -type f -mtime +7 -delete`**

- **Answer:** Searches the entire system (/) with root privileges (sudo) for files (-type f) named with a .tmp extension that were modified more than 7 days ago (-mtime +7) and deletes them (-delete).
    

**Q167: [BONUS] What is the difference between a hard link and a symbolic link?**

- **Answer:** A hard link points directly to the inode (data) of the file; a symbolic (soft) link points to the filename/path. If the original file is deleted, the symbolic link breaks, but the hard link remains valid.