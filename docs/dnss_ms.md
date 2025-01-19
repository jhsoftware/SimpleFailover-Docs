---
Slug: specific-dns-server-software-microsoft-dns
Keywords: Microsoft DNS server,Windows Server
---
# Specific DNS server software - Microsoft DNS

Microsoft's DNS server software is included with the server versions of Windows.

Unlike most other DNS servers, Microsoft's DNS server does not support standard TSIG signed dynamic DNS updates.

Note: What the Microsoft's DNS UI refers to as "secure dynamic updates" (a.k.a. "GSS-TSIG Kerberos authenticated DNS updates") is something very different and incompatible.

So unfortunately, Simple Failover has no way to securely update a Microsoft DNS server directly via the DNS protocol.

Simple Failover does however provide another update method specifically for Microsoft DNS servers - utilizing Microsoft's "dnscmd.exe" tool behind the scenes.

![](images/bede5030005a.png)

If you want to update a Microsoft DNS server on a remote computer, that computer must be running the "Simple Failover - Microsoft DNS update agent" program - see <https://simplefailover.com/mdua.aspx>

Note: Updates can only be performed on "Standard Primary" and "Active Directory Integrated" DNS zones - not on secondary zones.

To ensure that DNS can always be updated (with any one of the DNS servers unavailable), you must configure the zone as "Standard Primary" or as "Active Directory Integrated" on all DNS servers.

IMPORTANT: This also means that unless you are using an "Active Directory Integrated" zone, you will have to keep the DNS servers synchronized manually by always making all zone / record updates on both servers.

Alternatively, you could use the option in Simple Failover to serve DNS requests directly - see [Options dialog / DNS serving section](gui_opt_dnsserving.md).
