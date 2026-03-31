# `alias`

An alias is a custom shortcut name for a command or a long series of commands. They are incredibly useful for saving time on commands you type frequently.

### Creating an Alias

- **Syntax**: `alias [shortcut]='[command]'`
    
- **Example**: `alias ll='ls -la'` (Now, typing `ll` will execute `ls -la`).
    

### Making Aliases Permanent

If you just type an alias into the terminal, it will disappear when you close your SSH session. To make it permanent, you must save it to a configuration file:

- **`~/.bash_aliases`** (The standard file for storing user-specific aliases).
    
- **`~/.bashrc`** (The main shell configuration file).