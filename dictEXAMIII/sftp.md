Secure File Transfer Protocol (SFTP) is a secure, interactive command-line utility used to transfer files between a local computer and a remote server over an SSH connection.

### Connecting

- **Syntax**: `sftp [user]@[host_or_ip]`
    
- **Example**: `sftp ubuntu@ceg2350-sandbox` (Connects to the server using existing SSH configuration/keys).
    

### Navigation & Commands

SFTP environments have two sets of commands: one for the **remote** server, and one for your **local** machine (local commands are usually prefixed with an `l`).

- **`ls`**: Lists files on the remote server.
    
- **`lls`**: Lists files on your local machine's current directory.
    
- **`cd`**: Changes the directory on the remote server.
    
- **`lcd`**: Changes the directory on your local machine.
    
- **`pwd` / `lpwd`**: Prints the working directory of the remote / local machine.
    

### Transferring Files

- **`put [file]`**: Uploads a file from your local machine to the remote server.
    
- **`get [file]`**: Downloads a file from the remote server to your local machine.
    
- **`exit` or `bye`**: Closes the SFTP connection.