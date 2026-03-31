## The Linux Kernel

- The core of the operating system.
    
- Manages system resources (CPU, memory, disk I/O).
    
- Acts as the bridge between software applications and physical hardware.
    

## System Initialization (`init` / `systemd`)

- **`init` / `systemd`** is the "Mother of all processes."
    
- When Linux boots, the Kernel starts `systemd` first.
    
- It is always assigned **PID 1**.
    
- It is responsible for starting up all other system services and user spaces.
    

## `systemctl` (Systemd Service Manager)

Used to control background services (daemons) like web servers, sshd, or custom scripts.

### Core Commands

- **`systemctl start <service>`** : Starts the service immediately for the current session.
    
- **`systemctl stop <service>`** : Stops the service immediately.
    
- **`systemctl restart <service>`** : Fully stops and then starts the service. (Drops current connections).
    
- **`systemctl reload <service>`** : Reloads configuration files _without_ dropping active connections (graceful).
    
- **`systemctl enable <service>`** : Configures the service to start automatically on system boot.
    
- **`systemctl disable <service>`** : Prevents the service from starting on boot.
    
- **`systemctl status <service>`** : Shows if the service is currently running, failed, or stopped, along with recent log output.