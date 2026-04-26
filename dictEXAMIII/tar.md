`tar` (Tape Archive) is a command-line utility used to collect many files into one archive file (often called a tarball) for distribution or backup. It is frequently combined with compression utilities like `gzip`.

### Key Flags

- **`-c`**: Create a new archive.
    
- **`-x`**: Extract files from an archive.
    
- **`-v`**: Verbose output (shows the files being processed).
    
- **`-f`**: Specifies the filename of the archive.
    
- **`-z`**: Compresses or decompresses the archive using `gzip` (creates `.tar.gz`).
    
- **`-t`**: Lists the contents of an archive without extracting it.
    

### Creating an Archive

- **Syntax**: `tar -czvf [archive-name.tar.gz] [directory-or-file-to-compress]`
    
- **Example**: `tar -czvf backup.tar.gz /home/ubuntu/project` (Creates a gzipped tarball of the `project` folder).
    

### Extracting an Archive

- **Syntax**: `tar -xzvf [archive-name.tar.gz]`
    
- **Example**: `tar -xzvf backup.tar.gz -C /var/www/html` (Extracts the contents directly into the `/var/www/html` directory).