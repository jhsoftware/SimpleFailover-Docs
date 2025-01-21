---
Slug: server-set-properties-dialog-dns-data
DocID: 20
Keywords: Server set properties dialog,DNS data,TTL value
---
# Server set properties dialog - DNS data

In this section of the Server set properties dialog, you can specify the host name(s), range of IP addresses, and DNS record TTL value to serve through DNS for this server set.

These values are used when Simple Failover serves DNS requests directly (see [Options dialog / DNS serving section](gui_opt_dnsserving.md)), and/or when updating DNS servers for this server set (see [Server set properties / Update DNS section](gui_ssprop_updatedns.md))

![](images/5cf6ad43e69c.png)

 - **Host names**\
    List of DNS host names for this server set.\
    Use the Add button to add a new host name, the Edit button to update the selected host name, and the Remove button to remove the selected host name.\
    Clicking the Add or Edit buttons will open the "Host name" dialog:

    ![](images/f655f715a525.png)

- **IP addresses of**\
    Which IP addresses to serve through DNS for the above host names.

- **If all servers fail**\
    Which IP addresses to serve through DNS for the above host names if all servers fail.

- **DNS record TTL**\
The DNS record TTL (time to live) value for DNS host records (A / AAAA records) served for the above host names.\
This value controls for how long DNS servers and other DNS caches may cache these host records.\
It should be set to a fairly low value so that when a server fails, clients will quickly obtain the updated DNS records.\
This is a balance between optimizing failover speed vs. the amount of DNS traffic (lower value = more DNS traffic).
