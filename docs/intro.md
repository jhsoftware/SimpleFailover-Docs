---
Slug: welcome
Keywords: Introduction,Monitoring,Notification,Redirection,Weighted round robin,Load balancing,DNS caching,Server set
---
# Welcome to Simple Failover Help

[?WEB]
> [!BLUE] **NOTE:** This is an on-line version of the help file (.chm) which is included with the latest version of Simple Failover.
>
> Pressing the `F1` key or clicking the small '?' icon in most windows / dialogs within the software,
> will take you to a page in this documentation which describes the specifics of that window / dialog.

[?ANY]


**Simple Failover** continuously monitors your network servers, notifies you of any trouble, and redirects traffic to standby servers when needed.

- **Monitoring** is done by polling (sending requests to) your servers at configurable intervals and evaluating the response against configurable criteria (e.g., web page must contain specific text). It can monitor web-servers, mail-servers, FTP-servers, and practically all other TCP/IP based server types, as well as custom monitoring through script / command line execution. It logs monitoring results to a database for tracking and evidence.

- **Notification** (optional) is sent whenever a server is not responding as expected (after a configurable number of retries). Simple Failover can send notifications to multiple recipients via e-mail, a HTTP GET/POST, through script / command line execution,  and the Windows event log.

- **Redirection** (optional) of server traffic is done via DNS by always pointing your domain name to the IP address of a functional server. When needed, Simple Failover can either dynamically update the DNS records on your DNS servers (various methods), or it can itself serve as a front-end DNS server - forwarding any DNS requests that it cannot answer directly (other domain names, non-host-record requests) to a DNS server that you specify.

When using the option to serve as a front-end DNS server (see Redirection above), Simple Failover can also provide** weighted DNS round robin / load balancing**.

Simple Failover is a software package **installed** on your Windows computer - physical or virtual – local or cloud. You can configure everything and interact with it through an easy to use **classic Windows desktop application user interface** - no funky configuration files and scripts to figure out. Unless you really want to. In that case it also has an **HTTP API** (REST / JSON) making it possible to do everything without the GUI and to integrate it with almost anything.

Simple Failover can be configured in many different ways depending on the level of monitoring and redundancy required. It can monitor any number of servers for a service, notify any number of recipients of problems, and update any number of DNS servers (or serve DNS requests directly) with any number of DNS host names for a service.

## Important considerations

- Simple Failover should be running at a different network location than the service that it is monitoring. Otherwise is may not detect network problems.

- Simple Failover does not include any data synchronization features. If you want your primary and your standby servers to serve identical data, you will also need to consider how to synchronize the data.

- Some client applications (e.g. some web-browsers) will not automatically refresh DNS records for ongoing sessions, and will therefore not immediately detect updated DNS records for such a service. Therefore, when Simple Failover detects a failed server and updates DNS records to point to a backup/standby server, such applications may need to be restarted before they connect to the backup/standby server.

- We are often asked if **DNS caching** is an issue in relation to quickly updating DNS records – which Simple Failover depends on to provide failover functionality. Generally, the only issue is the one with some client applications mentioned above. Otherwise DNS caching is not an issue because Simple Failover assigns a low TTL (time to live) value to DNS records, thereby avoiding caching on other DNS servers and local DNS caches.

## "Server set" concept

Simple Failover is built around the concept of **server sets**.

A server set represents one or more servers that host the same Internet service (e.g., a web site).

Each server must have a unique IP address,

A server set also defines various other properties, such as the service type (HTTP, FTP, etc.), how often to poll each server (monitoring), how and who to notify if anything goes wrong, the host name(s) for the service, and the DNS servers to update.
