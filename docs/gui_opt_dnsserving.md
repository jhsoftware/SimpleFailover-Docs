---
Slug: options-dialog-dns-serving
Keywords: Options dialog,DNS serving,Serve DNS requests directly,Forward un-matches DNS requests
---
# Options dialog - DNS serving

In this section of the Options dialog, you can configure settings related to serving DNS requests directly.

Simple Failover can act as a simple DNS server, responding to DNS requests for host records (A / AAAA) for the host names configured for any server set in the [Server set properties dialog / DNS data section](gui_ssprop_dnsdata.md).

DNS requests that it cannot answer itself (unknown host names / other record types) can be forwarded to another DNS server.

![](images/036239a27125.png)

- **Serve DNS requests directly**\
Check this to enable serving DNS requests directly.

    - **On IP address**\
    Select the local IP address on which to serve DNS requests.

    - **Port**\
    Select the port number (1-65535) on which to serve DNS requests.\
    Other DNS servers / resolvers will generally always send DNS requests to port 53.\
    However if for example you are using port mapping on a NAT router, you could use a different port number here - freeing up the local port 53 to run something else - for example a DNS server that you will be forwarding un-matched requests to (see below).

    - **Forward un-matched DNS requests**\
    Check this to enable forwarding of un-matched DNS requests.

        - **To DNS server IP address**\
        Specify the IP address of the DNS server to forward to.

        - **Port**\
        Specify the port number to forward to.\
        Most DNS servers will listen for DNS requests on port 53 by default.

        - **Clear RD/RA flags (disables recursion)**\
        With this option enabled, Simple Failover will clear the RD (recursion desired) flag on DNS requests before forwarding, and it will clear the RA (recursion available) flag on DNS responses before returning this.\
        This will make it appear that the client does not request recursion, and that the server does not offer it.\
        If you cannot disable recursion on the DNS server being forwarded to (either because it has no such option, or because it needs to perform recursion for other clients), this will help prevent certain kinds of DNS attacks like DNS spoofing.
