# `shred` (Secure Data Deletion)

The `rm` command only removes the _pointer_ to a file on the hard drive; it does not actually delete the file's data. Forensic tools (like the `strings` command) can still read the raw data left behind on the disk partition.

### How `shred` works

`shred` securely deletes a file by overwriting its data multiple times with random zeroes and garbage data _before_ removing the pointer, making it completely unrecoverable.

### Lab 08 Example

- **Command**: `shred -u secret2.txt` (The `-u` flag tells it to overwrite the file and then remove it from the filesystem).
    
- **Verification**: Running `sudo strings /dev/xvdb1 | less` on the raw partition proved that standard `rm` left data behind, but `shred` destroyed the strings entirely.