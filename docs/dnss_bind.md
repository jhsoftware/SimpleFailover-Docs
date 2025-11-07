---
Slug: specific-dns-server-software-bind
DocID: 40
Keywords: BIND,Berkeley Internet Name Domain,TSIG,named.conf
---
# Specific DNS server software - BIND

BIND (Berkeley Internet Name Domain) is a DNS server software package available for various operating systems.

For more information on this product see [www.isc.org](http://www.isc.org).

When updating DNS records on BIND, we recommend using the [Dynamic update via DNS protocol](gui_dnsserv_update.md#dyndns) update method with the "TSIG sign update request" option enabled.

In BIND, TSIG signed dynamic DNS updates are configured individually for each DNS zone.

Open the BIND configuration file (named.conf) file in a text editor, and add a key section in the top of the file, and add a matching allow-update statement to the zone you want Simple Failover to update as follows:

![](images/e7131e07627d.png)

IMPORTANT: make sure to add a period (.) after the key name (following the word *key*) in both sections.

The zone file must be placed in a directory where dynamic updates are allowed. In the screenshot you can see, that we have placed the simplefailover.com.zone file in the dyn directory.

Command line tools are available with BIND to create key values (secrets).

However, it is easier (and just as secure) to use the Generate button in the Simple Failover for this (see screenshot below).

After editing and saving the named.conf file, you must restart BIND for the changes to take effect.

The key, algorithm and the secret must match the settings in  Simple Failover:

![](images/daa96598ceca.png)

Note: Updates can only be performed on primary DNS zones - not on secondary zones.

To ensure that DNS can always be updated (with any one of the DNS servers unavailable), you must configure the zone as primary on all DNS servers.

IMPORTANT: This also means that you will have to keep the DNS servers synchronized manually by always making all zone / record updates on both servers.

Alternatively, you could use the option in Simple Failover to serve DNS requests directly - see [Options dialog / DNS serving section](gui_opt_dnsserving.md).
