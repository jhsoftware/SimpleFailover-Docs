---
Slug: server-properties-dialog-general
Keywords: Server properties dialog,General,Weighted round robin,Pause server set,Disable server
---
# Server properties dialog - General

In this section of the Server properties dialog, you can specify the general settings for a server:

![](images/c0d68c74f973.png)

- **Public IP address**\
The public facing IP address for this server. 

- **Poll a different IP address (for example private IP behind NAT)**\
It is always preferable to poll a server's public IP address, but some NAT routers do not support this when both the server and the Simple Failover computers are on the same private private network behind the same NAT router. In this case you can use this option to have Simple Failover poll the server using its private IP address.

- **Display name / location (optional)**\
Used for easier reference only.

- **DNS weighted round robin weight**\
When Simple Failover is configured to serve DNS requests directly (see [Options dialog / DNS serving section](gui_opt_dnsserving.md)) and this server set is configured with the "IP address of -\> One of the responding servers - weighted round robin" option in the [Server set properties / DNS data section](gui_ssprop_dnsdata.md), this value controls how often the IP address of this server will be provided through DNS relative to the other servers in this server set.

- **Pause server set if this server fails (prevent failback)**\
With this option enabled, when Simple Failover detects a problem with this server, it will immediately pause the server set (after sending notifications and updating DNS if configured to do so). The server set must be resumed through the user interface or API before it begins monitoring again.

- **Disabled (intentionally off-line)**\
Check this option if you need to temporarily take down a server - for example for maintenance.\
Simple Failover will continue as if the server was no longer part of the server set.\
Once the server is ready again, you can simply un-check this option, and the server will be included again.
