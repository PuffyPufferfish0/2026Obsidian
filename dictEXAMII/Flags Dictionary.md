A quick-reference guide for commonly used command options.

### `ls` (List)

- **`-a`**: All. Shows hidden files (files starting with a `.`).
    
- **`-l`**: Long format. Shows permissions, owner, group, size, and modified date.
    
- **`-t`**: Time. Sorts files by modification time. Puts the most recently modified files at the top.
    
- **`-d`**: Directory. Lists information about the directory itself, rather than its contents (e.g., `ls -ld share`).
    

### `rm` (Remove)

- **`-r`**: Recursive. Required to delete directories and the files inside them.
    

### `ps` (Process Status)

- **`-a`**: All users' processes.
    
- **`-u`**: User-oriented format (shows detailed info like CPU/MEM usage).
    
- **`-x`**: Includes processes that don't have a controlling terminal attached to them.
    
- _Combined:_ `ps -aux`
    

### `kill`

- **`-9`**: Passes the `SIGKILL` signal for an immediate, non-graceful termination.
    

### `sed` (Stream Editor)

- **`-e`**: Expression. Allows you to chain multiple sed operations in a single command.
    
- **`-i`**: In-place. Saves the changes directly to the file rather than just outputting them to the terminal.
    

### `sort`

- **`-n`**: Numeric sort. Sorts data by numerical value rather than alphabetical order.
    

### `ssh` (Secure Shell)

- **`-i`**: Identity file. Specifies the path to the private key used for authentication.
    

### `ssh-keygen`

- **`-t`**: Type. Specifies the type of encryption to use (e.g., `-t ed25519`).
    
- **`-C`**: Comment. Appends a comment to the end of the key, usually an email address.
    

### `usermod` (User Modification)

- **`-a`**: Append. Used to add a user to a supplementary group without removing them from other groups.
    
- **`-G`**: Group. Specifies the group to append the user to (usually combined with `-a`, like `usermod -aG sudo puffy`).