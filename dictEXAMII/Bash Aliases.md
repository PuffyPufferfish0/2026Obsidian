# `.bash_aliases`

The `.bash_aliases` file is a hidden file in your home directory (`~/.bash_aliases`) used to create a permanent list of custom command shortcuts (aliases).

### How it Works

1. You write aliases inside this file.
    
    - Example: `alias home="cd ~"`
        
2. Your main shell configuration file (`~/.bashrc`) contains logic that looks for `.bash_aliases`. If it finds it, it "sources" it (loads it into your environment).
    

### Why use it?

It gives complex or lengthy commands short, memorable nicknames that persist across all your SSH sessions and system reboots.