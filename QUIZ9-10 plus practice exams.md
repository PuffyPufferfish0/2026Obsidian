# Quiz 10 - Networking - Results
> [!info] if there is a cross through on a multiple choice, the one WITH the cross through is correct. Idk how to make those cool checkboxes without the crossthrough


### Question 1

Translate `00100100` to base 10

**Answer:** 36

**Explanation:** To convert binary to decimal (base 10), you look at the place values of each bit from right to left, which are powers of 2 (128, 64, 32, 16, 8, 4, 2, 1).

- The binary number is: `0 0 1 0 0 1 0 0`
    
- The place values are: `128 64 32 16 8 4 2 1` You only add the place values where there is a `1`. In this case: 32 + 4 = 36.
    

### Question 2

Write the number 175 in 8 binary bits.

**Answer:** 10101111

**Explanation:** To convert decimal to binary, you subtract the largest possible power of 2 until you reach 0.

- 175 - **128** = 47 (Bit 128 is `1`)
    
- 47 is less than 64 (Bit 64 is `0`)
    
- 47 - **32** = 15 (Bit 32 is `1`)
    
- 15 is less than 16 (Bit 16 is `0`)
    
- 15 - **8** = 7 (Bit 8 is `1`)
    
- 7 - **4** = 3 (Bit 4 is `1`)
    
- 3 - **2** = 1 (Bit 2 is `1`)
    
- 1 - **1** = 0 (Bit 1 is `1`) Putting the bits together from 128 to 1 gives us `10101111`.
    

### Question 3

Match the IPv4 addresses with the CIDR notation subnet masks with both their long form subnet mask and with their IPv4 address ranges.

**Options:**

1. `192.168.86.24/0`
    
2. `192.168.86.24/8`
    
3. `192.168.86.24/16`
    
4. `192.168.86.24/24`
    
5. `192.168.86.24/32`
    

**Matches & Explanations:**

- **[5]** `192.168.86.24` (only one IP is on the subnet)
    
    - _Why:_ A `/32` mask means all 32 bits are locked to the network, leaving 0 bits for hosts. It represents a single specific IP address.
        
- **[3]** `192.168.0.0 - 192.168.255.255`
    
    - _Why:_ A `/16` mask locks the first two octets (`192.168.X.X`), leaving the last two open for hosts.
        
- **[4]** `192.168.86.0 - 192.168.86.255`
    
    - _Why:_ A `/24` mask locks the first three octets (`192.168.86.X`), leaving only the last octet (0-255) for hosts.
        
- **[1]** `0.0.0.0` (Subnet mask)
    
    - _Why:_ A `/0` mask means 0 bits are used for the network, which equates to a subnet mask of all zeros.
        
- **[3]** `255.255.0.0`
    
    - _Why:_ A `/16` mask translates to 16 binary `1`s (`11111111.11111111.00000000.00000000`), which is `255.255.0.0`.
        
- **[1]** `0.0.0.0 - 255.255.255.255` (all IPs are hosts)
    
    - _Why:_ A `/0` network includes the entire IPv4 address space.
        
- **[2]** `192.0.0.0 - 192.255.255.255`
    
    - _Why:_ A `/8` mask locks only the first octet (`192.X.X.X`), leaving the remaining three for hosts.
        
- **[2]** `255.0.0.0`
    
    - _Why:_ A `/8` mask translates to 8 binary `1`s (`11111111.00000000.00000000.00000000`), which is `255.0.0.0`.
        
- **[5]** `255.255.255.255`
    
    - _Why:_ A `/32` mask translates to 32 binary `1`s, which is 255 in all four octets.
        
- **[4]** `255.255.255.0`
    
    - _Why:_ A `/24` mask translates to 24 binary `1`s (`11111111.11111111.11111111.00000000`), which is `255.255.255.0`.
        

### Question 4

172.198.210.15 is a valid IPv4 address

- [x] True
    
- [ ] False
    

**Explanation:** An IPv4 address consists of four decimal numbers separated by dots (octets). Each number must be between 0 and 255 (inclusive). Since 172, 198, 210, and 15 all fall within the 0-255 range, this is a valid address.

### Question 5

31.899.233.90 is a valid IPv4 address

- [ ] True
    
- [x] False
    

**Explanation:** The second octet in this address is `899`. Because an octet is 8 bits, its maximum decimal value is `255`. Since 899 is greater than 255, this is an invalid IPv4 address.

### Question 6

Match the networking concepts to their definitions.

**Matches & Explanations:**

- **[5] Protocol**: A set of rules governing the exchange of data between devices. _(Just like a language has grammar rules so people can understand each other, networks use protocols like TCP/IP)._
    
- **[6] MAC Address**: A unique hardware identifier assigned to a network interface controller (NIC). _(This is permanently burned into your network card by the manufacturer)._
    
- **[2] IP address**: A numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication. _(This is your logical address on the network, similar to a street address)._
    
- **[4] Gateway**: A device or software component that connects different networks, allowing data to flow between them. _(Typically your router, which acts as the 'doorway' to the internet)._
    
- **[3] Subnet mask**: A numerical value used to divide an IP address into network and host portions. _(It tells the computer which part of the IP address is the neighborhood and which part is the specific house)._
    
- **[7] Route table**: A data structure that lists available routes to various destinations within a network. _(A map that the router uses to decide where to send packets next)._
    
- **[1] DNS**: A system that translates domain names into IP addresses. _(The "phonebook" of the internet, turning human-readable names like google.com into machine-readable IPs)._
    

### Question 7

Given this output from `ip a`:

```
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:15:5d:32:2b:65 brd ff:ff:ff:ff:ff:ff
    inet 172.26.112.248/20 brd 172.26.127.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::215:5dff:fe32:2b65/64 scope link
       valid_lft forever preferred_lft forever
```

What is the MAC address? **Answer:** `00:15:5d:32:2b:65`

**Explanation:** In Linux network outputs, the MAC address (hardware address) is found on the line starting with `link/ether`. It consists of 6 pairs of hexadecimal digits.

### Question 8

Given this output from `ip a`:

```
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:15:5d:32:2b:65 brd ff:ff:ff:ff:ff:ff
    inet 172.26.118.11/24 brd 172.26.118.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::215:5dff:fe32:2b65/64 scope link
       valid_lft forever preferred_lft forever
```

What is the IPv4 address? **Answer:** `172.26.118.11`

**Explanation:** In the `ip a` command output, IPv4 addresses are listed next to the keyword `inet` (whereas IPv6 addresses are next to `inet6`). The address is `172.26.118.11` (the `/24` is the subnet mask).

### Question 9

Match the ports to the service protocol that commonly runs on them.

**Matches & Explanations:**

- **[2] HTTP**: Runs on port 80. (Standard, unencrypted web traffic).
    
- **[1] SSH**: Runs on port 22. (Secure Shell, used for secure remote command-line access).
    
- **[3] HTTPS**: Runs on port 443. (Secure, encrypted web traffic).
    

### Question 10

Given this output from `ip a`:

```
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:15:5d:32:2b:65 brd ff:ff:ff:ff:ff:ff
    inet 172.26.118.11/24 brd 172.26.118.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::215:5dff:fe32:2b65/64 scope link
       valid_lft forever preferred_lft forever
```

What is the subnet mask for the CIDR notation? **Answer:** `255.255.255.0`

**Explanation:** The output shows `inet 172.26.118.11/24`. The `/24` means the first 24 bits of the subnet mask are `1`s. `11111111.11111111.11111111.00000000` converts to decimal as `255.255.255.0`.

### Question 11

How can I find the public IPv4 address my network communication is utilizing?

**Answer:** `either hostname -I or curl whatismyip.com (or another website that tells you)`

**Explanation:** While `hostname -I` typically prints the local/private IP addresses configured on the machine interfaces, utilizing a tool like `curl` to reach out to an external server (like `whatismyip.com` or `ifconfig.me`) will cause that server to echo back the public IP address it sees your requests originating from.

### Question 12

Given this output from `ip a`:

```
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:15:5d:32:2b:65 brd ff:ff:ff:ff:ff:ff
    inet 172.26.118.11/24 brd 172.26.118.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::215:5dff:fe32:2b65/64 scope link
       valid_lft forever preferred_lft forever
```

What is the CIDR subnet mask? **Answer:** `24`

**Explanation:** On the `inet` line (`inet 172.26.118.11/24`), the number immediately following the forward slash (`/`) is the Classless Inter-Domain Routing (CIDR) notation.

### Question 13

What is the IPv4 address for www.downloadmoreram.com ?

**Answer:** `172.67.193.114`

**Explanation:** You find this by querying the Domain Name System (DNS). In a terminal or command prompt, you would use a command like `ping www.downloadmoreram.com`, `nslookup www.downloadmoreram.com`, or `dig www.downloadmoreram.com`. The DNS server responds with the IP address associated with that domain.



# Quiz 9 - Compiling & Makefiles - Results

### Question 1

Given source code, the corresponding compiler or interpreter needs to be installed on the system in order to compile and / or run the code.

- [x] True
    
- [ ] False
    

**Explanation:** Source code (like C++ or Python) is written in human-readable text. Computers only understand machine code (binary). To run the code, you must have the specific compiler (to translate the code into a binary executable ahead of time) or an interpreter (to translate and execute it line-by-line on the fly) installed on that machine.

### Question 2

Given the following Makefile contents:

```
hello: code.c
    gcc -E code.c

rainbow:
    gcc -Wall -o prog code.c

batman:
    ./prog
```

What make command will compile source code in `code.c`?

- [ ] `make`
    
- [ ] `make batman`
    
- [ ] `make hello`
    
- [ ] `./code.c`
    
- [x] `make rainbow`
    

**Explanation:** * `make rainbow` runs the command `gcc -Wall -o prog code.c`, which invokes the GCC compiler with all warnings enabled (`-Wall`) and outputs an executable named `prog` (`-o prog`). This is the correct compilation step.

- `make hello` only runs the preprocessor (`-E`), which doesn't fully compile the code.
    
- `make batman` attempts to execute the compiled program (`./prog`).
    

### Question 3

If c/c++ code is compiled in gcc on a Unix / Linux system, the compiled program will run in Windows.

- [ ] True
    
- [x] False
    

**Explanation:** C and C++ compile down to native machine code specific to the operating system's architecture and format (e.g., ELF format for Linux, PE format for Windows). An executable built natively on Linux cannot natively run on Windows without an emulator or compatibility layer (like WSL). To make a Windows executable from Linux, you would need to use a cross-compiler (like MinGW).

### Question 4

A compiled Java program can run on any system with a JVM installed.

- [x] True
    
- [ ] False
    

**Explanation:** This is Java's famous "Write Once, Run Anywhere" (WORA) principle. Java source code is compiled into an intermediate format called "bytecode". This bytecode is not tied to a specific operating system; instead, it is executed by the Java Virtual Machine (JVM). As long as a system has a JVM compatible with that bytecode version, it can run the program.

### Question 5

In order to call the interpreter / compiler without specifying what folder it's located in (for example, typing 'java' instead of the full path to the java virtual machine), the folder the interpreter / compiler is located in need to be listed in what environment variable?

**Answer:** `PATH`

**Explanation:** The `PATH` environment variable contains a list of directory paths. When you type a command in the terminal (like `java`, `gcc`, or `python`), the operating system searches through these directories in order. If it finds an executable with that name in one of the directories, it runs it. Without it, you would have to type out the absolute path every time (e.g., `C:\Program Files\Java\jdk\bin\java.exe`).

### Question 6

How would you install python 3 on your system?

**Answer:** `sudo apt install python3`

**Explanation:** This is the standard command for installing packages on Debian/Ubuntu-based Linux distributions.

- `sudo` grants administrative (root) privileges.
    
- `apt` is the Advanced Package Tool (the package manager).
    
- `install` is the command instructing apt to download and install a package.
    
- `python3` is the name of the package.
    

### Question 7

Correctly order the 4 steps of the C/C++ compilation process

**Matches:**

- **[ 1 ]** pre-processing
    
- **[ 2 ]** compiling
    
- **[ 4 ]** linking
    
- **[ 3 ]** assembling
    

_(Chronological order: 1. Pre-processing -> 2. Compiling -> 3. Assembling -> 4. Linking)_

**Explanation:**

1. **Pre-processing:** Handles directives like `#include` (copying header files) and `#define` (expanding macros) before actual compilation begins.
    
2. **Compiling:** Translates the pure C/C++ code into assembly language specific to the target architecture.
    
3. **Assembling:** Converts the assembly code into machine-level binary code, producing object files (`.o` or `.obj`).
    
4. **Linking:** Takes one or more object files and links them with external libraries to create the final, runnable executable.
    

### Question 8

Commits made on a branch exist on that branch. Other branches will show their respective states of the files based on commits made to those branches until a merge between branches occurs.

- [x] True
    
- [ ] False
    

**Explanation:** In Git, a branch is an isolated line of development. When you commit changes on one branch, it does not affect any other branch. They act as parallel universes. The only way to bring changes from one branch into another is by explicitly performing a `merge` (or a `rebase`).

### Question 9

I am on branch hotfix and need to switch to the main branch. Write a command that will switch me to the main branch.

**Answer:** `git checkout main`

**Explanation:** The `git checkout <branch_name>` command updates the files in your working directory to match the version stored in the specified branch, effectively switching your active environment to that branch. _(Note: In newer versions of Git, `git switch main` is also correct and heavily encouraged)._

### Question 10

I have changes (commits) on branch GUI-dev that need to be merged to the main branch. How can I merge the commits on GUI-dev with those on main?

- [x] (While on the main branch) git merge GUI-dev
    
- [ ] git push --set-upstream origin GUI-dev
    
- [ ] (While on the GUI-dev branch) git merge main
    
- [ ] git merge
    
- [ ] (While on the main branch) git merge main
    
- [ ] (While on the GUI-dev branch) git merge GUI-dev
    

**Explanation:** To merge branches in Git, you must first switch to the "destination" branch (the one that will receive the new code). In this scenario, `main` is the destination. Once on `main`, you use `git merge <source_branch>` to pull the commits from the source branch (`GUI-dev`) into your current branch.



# Practice Exam

## 1. Network Discovery & Testing

**Question:** You are troubleshooting a web server and need to test if the HTTP service is running and view the specific response headers being returned. Which command is best suited for this?

- [ ] `ping http://localhost`
    
- [ ] `nslookup localhost`
    
- [x] `curl -v http://localhost`
    
- [ ] `traceroute localhost`
    

**Explanation/Notes:** `curl` is used to transfer data to or from a server. The `-v` (verbose) flag is essential here because it displays the complete request and response headers, allowing you to debug the HTTP transaction.

## 2. Advanced `tar` Archiving

**Question:** You need to view the contents of a compressed archive named `backup.tar.gz` without actually extracting the files. Which `tar` flag combination should you use?

- [ ] `-xzvf`
    
- [ ] `-czvf`
    
- [x] `-tzvf`
    
- [ ] `-vzf`
    

**Explanation/Notes:** The `-t` flag stands for "list". Combined with `z` (gzip), `v` (verbose), and `f` (file), it lists the contents of the tarball without unpacking it to your directory.

## 3. SSH Configurations

**Question:** What is the primary purpose of the `~/.ssh/known_hosts` file on your local machine?

- [ ] To store the public keys of users allowed to access your machine.
    
- [x] To store the host keys of remote servers you have previously connected to, preventing man-in-the-middle attacks.
    
- [ ] To define custom shortcuts and aliases for SSH connections.
    
- [ ] To store your private keys securely.
    

**Explanation/Notes:** The `known_hosts` file logs the cryptographic identity of servers you connect to. If a server's identity changes in the future, SSH will warn you, protecting you from connecting to a malicious imposter.

## 4. Git Version Control

**Question:** You accidentally committed a compiled binary file (`app.exe`) to your Git repository. You added it to your `.gitignore` file, but Git is still tracking it. What command must you run to fix this?

- [ ] `git remove app.exe`
    
- [x] `git rm --cached app.exe`
    
- [ ] `git delete app.exe`
    
- [ ] `git checkout app.exe`
    

**Explanation/Notes:** If a file is already being tracked by Git, adding it to `.gitignore` won't untrack it. You must use `git rm --cached` to remove it from Git's tracking index while keeping the file on your local hard drive.

## 5. Web Server Document Root

**Question:** By default, if you install `apache2` or `nginx` on an Ubuntu system, in which directory must you place your `index.html` file for the web server to serve it to the public?

- [ ] `/etc/apache2/html`
    
- [ ] `/home/ubuntu/www`
    
- [x] `/var/www/html`
    
- [ ] `/usr/share/nginx/html`
    

**Explanation/Notes:** `/var/www/html` is the default "Document Root" for web servers on Debian/Ubuntu systems. The web server daemon looks here first for content to serve.

## 6. Process States

**Question:** In Linux, what defines a "Zombie" process?

- [ ] A process that is currently running in the background using `&`.
    
- [ ] A process whose parent has died, and it has been adopted by `init`/`systemd`.
    
- [x] A process that has completed execution but still has an entry in the process table because its parent hasn't read its exit status.
    
- [ ] A process that has been paused using a `SIGSTOP` signal.
    

**Explanation/Notes:** A zombie is "dead" but hasn't been "reaped". If the parent process dies before reaping the child, the child becomes an "Orphan" (which is then adopted by `init`).

## 7. The Compilation Process

**Question:** During the C/C++ compilation process, which stage is responsible for translating Assembly language into machine-readable binary object code?

- [ ] Pre-processor
    
- [ ] Compiler
    
- [x] Assembler
    
- [ ] Linker
    

**Explanation/Notes:** The order is Pre-processor (handles macros/includes) -> Compiler (C++ to Assembly) -> Assembler (Assembly to Binary Object code) -> Linker (combines object code with libraries into an executable).

## 8. Makefiles

**Question:** In a `Makefile`, what represents the files or conditions that must be satisfied before a specific target can be built?

- [ ] Actions
    
- [x] Dependencies
    
- [ ] Macros
    
- [ ] Compilers
    

**Explanation/Notes:** A Makefile rule consists of a Target, its Dependencies (the files needed to build the target), and the Actions (the tab-indented shell commands to execute the build).

## 9. SFTP Commands

**Question:** While connected to an AWS instance via `sftp`, which command would you use to change the working directory on your **local** machine without closing the connection?

- [ ] `cd`
    
- [x] `lcd`
    
- [ ] `pwd`
    
- [ ] `local cd`
    

**Explanation/Notes:** In SFTP, standard commands like `cd`, `ls`, and `pwd` apply to the remote server. Prepending an `l` (e.g., `lcd`, `lls`, `lpwd`) applies the command to your local machine.

## 10. DNS and Routing

**Question:** Which networking command queries the Domain Name System (DNS) to perform a reverse lookup, converting a known IP address into its corresponding domain name?

- [ ] `route`
    
- [x] `nslookup`
    
- [ ] `traceroute`
    
- [ ] `nmap`
    

**Explanation/Notes:** `nslookup` (Name Server Lookup) can perform both forward lookups (Domain to IP) and reverse lookups (IP to Domain).

## 11. Security Groups and Firewalls

**Question:** In an AWS Security Group, what CIDR block should you use to allow inbound traffic from _any_ IPv4 address on the internet?

- [ ] `127.0.0.1/32`
    
- [ ] `10.0.0.0/24`
    
- [x] `0.0.0.0/0`
    
- [ ] `255.255.255.255/32`
    

**Explanation/Notes:** `0.0.0.0/0` represents the entire IPv4 address space. Conversely, a `/32` block (e.g., `192.168.1.5/32`) restricts access to one specific, single IP address.

## 12. Linux Boot Process

**Question:** What is the correct chronological order of the Linux boot process?

- [ ] Bootloader -> BIOS/UEFI -> POST -> Kernel -> OS/init
    
- [x] BIOS/UEFI -> POST -> Bootloader -> Kernel -> OS/init
    
- [ ] POST -> Bootloader -> BIOS/UEFI -> OS/init -> Kernel
    
- [ ] Kernel -> BIOS/UEFI -> POST -> Bootloader -> OS/init
    

**Explanation/Notes:** The firmware (BIOS/UEFI) wakes up first, runs hardware checks (POST), hands off to the Bootloader (like GRUB), which loads the Kernel into memory. Finally, the Kernel starts the OS services (systemd/init).

## 13. System Utilities

**Question:** You want to find out the exact path to the executable file for the `gcc` compiler. Which command will return this location based on your `$PATH` variable?

- [ ] `find gcc`
    
- [x] `which gcc`
    
- [ ] `ldd gcc`
    
- [ ] `grep gcc`
    

**Explanation/Notes:** `which` (and `whereis`) searches the directories listed in your `$PATH` environment variable to find the location of the executable command. `ldd` checks shared library dependencies.

## 14. File Inodes & Links

**Question:** What happens if you delete the original source file that a **symbolic link (symlink)** points to?

- [ ] The symbolic link automatically deletes itself.
    
- [ ] The data remains accessible through the symbolic link.
    
- [x] The symbolic link breaks and becomes a "dangling" link.
    
- [ ] The OS restores the original file.
    

**Explanation/Notes:** A symlink points to a file's _name/path_. If the target is deleted, the link breaks. A _hard link_, however, points directly to the inode; the data persists as long as at least one hard link exists.

## 15. Shell Scripting variables

**Question:** In a bash script, which environment variable stores the exit status of the most recently executed command?

- [x] `$?`
    
- [ ] `$$`
    
- [ ] `$PATH`
    
- [ ] `$1`
    

**Explanation/Notes:** `$?` returns `0` if the previous command was successful, and a non-zero number (like `1` or `2`) if an error occurred. `$1` is the first argument passed to the script, and `$$` is the PID of the current shell.

## 16. Packet Sniffing

**Question:** Which command provides raw packet capture capabilities directly from the command line, allowing you to see traffic on port 80 or 443?

- [ ] `netstat`
    
- [ ] `nmap`
    
- [x] `tcpdump`
    
- [ ] `iptables`
    

**Explanation/Notes:** `tcpdump` is a powerful packet analyzer. `netstat` shows active connections, `nmap` scans for open ports, and `iptables` manages firewall rules.

## 17. Bash Text Processing

**Question:** Which text processing tool is best described as a "stream editor" that is highly effective for performing on-the-fly find-and-replace operations within text files?

- [ ] `grep`
    
- [x] `sed`
    
- [ ] `awk`
    
- [ ] `wc`
    

**Explanation/Notes:** `sed` (Stream Editor) is famously used for substitutions (e.g., `sed 's/find/replace/g'`). `grep` is for searching, and `awk` is for column/field-based data manipulation.

## 18. Service Management

**Question:** Using `systemctl`, what is the difference between `enable` and `start`?

- [ ] `start` turns it on permanently, `enable` turns it on for the current session.
    
- [x] `start` turns it on for the current session, `enable` configures it to start automatically on boot.
    
- [ ] They are identical commands.
    
- [ ] `enable` allows users to use it, `start` runs the binary.
    

**Explanation/Notes:** If you install a web server, you `start` it to run it right now. You `enable` it so that if the server reboots, the web service turns itself back on automatically.

## 19. Terminal Multiplexers

**Question:** What is the primary benefit of using a tool like `tmux`?

- [ ] It compiles C++ code faster.
    
- [ ] It securely transfers files over SSH.
    
- [x] It creates pseudo-terminals that allow processes to keep running in the background even if your SSH session disconnects.
    
- [ ] It acts as a firewall for your terminal.
    

**Explanation/Notes:** `tmux` (Terminal Multiplexer) allows you to "detach" from a session, leaving tasks running, and "attach" to it later, preventing long scripts from dying if your connection drops.

## 20. Networking / Sockets

**Question:** In socket programming (as seen in Lab 12), what two pieces of information are required to successfully form a socket connection?

- [ ] MAC Address and Hostname
    
- [ ] Public Key and Private Key
    
- [x] IP Address and Port Number
    
- [ ] Domain Name and Subnet Mask
    

**Explanation/Notes:** An IP Address routes the traffic to the correct physical machine, and the Port Number routes the traffic to the correct software application running on that machine. Together, they form a Socket.

## 21. Standard IO Redirection

**Question:** What does the `>>` operator do in bash?

- [ ] Overwrites the contents of a file with standard output.
    
- [x] Appends standard output to the end of an existing file.
    
- [ ] Redirects standard error (stderr) to standard output.
    
- [ ] Pipes the output of one command into the input of another.
    

**Explanation/Notes:** `>` overwrites a file. `>>` appends to a file. `|` pipes output to another command.

## 22. Network Routing

**Question:** When looking at network information, what is the role of the "Gateway Address"?

- [ ] It translates domain names to IP addresses.
    
- [x] It is the IP address of the router that handles traffic destined for outside the local subnet.
    
- [ ] It is the unique hardware identifier of your Network Interface Card.
    
- [ ] It assigns dynamic IP addresses to new devices on the network.
    

**Explanation/Notes:** If your computer wants to talk to a computer not on your local network (like a server on the internet), it sends the packet to the Default Gateway (usually your router), which forwards it out to the internet.

## 23. File Permissions

**Question:** You run `ls -l` and see a file with permissions `-rwxr-xr--`. What does this mean in terms of User, Group, and Other?

- [ ] User: Read/Write, Group: Read/Execute, Other: Read
    
- [x] User: Read/Write/Execute, Group: Read/Execute, Other: Read
    
- [ ] User: Read/Execute, Group: Read/Write, Other: Execute
    
- [ ] User: Read/Write/Execute, Group: Read/Write, Other: None
    

**Explanation/Notes:** The first three (`rwx`) belong to the Owner/User. The middle three (`r-x`) belong to the Group. The last three (`r--`) belong to Other/World. In octal notation, this is `754`.

## 24. Process Control

**Question:** You have a process running in the foreground that is unresponsive. You press `Ctrl+Z`. What does this do?

- [ ] It forcefully kills the process (SIGKILL).
    
- [ ] It gracefully terminates the process (SIGTERM).
    
- [x] It stops/pauses the process and sends it to the background.
    
- [ ] It detaches the process from the terminal.
    

**Explanation/Notes:** `Ctrl+Z` sends a `SIGSTOP` signal, pausing the process and returning control of the terminal. You can then use the `bg` command to let it run in the background, or `fg` to bring it back. `Ctrl+C` sends `SIGINT` to interrupt/terminate.

## 25. Git Collaboration

**Question:** You've created a new branch locally and made your commits. When you try to run `git push`, Git gives you an error because the remote repository doesn't know about this branch yet. What command must you run?

- [ ] `git push --force`
    
- [ ] `git merge origin main`
    
- [x] `git push -u origin [branch-name]`
    
- [ ] `git checkout origin`
    

**Explanation/Notes:** The `-u` (or `--set-upstream`) flag tells Git to create the branch on the remote server (`origin`) and set up a tracking connection so future `git pull` or `git push` commands know where to go.