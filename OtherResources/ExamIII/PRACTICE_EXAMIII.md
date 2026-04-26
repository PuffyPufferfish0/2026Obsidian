## 1. Intro Topics

**Shells**

- **Windows**: PowerShell (modern, object-oriented), CMD (legacy command prompt).
    
- **Linux/Mac**: `bash` (Bourne Again Shell, default on most Linux), `sh` (legacy standard), `zsh` (Z shell, default on modern macOS).
    

**SSH (Secure Shell)**

- **Structure**: `ssh -i [path/to/private_key] [username]@[hostname_or_ip]`
    
- **Private Key Files**: Typically named `id_rsa` or `id_ed25519` or end in `.pem`. These must _never_ be shared. Permissions must be strict (`chmod 400` or `600`), otherwise SSH will refuse to use them.
    
- **Public Keys & `authorized_keys`**: Public keys (`.pub`) are safely shared. To allow a user to log in to a server, their public key is appended to the `~/.ssh/authorized_keys` file on the remote server.
    

## 2. Files, Directories, and OS Structure

**Filesystem Structure**

- **Linux/Mac**: Root-based (`/`). Everything branches from the root.
    
- **Windows**: Drive-letter based (`C:\`, `D:\`).
    

**Ownership & Sharing (Linux)**

- **Permissions**: Read (`r` = 4), Write (`w` = 2), Execute (`x` = 1).
    
- **Categories**: User (Owner), Group, Other (World).
    
- **Commands**:
    
    - `chmod`: Change permissions (e.g., `chmod 755 file`).
        
    - `chown`: Change owner (e.g., `chown user:group file`).
        
    - `adduser` / `deluser`: Manage users.
        
- **Sudo vs Root**: `sudo` allows a regular user to execute a command with administrative privileges temporarily. `root` is the absolute superuser account.
    

## 3. Scripting

**Environment Variables** Variables maintained by the OS/Shell that dictate system behavior.

- `$HOME`: Path to the current user's home directory.
    
- `$USER`: The current logged-in user.
    
- `$SHELL`: The path to the active shell executable.
    
- `$PATH`: A colon-separated list of directories the shell searches to find executable commands.
    

**Execution Methods**

- `source script.sh` or `. script.sh`: Executes in the _current_ shell environment (can change current env vars).
    
- `bash script.sh`: Runs a new bash subshell.
    
- `./script.sh`: Uses the `#!` (shebang, e.g., `#!/bin/bash`) at the top of the file to determine the interpreter.
    

**Bash Scripting Basics**

- **Variables**: Defined without spaces (`var="hello"`). Accessed with `$` (`echo $var`).
    
- **Conditionals**: `if [ "$val" -eq 5 ]; then ... fi`.
    
- **Loops**: `for`, `while`.
    
- **`getopts`**: Built-in tool for parsing command-line flags (like `-a` or `-b`).
    

**Text Processing**

- `grep`: Searches text for regular expression patterns.
    
- `sed`: Stream editor. Great for find-and-replace (`sed 's/find/replace/g'`).
    
- `awk`: Data extraction tool, treats lines as records and columns as fields (`awk '{print $1}'`).
    

## 4. Computer Hardware & VMs

- **CPU**: Central Processing Unit; executes instructions.
    
- **RAM**: Random Access Memory; volatile short-term memory where active processes live.
    
- **Storage**: HDD (spinning disks), SSD (flash memory, faster), NVMe (flash memory over PCIe, fastest).
    
- **VMs (Virtual Machines)**: A software-based computer. Requires a **Hypervisor** to allocate host resources (CPU, RAM, Disk) to the guest VM.
    

## 5. Boot Process

1. **BIOS/UEFI**: Firmware that initializes hardware.
    
2. **POST**: Power-On Self-Test (checks RAM, CPU).
    
3. **Bootloader**: Software (like GRUB) that loads the operating system kernel into memory.
    
4. **Kernel**: Core of the OS. Takes over hardware control.
    
5. **OS / init**: Starts background services (daemons) and user space (`systemd`).
    

## 6. Filesystems & Disks

- **Partition Tables**: **MBR** (Master Boot Record, older, max 2TB) vs **GPT** (GUID Partition Table, modern, massive limits). Tools: `fdisk`, `parted`.
    
- **Inodes**: Data structures holding metadata about a file (permissions, owner, physical location on disk). They do _not_ contain the file name.
    
- **Links**:
    
    - _Hard link_: Points directly to the inode. If the original file is deleted, the data persists via the hard link.
        
    - _Symbolic (Symlink)_: Points to the _name_ of another file. If the original file is deleted, the symlink breaks (dangles).
        
- **Mounting**: Attaching a filesystem to a directory (the mount point) so it can be accessed. `fstab` automates this on boot.
    

## 7. Process Control

- **Terminology**:
    
    - _Process_: A running instance of a program.
        
    - _Daemon_: A background service process.
        
- **States**: Running, Sleeping, Stopped, Zombie (dead but parent hasn't acknowledged), Orphan (parent died, adopted by `init`).
    
- **Metadata**: PID (Process ID), PPID (Parent Process ID).
    
- **Systemd**: Modern Linux init system. Managed via `systemctl` (start, stop, enable, status) and logs are viewed with `journalctl`.
    

## 8. Programming & Compilation

- **Interpreted vs Compiled**: Interpreted languages (Python, Bash) read and execute code line-by-line. Compiled languages (C, C++) convert source code entirely into machine code before execution.
    
- **C/C++ Compilation Steps**:
    
    1. _Pre-processor_: Handles `#include` and macros.
        
    2. _Compiler_: Translates to assembly language.
        
    3. _Assembler_: Translates assembly to object code (binary).
        
    4. _Linker_: Links object code with libraries to create the final Executable (ELF on Linux, EXE on Windows).
        
- **Makefiles**: Automate compilation using targets, dependencies, and actions.
    

## 9. Networking

- **Physical Layer / NIC**: Network Interface Card. Hardware that connects to the network. Identified locally by a physical MAC address.
    
- **IP Addresses (IPv4)**: Logical addresses for routing.
    
    - _DHCP_: Automatically assigns IP addresses to devices.
        
    - _NAT_: Network Address Translation. Maps a single public IP to multiple private IPs on a local network.
        
- **DNS**: Domain Name System. Translates URLs (google.com) to IPs (8.8.8.8).
    
- **Sockets & Ports**: An IP address gets you to the correct computer; a Port (e.g., 80 for HTTP, 22 for SSH) gets you to the correct application. An IP + Port = A Socket.
    
- **Firewalls**: Define Inbound (ingress) and Outbound (egress) rules to block or allow traffic based on IPs and Ports.
    

## 10. Git (Version Control)

- **Basic Commands**:
    
    - `clone`: Download a repo.
        
    - `add`: Stage changes.
        
    - `commit`: Save staged changes with a message.
        
    - `push`: Upload commits to remote (GitHub).
        
    - `pull`: Download and merge remote changes.
        
- **`.gitignore`**: A file specifying patterns for files that Git should intentionally leave untracked (e.g., compiled `.exe` files, log files).