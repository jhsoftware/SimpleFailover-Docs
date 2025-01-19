---
Slug: specific-dns-server-software-simple-dns-plus
Keywords: Simple DNS Plus,JH Software,TSIG
---
# Specific DNS server software - Simple DNS Plus

Simple DNS Plus is a DNS server software package for desktop and server versions of Windows made by JH Software (same company that makes Simple Failover).

For more information on this product see <https://simpledns.com>.

When updating DNS records on Simple DNS Plus with Simple Failover, we recommend using the [Dynamic update via DNS protocol](gui_dnsserv_update.md#dyndns) update method with the "TSIG sign update request" option enabled.

To configure TSIG signed dynamic updates in Simple DNS Plus, click the "Options" button.

![](images/1b2d65290ecb.png)

In the Options dialog, select the "TSIG Updates" section, and click the "Add..." button:

![](images/b1aec5d938f6.png)

In the TSIG Key dialog, enter a key name (for example "simplefailover"), select a signing algorithm, generate a random secret, and optionally specify which domains names Simple Failover is allowed to update:

![](images/549a05c32d5e.png)

Click the OK buttons in this and the previous dialog to save your settings.

In Simple Failover, make sure to use the same settings:

![](images/9bddecea3a1b.png)

Note: Updates can only be performed on primary DNS zones - not on secondary zones.

To ensure that DNS can always be updated (with any one of the DNS servers unavailable), you must configure the zone as primary on all DNS servers.

IMPORTANT: This also means that you will have to keep the DNS servers synchronized manually by always making all zone / record updates on both servers.

Alternatively, you could use the option in Simple Failover to serve DNS requests directly - see [Options dialog / DNS serving section](gui_opt_dnsserving.md).
