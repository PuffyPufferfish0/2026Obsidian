### SSH (Secure Shell)

A cryptographic network protocol for operating network services securely over an unsecured network. Commonly used for remote command-line login and execution.

### Key Components

- **Private Key**: The secret key kept on your local machine (e.g., `/home/puffy/labsuser.pem`). _Must have strict permissions (600)._
    
- **Public Key**: The key you share with the server/service (e.g., pasting into GitHub settings).
    
- **`authorized_keys`**: A file on the server (`~/.ssh/authorized_keys`) containing a list of allowed public keys.
    

### Essential Commands

- **Generating a key**: `ssh-keygen -t ed25519 -C "anderson.692@wright.edu"`
    
- **Viewing a public key**: `cat ~/.ssh/id_ed25519.pub`
    
- **Connecting to a server**: `ssh -i /home/puffy/labsuser.pem ubuntu@34.192.142.17`
    

### Git Integration

Used to authenticate [[Git]] securely without typing a password every time: `git clone git@github.com:WSU-kduncan/ceg2350-s26-PuffyPufferfish0.git`



# EXAM II extra info
Primary use: To establish a secure, encrypted connection to remote systems.

- **Default Port**: 22
    
- **Keys**: Requires a Public and Private key pair.
    
    - **Private Key**: Must _NEVER_ be shared (e.g., `labsuser.pem` or `id_ed25519`). It stays on your local machine.
        
    - **Public Key**: Shared with the remote server (e.g., `id_ed25519.pub`). It acts as the "lock" that your private key opens.
        

### Generating Keys

- `ssh-keygen -t ed25519 -C "email@example.com"`
    
    - `-t`: Specifies the type of encryption.
        
    - `-C`: Adds a comment (usually your email) to identify the key.
        

### Connecting

- `ssh -i /path/to/key.pem user@hostname`