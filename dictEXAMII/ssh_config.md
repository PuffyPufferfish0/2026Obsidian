# `~/.ssh/config`

The SSH config file is used to create shortcuts (aliases) for your SSH connections, saving you from typing out long IP addresses, usernames, and key paths every time.

### Structure

The file lives at `~/.ssh/config`. Each entry defines a host alias and its connection parameters:

|Option|Description|
|---|---|
|**`Host`**|The shortcut name you will type (e.g., `lab08-raah`).|
|**`HostName`**|The actual IP address or domain name of the remote server.|
|**`User`**|The username to log in with (e.g., `ubuntu`).|
|**`Port`**|The port SSH is listening on (default is 22).|
|**`IdentityFile`**|The absolute path to your `.pem` private key.|

### Example

Instead of typing: `ssh -i /home/puffy/labsuser.pem ubuntu@34.192.142.17`

You configure your file, and simply type: `ssh ceg2350-sandbox`