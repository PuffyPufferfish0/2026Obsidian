# `sudo` vs `su`

Both commands are used to gain elevated privileges (root access), but they do it in different ways.

### `sudo` (Superuser Do)

- **Action**: Runs a _single_ command with superuser privileges.
    
- **Behavior**: You remain logged in as your current user, but the command executes as if root ran it.
    
- **Example**: `sudo cat /etc/shadow`
    

### `su` (Switch User)

- **Action**: Completely switches your active user session.
    
- **Behavior**: If you run `su root` (or `sudo su`, or `su -`), your prompt will change, and _every_ subsequent command you run will be executed as root until you type `exit`.
    
- **Note**: `su -` also loads the target user's environment variables.