## Program vs. Process

- **Program**: A passive, executable file resting on your disk (storage).
    
- **Process**: An active, running instance of a program loaded into memory (RAM).
    

## Process Attributes

Every active process has specific attributes (often seen in `ps` output):

- **PID**: Process ID (Unique numerical identifier).
    
- **PPID**: Parent Process ID (The PID of the process that created/spawned it).
    
- **UID / USER**: The user account that owns the process.
    
- **Command**: The exact command that initiated the process.
    
- **TTY**: Teletypewriter; the terminal where the process is running.
    
- **STAT**: State; the current status of the process (running, sleeping, etc.).
    

## Finding & Viewing Processes

- **`ps`**: View a snapshot of active processes.
    
    - `ps -aux`: See all processes from all users with detailed info (CPU/memory usage).
        
- **`top` / `htop`**: Real-time, interactive process and resource monitors.
    
- **`pgrep [name]`**: Searches for running processes by their name and returns their PIDs.
    
- **`pstree`**: Shows running processes in a visual, hierarchical "tree," making it easy to see which Parent Process spawned which Child Processes.
    

## Foreground vs. Background

- **Foreground Process**: Occupies your terminal until it finishes. You cannot type new commands.
    
- **Background Process**: Runs silently, freeing up your terminal for other work.
    
    - **`&`**: Add to the end of a command to start it in the background (e.g., `sleep 100 &`).
        
    - **`Ctrl + Z`**: Suspends (pauses) the current foreground process.
        
    - **`bg`**: Resumes a suspended job in the background.
        
    - **`fg`**: Brings a background job back to the foreground.
        
    - **`jobs`**: Lists all active jobs tied to your current terminal session.
        

## Advanced Signals (`kill`)

The `kill` command sends signals to processes using their PID.

- **`kill [PID]`**: Sends `SIGTERM` (15), asking the process to cleanly and gracefully shut down.
    
- **`kill -9 [PID]`**: Sends `SIGKILL` (9), instantly forcing the process to terminate. Use as a last resort.
    
- **`kill -STOP [PID]`**: Pauses/suspends the process entirely without terminating it.
    
- **`kill -CONT [PID]`**: Resumes a suspended process from exactly where it left off.
    
- **`killall [name]`**: Kills all processes matching a specific name.
    

## Terminal Multiplexers (`tmux`)

- `tmux` allows you to run "pseudo-terminals".
    
- **Why it's useful**: You can start a process in a `tmux` session, **detach** from it, close your SSH connection entirely, and the process will continue running on the server. You can **attach** back later to view it.