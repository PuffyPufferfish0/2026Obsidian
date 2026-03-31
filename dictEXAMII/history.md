# `history`

The `history` command outputs a numbered list of all the commands you have previously executed in your current shell session.

### Useful Workflows

- **Searching History**: You can pipe `history` into `grep` to find a command you forgot.
    
    - _Example_: `history | grep "ssh"` (Searches your past commands for anything containing "ssh").
        
- **Executing by Number**: If `history` shows that command `146` was a long script you want to run again, you can type `!146` to instantly execute it.
    
- **Interactive Search**: Pressing `Ctrl + R` in the terminal opens a reverse search prompt, allowing you to type parts of a previous command to find it dynamically.