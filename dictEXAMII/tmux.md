# `tmux` (Terminal Multiplexer)

`tmux` is a terminal multiplexer that allows you to run and manage multiple "pseudo-terminals" from a single terminal window.

### Why it's useful (The Superpower)

The primary benefit of `tmux` is **session persistence**.

Normally, if you run a process in an SSH session and your connection drops (or you close the terminal), that process is killed. `tmux` solves this:

1. You can start a long-running process inside a `tmux` session.
    
2. You can **detach** from that session, leaving it running in the background.
    
3. You can safely close your SSH connection entirely.
    
4. The process will continue running safely on the server.
    
5. Later, you can log back in and **attach** back to the exact `tmux` session to view the progress or interact with it.
    

### Core Concepts

- **Attach**: Connecting your current terminal view to a running `tmux` session.
    
- **Detach**: Disconnecting your view from the `tmux` session while leaving the session (and its processes) running in the background.
    

see [[tmux documentation]]for more



(source: https://tmuxcheatsheet.com/)