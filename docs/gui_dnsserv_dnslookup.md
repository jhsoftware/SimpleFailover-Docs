---
Slug: dns-server-properties-dialog-dns-lookup
DocID: 32
Keywords: DNS server properties,DNS lookup,EDNS0,TTL value
---
# DNS server properties dialog - DNS lookup

In this section of the DNS server properties dialog, you specify DNS look up settings for this DNS server:

![](images/809bd636857e.png)

 - **Use EDNS0**\
    Enable this option to allow larger DNS packets over UDP with DNS servers that support this.\
    For details on EDNS0 see RFC2671 at <http://www.rfc-editor.org/rfc/rfc2671.txt>

 - **Ignore host record TTL value**\
    Ignore the TTL value when comparing DNS host records retrieved via DNS lookup to the TTL value configured in the [Server set properties dialog / DNS data section](gui_ssprop_dnsdata.md).

 - **Perform a DNS lookup to re-check DNS host records every**\
    Re-check frequency.
