

> [!info] This is a comprehensive dictionary I made from Labs 01-09 and Midterm 2 Review materials. It covers everything from Command Line Navigation to Process Management and System Discovery.



## 1. [[Command Line Navigation]]

Basic file and directory manipulation commands in Linux.

- **[[man]]**: Shows a list of available commands / manual pages.
    
- **[[pwd]]**: Shows the directory you are currently in.
    
- **[[ls]]**: Lists whatever is in the directory you are in.
    
- **[[cd]]**: Changes the directory you are in.
    
- **[[mkdir]]**: Makes a new directory.
    
- **[[touch]]**: Makes a new blank file, or updates the timestamp.
    
- **[[cp]]**: Copies a source to a directory.
    
- **[[mv]]**: Moves an item to a new directory (also used to rename).
    
- **[[rm]]**: Removes a file.
    
- **[[vim]]**: Opens a CLI text editor directly into the terminal.
    

## 2. [[File Permissions]], Users, and Groups

Managing who has access to what, using [[octals]] and symbolic notation.

- **`chmod`**: Changes the permissions of a file or directory. (e.g., `chmod 644 file` sets Owner: rw-, Group: r--, Other: r--).
    
- **`chown`**: Changes the user and/or group ownership of a file.
    
- **[[sudo vs su]]**: Running commands as superuser vs. switching to the root user entirely.
    

## 3. [[SSH]] (Secure Shell) & Configs

Establishing secure connections to remote systems (Default Port: 22).

- Requires a Public (`.pub`) and Private (`.pem`) key pair. The private key must _never_ be shared.
    
- **`ssh-keygen`**: Generates a new key pair.
    
- **[[ssh_config]]**: Automating long SSH commands using the `~/.ssh/config` file to create host aliases.
    

## 4. [[Git]]

Version control system used to track changes in code.

- Basic workflow: `clone` -> `status` -> `add` -> `commit` -> `push` / `pull`.
    

## 5. [[Bash Scripting]] & [[Shells]]

Automating tasks using scripts.

- **[[Shells]]**: Different command-line environments (bash, zsh, PowerShell).
    
- **Variables & [[Color Output]]**: `name="John"`, using `echo -e` and ANSI escape codes for stylized text.
    
- **Conditionals**: `if [ "$var" -eq 1 ]; then` (`==` for strings, `-gt`/`-lt` for numbers).
    
- **Loops**: `for i in {1..5}; do`
    
- **[[getopts]]**: Parsing command-line flags (like `-s` or `-a`) into your scripts.
    
- **[[Bash Aliases]]**: Using `.bash_aliases` to create custom command shortcuts.
    

## 6. [[Text Processing]] (grep, sed, awk)

Searching, replacing, and parsing data from text files.

- **[[grep]]**: Searches text for patterns.
    
- **[[sed]]**: Stream editor used for find-and-replace on the fly.
    
- **[[awk]]**: Column/field-based text processor.
    
- **`wc`**: Word count (e.g., `wc -l` counts lines).
    

## 7. Standard Streams & Redirection

How Linux handles input, output, and errors.

- **`>`** : Overwrites standard output to a file.
    
- **`>>`** : Appends standard output to a file.
    
- **`|` (Pipe)** : Takes the output of one command and passes it as input to the next.
    
- **[[xargs]]**: Advanced piping tool to convert standard input into command arguments.
    

## 8. System Utilities, Hardware & Security

Essential commands for managing your environment, finding things, and hardware discovery.

- **[[find]]**: Powerful search utility for locating files and directories.
    
- **[[history]]**: Viewing and searching previously executed commands.
    
- **[[df]]**: Checking available disk space.
    
- **[[System Discovery]]**: Commands like `lscpu`, `free`, and `lspci` to check hardware specs.
    
- **[[shred]]**: Securely deleting files so they cannot be recovered by forensic tools like `strings`.
    

## 9. [[Process Management & Control]] & Service Management

Managing active programs (RAM) and background daemons.

- **Processes**: Active instances of programs. Tracked by PID, PPID, User, and Command.
    
- **Viewing**: `ps`, `top`, `pstree`, `pgrep`.
    
- **Signaling/Killing**: `kill`, `kill -9` (SIGKILL), `kill -STOP` (Pause), `kill -CONT` (Resume).
    
- **Terminal Multiplexers ([[tmux]])**: Running "pseudo-terminals" to detach and attach background sessions.
    
- **Kernel & Services**: The Kernel manages hardware/resources. `init`/`systemd` (PID 1) starts everything else. Managed using `systemctl` (start, stop, enable, reload).