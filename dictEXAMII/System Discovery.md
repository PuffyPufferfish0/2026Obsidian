# System Discovery Commands

Linux has specialized commands to query the Kernel for hardware information. These were heavily used in the Lab 07 `sys-info.sh` script.

### Essential Commands

- **`hostnamectl`**: Shows the OS name, Kernel version, and system architecture.
    
- **`lscpu`**: Displays detailed information about the CPU architecture (brand, model, cores, threads).
    
- **`free -h`**: Shows the total, available, and used Physical Memory (RAM) in a human-readable format.
    
- **`df -h`**: Shows disk space usage for mounted file systems (like your SSD/HDD).
    
- **`lspci`**: Lists all PCI devices. Often piped to `grep -E "VGA|3D"` to specifically find the brand and model of the GPU.
    
- **`lsblk`**: Lists information about all available block devices (disk partitions and volumes).