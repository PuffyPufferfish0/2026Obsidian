Miscellaneous system administration and navigation tools

## `df` (Disk Free)

- Shows available disk space on your mounted file systems.
    
- Usually run with `-h` (`df -h`) to show output in "human-readable" formats (Gigabytes/Megabytes instead of raw blocks).
    

## `find`

- Powerful search utility for locating files and directories across the filesystem based on various parameters (name, size, modification date).
    
- **Example**: `sudo find / -name "*.tmp" -delete`
    
    - Searches starting from the root directory (`/`).
        
    - Looks for files matching the name `*.tmp`.
        
    - Executes the `-delete` action on matches.
        

## `alias`

- Creates custom shortcuts for long, frequently used commands.
    
- **Example**: `alias ll='ls -la'`
    
- To make aliases persist after you close the terminal, you must add the alias command to your `~/.bash_aliases` or `~/.bashrc` file.
    

## `history`

- Shows the command history of your current shell.
    
- **Recalling commands**:
    
    - `!146` : Immediately executes line 146 from your history.
        
    - `history | grep "ssh"` : Searches your history for commands containing the string "ssh".
        
    - `Ctrl + R` : Opens a reverse search prompt in the terminal to interactively find previously typed commands.