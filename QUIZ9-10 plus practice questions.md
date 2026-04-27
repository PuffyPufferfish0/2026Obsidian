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



# AI Practice Exam I

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

# AI practice exam II
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

## 26. SSH Key Security

**Question:** You try to SSH into a server using your private key (`id_rsa`), but the command fails with a "bad permissions" or "permissions are too open" error. How should you fix this?

- [ ] Run `chmod 777 id_rsa`
    
- [ ] Run `chmod 755 id_rsa`
    
- [x] Run `chmod 400 id_rsa` or `chmod 600 id_rsa`
    
- [ ] Rename the file to `id_rsa.pub`
    

**Explanation/Notes:** SSH clients strictly enforce that private keys must _only_ be readable by the owner. If groups or others can read the file, SSH will refuse to use it for security reasons.

## 27. Git Merge Conflicts

**Question:** You pull changes from a remote branch, and Git tells you there is a merge conflict. When you open the conflicting file, what markers will Git have inserted to show you the conflicting code?

- [ ] `!!! CONFLICT !!!` and `/// END ///`
    
- [x] `<<<<<<< HEAD`, `=======`, and `>>>>>>> branch-name`
    
- [ ] `# BEGIN MERGE` and `# END MERGE`
    
- [ ] `/* Git Conflict */`
    

**Explanation/Notes:** Git uses these specific arrow and equal-sign markers to delineate your local changes (`HEAD`), the divider, and the incoming remote changes. You must manually edit the file to choose the correct code and delete the markers.

## 28. SFTP Uploads

**Question:** While using the `sftp` interactive prompt, which command pushes a file from your local computer up to the remote server?

- [ ] `get [file]`
    
- [ ] `upload [file]`
    
- [x] `put [file]`
    
- [ ] `push [file]`
    

**Explanation/Notes:** In SFTP, `get` retrieves a file from the remote server, while `put` places a file onto the remote server.

## 29. Network Packet Tracing

**Question:** You are trying to diagnose exactly where a connection is failing between your computer and a remote server by viewing every "hop" (router) the packet takes along the way. What command does this?

- [ ] `tcpdump`
    
- [x] `traceroute` (or `tracert` on Windows)
    
- [ ] `nslookup`
    
- [ ] `ping`
    

**Explanation/Notes:** `traceroute` prints the route packets take to a network host, showing each router (hop) and the time it takes to travel between them.

## 30. Bash Scripting: Shebang

**Question:** What is the purpose of placing `#!/bin/bash` at the very first line of a script file?

- [x] It tells the operating system which interpreter to use to execute the script.
    
- [ ] It is a comment reminding the programmer that this is a bash script.
    
- [ ] It grants the file execute permissions automatically.
    
- [ ] It imports the bash standard library into the script.
    

**Explanation/Notes:** The "shebang" (`#!`) explicitly defines the path to the interpreter (like `/bin/bash` or `/usr/bin/python3`) so the OS knows how to run the file when executed via `./script.sh`.

## 31. Filesystem Inodes

**Question:** Which of the following pieces of information is NOT stored inside a file's inode?

- [ ] The file's owner (UID)
    
- [ ] The file's permissions
    
- [x] The file's name
    
- [ ] The physical location of the file's data blocks on the disk
    

**Explanation/Notes:** Inodes store all the metadata _except_ the file's name. The filename is actually stored in the directory table, which maps the human-readable name to the inode number.

## 32. Standard Streams: Piping

**Question:** In the command `cat auth.log | grep "Failed"`, what is the vertical bar (`|`) doing?

- [ ] Running the two commands at the exact same time.
    
- [ ] Appending the output of `grep` to `auth.log`.
    
- [x] Taking the standard output (stdout) of `cat` and passing it as the standard input (stdin) to `grep`.
    
- [ ] Checking if the first command fails, and if so, running the second.
    

**Explanation/Notes:** The pipe operator allows you to chain commands together, feeding the output of the left command directly into the input of the right command.

## 33. Tar Extraction

**Question:** You have downloaded `project.tar.gz`. What is the correct command to extract its contents?

- [ ] `tar -czvf project.tar.gz`
    
- [x] `tar -xzvf project.tar.gz`
    
- [ ] `tar -tzvf project.tar.gz`
    
- [ ] `tar -ezvf project.tar.gz`
    

**Explanation/Notes:** The `-x` flag stands for "eXtract". `c` is for create, and `t` is for list.

## 34. Web Server Ports

**Question:** If a client uses `https://` to connect to your web server, which port is the server listening on by default?

- [ ] Port 22
    
- [ ] Port 80
    
- [x] Port 443
    
- [ ] Port 8080
    

**Explanation/Notes:** Standard HTTP uses Port 80. Secure HTTP (HTTPS) uses Port 443. Port 22 is for SSH.

## 35. The Compilation Process: Linking

**Question:** In the final step of C/C++ compilation, what is the role of the Linker?

- [ ] It translates high-level code into Assembly.
    
- [ ] It links your code to a Git repository.
    
- [x] It combines your compiled object code with pre-compiled libraries (like standard math or IO libraries) to form the final executable.
    
- [ ] It handles macro definitions like `#include`.
    

**Explanation/Notes:** The linker resolves all the references to external functions (like `printf` or `cout`) by finding them in system libraries and linking them into your final `a.out` or `.exe` file.

## 36. Makefile Default Behavior

**Question:** If you have a `Makefile` with targets named `clean`, `build`, and `run` in that exact order, what happens if you type just `make` and hit Enter?

- [ ] It will run all three targets sequentially.
    
- [ ] It will prompt you to choose a target.
    
- [ ] It will run the `build` target automatically.
    
- [x] It will run the `clean` target because it is the first one listed.
    

**Explanation/Notes:** By default, if no target is specified, the `make` command will automatically execute the very first target defined in the file.

## 37. Process Control: Force Kill

**Question:** A background process is completely frozen and ignoring the standard `kill` command. How do you send a `SIGKILL` to forcefully terminate it immediately?

- [ ] `kill -STOP [PID]`
    
- [x] `kill -9 [PID]`
    
- [ ] `kill -1 [PID]`
    
- [ ] `forcekill [PID]`
    

**Explanation/Notes:** The standard `kill` sends a `SIGTERM` (terminate gracefully, signal 15). `kill -9` sends a `SIGKILL`, which the kernel handles directly, instantly destroying the process without letting it clean up.

## 38. ICMP and Firewalls

**Question:** You run `ping 8.8.8.8` and get 100% packet loss, but you can successfully run `curl https://8.8.8.8`. Why did the ping fail?

- [ ] Your internet is completely down.
    
- [x] The remote server's firewall is configured to drop or block ICMP packets.
    
- [ ] `ping` requires root (`sudo`) privileges.
    
- [ ] The DNS server is offline.
    

**Explanation/Notes:** `ping` relies on the ICMP protocol. Many modern servers and firewalls intentionally block ICMP Echo Requests for security purposes, while leaving TCP ports (like 443 for HTTPS) open.

## 39. AWS Security Groups: Single IP

**Question:** You want to restrict SSH access to your AWS instance so that ONLY your specific home IP address (e.g., `192.168.1.5`) can connect. What CIDR block must you use in the inbound rule?

- [ ] `192.168.1.5/0`
    
- [ ] `192.168.1.5/24`
    
- [x] `192.168.1.5/32`
    
- [ ] `192.168.1.5/16`
    

**Explanation/Notes:** A `/32` subnet mask means "match all 32 bits of the IPv4 address exactly", restricting the rule to one single host IP.

## 40. SSH `config` Files

**Question:** What is the benefit of setting up a `~/.ssh/config` file?

- [ ] It automatically disables firewall rules to let you connect.
    
- [x] It allows you to create aliases (like `ssh myserver`) that automatically apply the correct IP, username, and private key path.
    
- [ ] It encrypts your bash history.
    
- [ ] It allows you to SSH without needing any keys or passwords.
    

**Explanation/Notes:** The config file simplifies the SSH workflow by storing connection parameters so you don't have to type out `ssh -i ~/.ssh/key user@192.168.1.1` every time.

## 41. Discovering Active Connections

**Question:** Which command will list all of your machine's currently active, established network connections?

- [ ] `ip a`
    
- [ ] `ping localhost`
    
- [x] `netstat -an | grep ESTABLISHED`
    
- [ ] `tcpdump -i any`
    

**Explanation/Notes:** `netstat` (or the newer `ss` command) shows network statistics. The `-an` flags show all sockets with numeric IPs, and piping into `grep ESTABLISHED` filters for only active connections.

## 42. Text Processing: `awk`

**Question:** Which text processing command is uniquely designed to process data formatted in columns and fields (such as printing only the 3rd column of a CSV file)?

- [ ] `grep`
    
- [ ] `sed`
    
- [x] `awk`
    
- [ ] `find`
    

**Explanation/Notes:** While `sed` is great for stream replacement and `grep` for searching, `awk` is a full programming language specifically designed to manipulate formatted data by rows and columns/fields.

## 43. Disk Partitions

**Question:** What is the primary limitation of the older MBR (Master Boot Record) partition table format compared to the modern GPT (GUID Partition Table)?

- [x] MBR cannot support hard drives larger than 2 Terabytes.
    
- [ ] MBR is only compatible with Windows.
    
- [ ] MBR cannot be used with solid-state drives (SSDs).
    
- [ ] MBR requires the drive to be formatted as FAT32.
    

**Explanation/Notes:** MBR is a legacy standard that maxes out at 2TB and 4 primary partitions. GPT allows for massive drive sizes and 128 partitions.

## 44. File Ownership

**Question:** You need to transfer ownership of a file named `report.txt` from the user 'ubuntu' to the user 'root'. Which command accomplishes this?

- [ ] `chmod root report.txt`
    
- [ ] `usermod -o root report.txt`
    
- [x] `chown root report.txt`
    
- [ ] `sudo su root`
    

**Explanation/Notes:** `chown` (change owner) modifies the user and/or group ownership of a file. `chmod` (change mode) modifies the read/write/execute permissions.

## 45. System Utilities: Disk Space

**Question:** Which command is used to view the amount of available and used disk space on your mounted filesystems?

- [ ] `du`
    
- [x] `df`
    
- [ ] `free`
    
- [ ] `ls -l`
    

**Explanation/Notes:** `df` (disk free) reports filesystem disk space usage. `du` (disk usage) estimates file space usage for specific directories. `free` checks RAM usage.

## 46. Secure File Deletion

**Question:** Why would you use the `shred` command instead of `rm` to delete a sensitive file?

- [ ] `shred` bypasses read-only permissions.
    
- [ ] `shred` deletes the file instantly without confirmation.
    
- [x] `shred` repeatedly overwrites the file's data on the physical disk to prevent forensic recovery.
    
- [ ] `shred` moves the file to a secure recycle bin.
    

**Explanation/Notes:** `rm` only removes the inode link, leaving the physical 1s and 0s on the hard drive until they are eventually overwritten. `shred` actively scrambles the physical data.

## 47. Bash Variables

**Question:** What is the correct syntax for assigning a value to a variable in a Bash script?

- [ ] `name = "John"`
    
- [ ] `$name="John"`
    
- [x] `name="John"`
    
- [ ] `let name == "John"`
    

**Explanation/Notes:** In Bash, variable assignments must NOT have spaces around the equals sign. To reference the variable later, you use the dollar sign (e.g., `echo $name`).

## 48. Git Commands: Initialization

**Question:** You want to download a complete copy of an existing repository from GitHub to your local computer. Which command do you use?

- [x] `git clone [url]`
    
- [ ] `git pull [url]`
    
- [ ] `git init [url]`
    
- [ ] `git fetch [url]`
    

**Explanation/Notes:** `git clone` creates a local copy of a remote repository. `git init` creates a brand new, empty repository locally.

## 49. Filesystems: Hard Links

**Question:** What happens to a hard link if you rename or move the original file it was linked to?

- [ ] The hard link breaks and must be recreated.
    
- [x] The hard link continues to function perfectly and points to the same data.
    
- [ ] The OS prevents you from moving the original file.
    
- [ ] The hard link automatically updates its internal path text.
    

**Explanation/Notes:** Hard links point directly to the physical inode number, not the file path/name. Therefore, renaming or moving the original file doesn't affect the hard link at all.

## 50. Network Port Discovery

**Question:** You want to discover which services are actively listening on a remote server by scanning its open ports. Which tool is standard for this?

- [x] `nmap`
    
- [ ] `ping`
    
- [ ] `route`
    
- [ ] `ifconfig`
    

**Explanation/Notes:** `nmap` (Network Mapper) is the industry standard tool for scanning networks to discover hosts, open ports, and running services.

## 51. Command Line Navigation

**Question:** Aside from moving a file from one directory to another, what is the `mv` command frequently used for in Linux?

- [ ] Making copies of files.
    
- [ ] Modifying file permissions.
    
- [x] Renaming files.
    
- [ ] Mounting drives.
    

**Explanation/Notes:** In Linux, renaming a file is technically moving it from its old name to its new name (e.g., `mv old_name.txt new_name.txt`).

## 52. Bash Scripting: Command Line Arguments

**Question:** Which built-in Bash utility is designed specifically to parse and handle command-line flags (like `-a` or `-f file.txt`) passed into your script?

- [ ] `xargs`
    
- [ ] `awk`
    
- [x] `getopts`
    
- [ ] `grep`
    

**Explanation/Notes:** `getopts` allows you to write while loops that elegantly parse short options/flags provided to your script by the user.

## 53. Devices in Linux

**Question:** In Linux, "Everything is a file." Hardware devices are represented as files in the `/dev` directory. What type of device is `/dev/null`?

- [ ] Block device
    
- [x] Character device
    
- [ ] Network device
    
- [ ] Symbolic link
    

**Explanation/Notes:** `/dev/null` is a special character device (a "black hole" that discards all data written to it). Hard drives (like `/dev/sda`) are Block devices because data is read/written in chunks (blocks).
# AI practice exam III
## Scenario 1: The Complete Development Workflow (Git, Make, & Compilers)

**Prompt:** You have cloned a C++ repository to your AWS instance. Your task is to develop a new feature safely, automate the build process, and merge your work.

1. Outline the exact Git commands to create and switch to a new branch called `feature-update`.
    
2. You create a `Makefile` with `build`, `run`, and `clean` targets. Explain the syntactic requirement for the action lines beneath each target.
    
3. You accidentally ran your `Makefile` and committed the resulting binary executable to Git. Explain how to use a `.gitignore` file and the `git rm` command to fix this so the executable is no longer tracked, but remains on your hard drive.
    
4. Finally, explain the steps to push this new branch to GitHub and merge it into `main`.
    

**Comprehensive Answer:**

1. **Branching:** To create and switch to the branch in one command, use `git checkout -b feature-update` (or `git switch -c feature-update`).
    
2. **Makefile Syntax:** In a `Makefile`, the action commands that execute under a target (like `g++ -o app main.cpp`) **must** be indented using a literal `Tab` character. If spaces are used, the `make` utility will throw a "missing separator" syntax error.
    
3. **Untracking Binaries:** First, add the name of the executable (or `*.exe`/`*.out`) to a `.gitignore` file located in the root of the repository. Because the file is already tracked, the `.gitignore` will be ignored for that specific file until it is removed from the cache. You must run `git rm --cached [executable_name]`. This removes it from Git's index but keeps the physical file intact on the disk.
    
4. **Pushing and Merging:** - Push the new branch to the remote repository and set upstream tracking: `git push -u origin feature-update`.
    
    - To merge, switch back to the main branch: `git checkout main`.
        
    - Merge the feature branch into main: `git merge feature-update`.
        

## Scenario 2: Web Server Deployment & Octal Permissions

**Prompt:** You are tasked with hosting a static website on your Ubuntu AWS instance. You downloaded `site.tar.gz`.

1. What command do you use to install the web server, and what is the default "Document Root" directory where files must be placed?
    
2. Write the exact command to extract `site.tar.gz` directly into that Document Root.
    
3. Users are reporting a "403 Forbidden" error when visiting your IP address. Explain the exact `chown` and `chmod` (using octal numbers) commands required to fix the directory and file permissions so the web server daemon can serve them.
    

**Comprehensive Answer:**

1. **Installation & Root:** Install using `sudo apt install apache2` (or `nginx`). The default Document Root on Ubuntu is `/var/www/html`.
    
2. **Extraction:** `sudo tar -xzvf site.tar.gz -C /var/www/html`. (The `-C` flag changes the directory before extracting).
    
3. **Permissions Fix:** A 403 error means the `apache2` service lacks OS-level read/execute permissions.
    
    - **Ownership:** Ensure your user owns the files so you can edit them: `sudo chown -R $USER:$USER /var/www/html`.
        
    - **Directory Permissions:** Directories require the Execute (`x`) bit so the server can traverse them. Set directories to **775** or **755**: `sudo chmod 775 /var/www/html`. (Owner: rwx, Group: rwx, Other: r-x).
        
    - **File Permissions:** Files only need to be Read (`r`). Set files to **664** or **644**: `sudo chmod 664 /var/www/html/*`. (Owner: rw-, Group: rw-, Other: r--).
        

## Scenario 3: Advanced SSH & SFTP Infrastructure

**Prompt:** You need to establish secure, password-less access to a remote server for a new user, `jpuff`, and transfer files.

1. Explain the sequence of generating an SSH key pair and where the Private and Public keys must reside.
    
2. What are the strict permission requirements for the private key?
    
3. Write a sample `~/.ssh/config` entry that would allow you to simply type `ssh jpuff` to connect to IP `34.192.142.17`.
    
4. Once connected via `sftp`, explain the difference between the `ls` and `lls` commands, and the `put` and `get` commands.
    

**Comprehensive Answer:**

1. **Key Generation & Placement:** Run `ssh-keygen -t ed25519` on the local machine. The Private Key (`id_ed25519`) must stay on the local machine and never be shared. The Public Key (`id_ed25519.pub`) must be copied to the remote server and appended to the `/home/jpuff/.ssh/authorized_keys` file.
    
2. **Private Key Permissions:** The private key must have highly restrictive permissions, typically `chmod 400` or `chmod 600` (Read-only or Read/Write for the owner _only_). If groups or others have access, the SSH client will reject the key for security reasons.
    
3. **SSH Config File:**
    
    ```
    Host jpuff
        HostName 34.192.142.17
        User jpuff
        IdentityFile ~/.ssh/id_ed25519
    ```
    
4. **SFTP Commands:** - `ls` lists the files on the _remote_ server, while `lls` (local ls) lists files on your _local_ machine.
    
    - `put` uploads a file from your local machine to the remote server.
        
    - `get` downloads a file from the remote server to your local machine.
        

## Scenario 4: Network Diagnostics, Protocols, & Packet Sniffing

**Prompt:** A user reports that a remote API (`https://api.example.com`) is unreachable.

1. You run `ping api.example.com` and receive 100% packet loss. However, `curl -v https://api.example.com` returns a successful HTTP 200 response. Explain why this happens regarding firewalls and protocols.
    
2. Explain the purpose of `nslookup` and `traceroute` in further diagnosing network issues.
    
3. You run `tcpdump` to capture raw packets between your machine and the server. Why can you easily read the requested data when hitting an `http://` endpoint, but the data looks like scrambled garbage when hitting an `https://` endpoint?
    

**Comprehensive Answer:**

1. **Ping vs Curl:** `ping` utilizes the ICMP protocol (specifically Echo Requests). Many modern servers and AWS Security Groups intentionally block inbound ICMP traffic to prevent discovery and DDoS attacks. `curl`, however, uses TCP (Port 443 for HTTPS). The firewall allows port 443 traffic while dropping ICMP, resulting in a failed ping but a successful web request.
    
2. **Diagnostics:** - `nslookup` queries the DNS server to ensure `api.example.com` is correctly resolving to an IP address. If DNS fails, the network connection cannot be made.
    
    - `traceroute` maps the exact path (every router/hop) the packet takes from your machine to the destination, identifying exactly where a connection might be dropping in the middle of the internet.
        
3. **Packet Sniffing:** HTTP transmits data in raw, unencrypted plaintext (ASCII), making it entirely readable via `tcpdump`. HTTPS transmits data encrypted via TLS/SSL. `tcpdump` captures the packets, but without the decryption keys, the payload payload is unreadable.
    

## Scenario 5: AWS Security Groups & CIDR Subnetting

**Prompt:** You are configuring an AWS Security Group (Firewall) for a server that hosts a website and requires SSH access for administration.

1. Define what Inbound (Ingress) and Outbound (Egress) rules mean.
    
2. You want the website (HTTP) to be accessible to the entire world. What port and CIDR block do you use?
    
3. You want SSH access to be restricted _only_ to devices on the Wright State University network (which uses IPs starting with `130.108`). What port and CIDR block do you use?
    
4. You want SSH access restricted to _only_ your specific home IP address (`184.59.169.106`). What CIDR block do you use?
    

**Comprehensive Answer:**

1. **Ingress/Egress:** Inbound (Ingress) rules control incoming traffic from the outside world trying to reach your server. Outbound (Egress) rules control traffic originating from your server trying to reach the outside world.
    
2. **World HTTP Access:** Allow TCP Port **80**. The CIDR block for "anywhere" is **`0.0.0.0/0`**.
    
3. **WSU Subnet SSH Access:** Allow TCP Port **22**. To allow any IP starting with `130.108`, use the CIDR block **`130.108.0.0/16`** (locking the first 16 bits).
    
4. **Single IP SSH Access:** Allow TCP Port **22**. To lock access to a single, specific IP address, use a `/32` mask: **`184.59.169.106/32`**.
    

## Scenario 6: Process Management, Signals, & Multiplexers

**Prompt:** You are running a long data-processing Python script on your AWS instance.

1. Explain how a Terminal Multiplexer like `tmux` solves the problem of your SSH connection unexpectedly dropping.
    
2. You run the script in a standard terminal without `tmux`. It takes up your terminal window. Explain the exact keystrokes and commands to pause the script, move it to the background, and verify it is running.
    
3. The script freezes entirely. Explain the difference between sending it a `SIGTERM` and a `SIGKILL` using the `kill` command.
    

**Comprehensive Answer:**

1. **Tmux:** When an SSH session drops, the controlling terminal is destroyed, sending a SIGHUP (Hangup) signal that kills all attached child processes. `tmux` creates a "pseudo-terminal" running independently on the server. You can "detach" from it safely and "attach" later; if SSH drops, the `tmux` session and its processes continue running unaffected in the background.
    
2. **Foreground to Background:**
    
    - Press `Ctrl + Z`. This sends a `SIGSTOP` signal, pausing the process and giving you your prompt back.
        
    - Type `bg` and press Enter. This resumes the paused process in the background.
        
    - Type `jobs` or `ps` to verify the process is actively running.
        
3. **Kill Signals:** - `kill [PID]` sends a `SIGTERM` (Signal 15). This is a polite request to terminate. It allows the program to catch the signal, save data, close files, and exit gracefully.
    
    - `kill -9 [PID]` sends a `SIGKILL` (Signal 9). This signal cannot be caught or ignored by the program. The Linux kernel forcefully and instantly destroys the process without giving it any chance to clean up.
        

## Scenario 7: Linux Hardware, Devices, and Filesystems

**Prompt:**

1. Explain the statement "In Linux, everything is a file." Provide examples of a Block device and a Character device found in the `/dev` directory.
    
2. Contrast the older MBR partition table with the modern GPT standard.
    
3. Explain the difference between a Hard Link and a Symbolic (Soft) Link. What happens to each if the original target file is deleted?
    

**Comprehensive Answer:**

1. **Devices as Files:** Linux abstracts hardware interfaces into file streams. You interact with hardware by reading/writing to special files in `/dev`. A **Block device** reads/writes data in buffered chunks/blocks (e.g., hard drives like `/dev/sda`). A **Character device** reads/writes data unbuffered, one character at a time (e.g., the terminal `/dev/tty`, or the data-destroying black hole `/dev/null`).
    
2. **MBR vs GPT:** MBR (Master Boot Record) is a legacy standard limited to drives no larger than 2 Terabytes and supports only 4 primary partitions. GPT (GUID Partition Table) is the modern standard, supporting virtually unlimited drive sizes (Zettabytes) and up to 128 partitions.
    
3. **Links:** - A **Symbolic Link** (`ln -s`) points to a file's _path/name_. If the original file is deleted, the symlink breaks and becomes a "dangling" link because the name it points to no longer exists.
    
    - A **Hard Link** (`ln`) points directly to the file's underlying **inode** on the physical disk. If the original file name is deleted, the data remains perfectly intact and accessible through the hard link, because the hard link itself is just another name pointing to the same physical data blocks. The data is only truly deleted when _all_ hard links to that inode are removed.
        

## Scenario 8: Bash Scripting, IO Streams, & Text Processing

**Prompt:** You are writing a Bash script to parse log files.

1. Explain what the `#!/bin/bash` line at the top of the file does.
    
2. Explain the flow of data in the following command string: `cat auth.log | grep "Failed" | awk '{print $1}' >> attackers.txt`
    
3. What built-in bash utility should you use inside your script if you want to allow the user to pass arguments with flags, such as `./script.sh -f auth.log -v`?
    

**Comprehensive Answer:**

1. **Shebang:** `#!/bin/bash` is called the shebang. It tells the operating system's program loader which interpreter program should be used to parse and execute the lines in the file (in this case, the bash shell).
    
2. **Stream Pipeline:** - `cat auth.log`: Reads the file and sends the content to Standard Output (stdout).
    
    - `|` (Pipe): Takes the stdout from `cat` and passes it as Standard Input (stdin) to `grep`.
        
    - `grep "Failed"`: Filters the stream to only lines containing "Failed", and pipes that stdout to `awk`.
        
    - `awk '{print $1}'`: Takes the filtered lines, splits them by spaces, and prints only the 1st column (the IP address or timestamp).
        
    - `>> attackers.txt`: Takes the final stdout from `awk` and **appends** it to the end of the `attackers.txt` file (unlike `>`, which would overwrite the file entirely).
        
3. **Parsing Flags:** You should use **`getopts`**. It is a built-in bash command specifically designed to be used inside a `while` loop to easily parse short options/flags (like `-f` or `-v`) and their associated arguments passed by the user.


Question 1

When configuring a firewall or an AWS Security Group, which term specifically refers to the rules governing traffic that is leaving your server and going out to the internet?
Answer: Egress
Question 2

When setting up SSH key-based authentication, which file on the remote server must contain the client's public key?
Answer: ~/.ssh/authorized_keys
Question 3

What is a 'Zombie' process in Linux?
Answer: A process that has terminated but still has an entry in the process table because its parent hasn't read its exit status.
Explanation: A zombie process has finished execution, but its parent hasn't collected its exit status yet, leaving a "dead" placeholder entry in the system's process table.
Question 4

What is the correct sequential order of the C/C++ compilation process?
Answer: Pre-processor, compiler, assembler, linker
Question 5

Which of the following is true regarding symbolic links versus hard links?
Answer: If the original file is deleted, a hard link to it will still retain the file's data.
Explanation: Hard links point directly to the file's underlying inode (the data blocks on the disk). The data persists until all hard links pointing to that inode are deleted. Symbolic links just point to the file's path, so if the target is deleted, the link breaks.
Question 6

Which scripting command can be used to take standard input and write it to both standard output and one or more files simultaneously?
Answer: tee
Question 7

In a Makefile, what is the term for the files or conditions that must be up-to-date before a specific target's actions are run?
Answer: Dependencies
Question 8

Which tool is primarily designed to manipulate formatted data using fields and columns, often processing it line by line?
Answer: awk
Question 9

What does CIDR notation (e.g., /24) specify in an IPv4 address?
Answer: The number of bits used for the network portion of the address.
Explanation: In a /24 network, 24 out of the 32 available bits are strictly used to identify the network itself, leaving the remaining 8 bits (256 addresses) available to be assigned to hosts.
Question 10

During the Linux boot process, what is the primary role of the bootloader (like GRUB)?
Answer: To load the kernel and initial ramdisk into memory and execute it.
Question 11

What happens when a parent process terminates before its child process completes its execution?
Answer: The child process becomes an Orphan and is typically adopted by the init or systemd process.
Explanation: When a parent dies before its child, the active child is orphaned. The system reassigns its parent to the root process (PID 1) to ensure the child can eventually be cleaned up properly when it finishes.
Question 12

Which command is used to resume a suspended (stopped) job and let it continue running in the background?
Answer: bg
Question 13

Which tool provides the proper interface for viewing the logs generated by a background service managed by systemd?
Answer: journalctl
Question 14

In the output of the 'ps' command, what does the PPID column represent?
Answer: Parent Process ID
Question 15

How do you redirect ONLY the standard error (stderr) of a command into a file named 'errors.log'?
Answer: command 2> errors.log
Explanation: In Linux IO streams, standard output is file descriptor 1, and standard error is file descriptor 2. Using 2> ensures that only the error stream is redirected to the file.
Question 16

Which operator is used to append standard output to the end of an existing file without overwriting its current contents?
Answer: >>
Question 17

What is the primary function of the pipe '|' operator in a bash shell?
Answer: It passes the standard output of the command on the left as standard input to the command on the right.
Question 18

While 'awk' is highly effective for processing column-based structured data, which tool is specifically recognized as a stream editor used heavily for 'search and replace' operations using regular expressions?
Answer: sed
Question 19

In an awk script like awk '{print $2}' file.txt, what does the $2 represent?
Answer: The second field (or column) of the current record.
Explanation: awk automatically splits each line it reads into distinct columns based on whitespace (or a specified delimiter). $1 is the first column, $2 is the second, and so on.
Question 20

Which command is correctly formatted to create a symbolic (soft) link named 'shortcut' that points to 'original.txt'?
Answer: ln -s original.txt shortcut
Question 21

What happens to a symbolic link if you delete the original file it points to?
Answer: The symbolic link remains on the filesystem but becomes broken or 'dangling'.
Question 22

Which of the following pieces of information is stored directly within a file's inode?
Answer: File metadata such as permissions, ownership, and timestamps.
Explanation: An inode stores all the administrative metadata about a file and pointers to its data blocks on the disk. However, the actual human-readable file name is not stored in the inode; it is stored in the directory that contains the file.
Question 23

If you want to view a summary of the total available and used disk space across your mounted filesystems, which command should you use?
Answer: df
Question 24

In the Linux filesystem, what kind of devices are /dev/null, /dev/zero, and /dev/random classified as?
Answer: Character devices
Explanation: Character devices handle data as a continuous, unbuffered stream of bytes. This differs from block devices (like an SSD or HDD), which read and write data in specific, fixed-size blocks.
Question 25

In an IPv4 address with a CIDR notation of /16 (e.g., 192.168.0.0/16), how many bits are reserved for the host portion of the addresses?
Answer: 16
Explanation: An IPv4 address is always exactly 32 bits long. If the network prefix takes up the first 16 bits, you subtract that from the total (32 - 16 = 16) to find the remaining bits available for hosts.
Question 26

Which network protocol automatically assigns IP addresses, subnet masks, and default gateways to devices joining a network?
Answer: DHCP
Question 27

Which modern command has largely replaced 'ifconfig' for viewing and manipulating network interfaces, IP addresses, and routing tables on Linux?
Answer: ip
Question 28

What is the primary function of the Domain Name System (DNS)?
Answer: To translate human-readable domain names into IP addresses.
Question 29

Which network diagnostic tool allows you to see the exact sequence of routers (hops) a packet passes through to reach its destination?
Answer: traceroute
Question 30

By default, which network port is used to establish a secure SSH connection?
Answer: 22
Question 31

Which of the following accurately describes the relationship and difference between a MAC address and an IP address?
Answer: A MAC address operates at the physical/data link layer to identify a Network Interface Card (NIC), while an IP address is used for logical routing across different subnets.
Explanation: MAC addresses are physical identifiers hardcoded into network hardware for local, point-to-point delivery. IP addresses are logical identifiers used by routers to navigate the larger global internet.
Question 32

In computer networking, what two specific pieces of information combine to form a 'socket'?
Answer: An IP address and a port number
Question 33

What is the primary function of Network Address Translation (NAT) as used on a typical home or corporate border gateway?
Answer: To map multiple private internal IP addresses to a single public IP address for internet access.
Explanation: NAT acts as an intermediary, allowing an entire local network of devices (which have non-routable private IPs) to share one single public-facing IP address when talking to the outside world.
Question 34

When connecting to a secure website via HTTPS, what is the crucial role of a Certificate Authority (CA)?
Answer: To verify the identity of the website owner and digitally sign their public key.
Explanation: A Certificate Authority acts as a trusted third party. It verifies that the server you are talking to actually belongs to the organization it claims to be, protecting you from man-in-the-middle attacks.
Question 35

Both curl and wget are command-line tools for downloading web content. What is a key difference in their typical default behavior?
Answer: curl outputs the retrieved data directly to the terminal standard output, while wget automatically saves it to a file.
Question 36

What network diagnostic task does the Address Resolution Protocol (ARP) perform on a local network?
Answer: It maps a known IPv4 address to an unknown hardware MAC address.
Explanation: ARP bridges the gap between Layer 3 and Layer 2 by asking the local network, "Who has this IP address? Please send me your physical MAC address so I can deliver this frame to your network card."
Question 37

Which of the following physical layer communication methods uses light to transmit data, offering extremely high bandwidth and immunity to electromagnetic interference?
Answer: Fiber optic
Question 38

If you need to capture, dump, and analyze live network packets arriving at and leaving your server's network interface, which tool is best suited for the job?
Answer: tcpdump
Question 39

What is the primary driving factor behind the global transition from the IPv4 standard to the IPv6 standard?
Answer: The exhaustion of the 32-bit IPv4 address space.
Question 40

You are configuring an AWS Security Group for a brand new web server. Which rule is required to allow public internet users to view your standard, unencrypted HTML website?
Answer: Allow Ingress (Inbound) traffic on Port 80 from 0.0.0.0/0