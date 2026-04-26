A web server is a software service running on a machine that listens for incoming network requests and serves web content (like HTML files, images, and scripts) back to the client over the internet.

### Common Web Server Software

- **`apache2`**: A widely-used, open-source web server known for its flexibility and power.
    
- **`nginx`**: Another popular open-source web server, famous for its speed and ability to handle high concurrent traffic.
    

### The Document Root

By default on Ubuntu/Debian systems, web servers look for the files they need to display in a specific directory called the Document Root.

- **Path**: `/var/www/html`
    
- **Note**: The web server needs specific read/execute permissions (`chmod`) to access and serve the files like `index.html` located in this directory.
    

### Key Ports & Management

- **Port 80**: Default port for HTTP (unencrypted web traffic).
    
- **Port 443**: Default port for HTTPS (secure, encrypted web traffic).
    
- **Service Management**: Web servers run as background daemons. You control them using `systemctl` (e.g., `systemctl status apache2` or `systemctl restart nginx`).