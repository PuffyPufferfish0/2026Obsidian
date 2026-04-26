A suite of CLI tools used for network discovery, testing, and troubleshooting across Linux and Windows systems.

### Discovery & Configuration

- **`hostname`**: Displays the machine's network name.
    
- **`ip a` / `ifconfig`** (Linux): Shows IP addresses, MAC addresses, and active network interfaces (NICs).
    
- **`ipconfig`** (Windows): Shows TCP/IP network configurations.
    
- **`route`**: Displays the machine's routing table (how packets find their way out of the local network via the Gateway).
    

### Connectivity Testing

- **`ping [ip_or_url]`**: Sends ICMP echo requests to test reachability and measure round-trip time. (Note: Firewalls often block ICMP, so a failed ping doesn't _always_ mean a server is completely offline).
    
- **`curl -v [url]`**: Transfers data to/from a server using protocols like HTTP or HTTPS. Useful for testing web servers. The `-v` (verbose) flag shows headers and handshake data.
    

### DNS & Tracing

- **`nslookup [domain/ip]`**: Queries the Domain Name System (DNS).
    
    - _Forward Lookup_: Turns a domain (like `wttr.in`) into an IP address.
        
    - _Reverse Lookup_: Turns an IP address into a domain name.
        
- **`traceroute [ip]`** (Linux) / **`tracert`** (Windows): Maps the exact path (hops) packets take across the internet to reach their destination.
    

### Traffic & Security Analysis

- **`netstat -an | grep ESTABLISHED`**: Lists all active, established network connections.
    
- **`nmap -p [port] [ip]`**: Scans a host to see which ports are open.
    
- **`tcpdump -i [interface]`**: A raw packet sniffer that captures network traffic traveling over a specific network interface.