---
Slug: dns-server-properties-dialog-update-method
DocID: 33
Keywords: DNS server properties,Update method,Dynamic update via DNS protocol,HTTP,Execute command line,Command line,TSIG,Microsoft DNS server
---
# DNS server properties dialog - Update method

In this section of the DNS server properties dialog, you specify how to update DNS records on this DNS server:

![](images/6d2b8ec5f8b6.png)

 - **Update method**\
Select one of the available notification methods:

    - [Dynamic update via DNS protocol](gui_dnsserv_update.md#dyndns)

    - [HTTP](gui_dnsserv_update.md#http)

    - [Execute command line](gui_dnsserv_update.md#cmdline)

    - [Microsoft DNS server (dnscmd.exe)](gui_dnsserv_update.md#msdns)

---

## Update method - Dynamic update via DNS protocol{#dyndns}

This DNS update method sends updates directly to the DNS server via the DNS protocol (UDP port 53).

For in-depth technical details about this update method, see RFC2136 - <http://www.rfc-editor.org/rfc/rfc2136.txt>

![](images/daa96598ceca.png)

 - **TSIG sign update request**\
    TSIG signing is a secure method of authenticating the client (in this case Simple Failover) to the DNS server.\
    We highly recommend that you configure your DNS servers not to accept un-signed dynamic update requests - as this would allow anyone to send it updates.\
    Most modern DNS servers support TSIG signed dynamic updates - with the notable exception of Microsoft's DNS server (their "secure updates" is non-compatible variant of this). We therefore recommend using the "Microsoft DNS server (dnscmd.exe)" update method instead.\
    For in-depth technical details about TSIG signing DNS requests, see [RFC2845](http://www.rfc-editor.org/rfc/rfc2845.txt).

    - **Algorithm**\
        The HMAC hash algorithm used to sign update requests. Must match settings on the DNS server.\
        If the DNS server does not allow you the specify an algorithm, this typically means that the DNS server only supports HMAC-MD5.

    - **Key name**\
        The key name used to sign update requests. Must match settings on the DNS server.\
        This is basically equivalent to a username and must be specified in domain name format, but can otherwise be anything you like.\
        The RFC recommendation is to use a name which identifies both the client and the server e.g. "client.domain1.server.domain2". However, it works just as well (and is probably easier) using just a simple name like "testuser".

    - **Secret (base64)**\
        The secret (in base64 format) used to sign update requests. Must match settings on the DNS server.\
        This is basically equivalent to a password.

    - **Generate button**\
        Click this button will generate a new random secret value.

---

## Update method - HTTP{#http}

This DNS update method sends updates to the DNS server via HTTP.

This might be used for example with a dynamic DNS service provider who offers an HTTP interface to update DNS records.

![](images/8ceb1be5bca2.png)

 - **HTTP method**\
Select GET, POST or PUT.

 - **Update URL**\
The full URL of page / script that will update the DNS server.\
Optionally include one or more of the $...$ tags listed which will be replaced with context specific values at the time of execution.

 - **Custom request headers**\
Custom HTTP request headers for web-services that require this (optional).\
Optionally include one or more of the $...$ tags listed which will be replaced with context specific values at the time of execution.

 - **Request body** (only available when HTTP method is POST or PUT)\
Data to be included in the body of requests.\
Optionally include one or more of the $...$ tags listed which will be replaced with context specific values at the time of execution.

 - **Use HTTP authentication**\
Check this option if the URL is password protected to enter User ID and password.

 - **Success criteria (in addition to getting a valid HTTP response)**\
Specify criteria for when the server is responding correctly and the DNS update was performed.

    - **Response status code**\
    Enable to evaluate the response status code. Typically, a successful HTTP response has status code 200.

    - **Response content length is**\
    Enable to evaluate the response content length

    - **Response body text**\
    Enable to evaluate the body text.\
    You can choose either "contains", "does not contain", "matches regular expression", or "does not match regular expression".\
    For more on regular expressions, see [http://en.wikipedia.org/wiki/Regular\_expression](http://en.wikipedia.org/wiki/Regular_expression)

---

## Update method - Execute command line{#cmdline}

With this DNS update method, you can use your own program or script to do the update.

It is possible to run executables (.exe) and batch (.bat) files directly, as well as most types of script languages through Windows Scripting Host (WSH) by executing "cscript.exe". For more on WSH see [http://en.wikipedia.org/wiki/Windows\_Script\_Host](http://en.wikipedia.org/wiki/Windows_Script_Host)

![](images/655118a0fbe3.png)

 - **File to execute**\
Specify the full path to the file to be executed. Optionally click the "..." button to browse for the file.

 - **Arguments**\
Specify any command line arguments needed.\
Optionally include one or more of the $...$ tags listed which will be replaced with context specific values at the time of execution.

 - **Wait for process to exit for \_\_ seconds. Success criteria:**\
Choose this option if you want Simple Failover to wait to the process to exit and evaluate the exit code or standard output.\
Specify how many seconds to wait for the process to exit.

    - **Exit code**\
    Enable this to evaluate the exit code returned by your program / script.\
    The exit code is an integer value, and you can evaluate this for equality (= / not =) or greater/lesser than (\> / \<) against a specified value.\
    Typically exit code 0 (zero) indicates success while other exit codes indicate some type of error condition.

    - **Standard output**\
    Enable to evaluate the standard output (STDOUT) returned by your program / script.\
    You can choose either "contains", "does not contain", "matches regular expression", or "does not match regular expression".\
    For more on regular expressions, see [http://en.wikipedia.org/wiki/Regular\_expression](http://en.wikipedia.org/wiki/Regular_expression)

 - **Don't wait for process to exit. Assume success.**\
Choose this option if your program / script does not return any usable exit code or standard output.\
The DNS update will be considered successful as long as the process starts.

---

## Update method - Microsoft DNS server (dnscmd.exe){#msdns}

With this DNS update method, you can update a Microsoft DNS server (using the Microsoft "dnscmd.exe" command line tool behind the scenes).

This update method is included in Simple Failover because Microsoft's DNS server does not support standard TSIG signed dynamic DNS update requests, and therefore cannot be updated securely using that method.

![](images/bede5030005a.png)

 - **Local Microsoft DNS server (on this computer)**\
Select this option if you want to update a Microsoft DNS server on the same computer as is running Simple Failover.

 - **Remote Microsoft DNS server (on another computer)**\
Select this option if you want to update a Microsoft DNS server on another computer.\
The Microsoft DNS server computer must be running the "Simple Failover - Microsoft DNS update agent" - see <https://simplefailover.com/mdua.aspx>

    - **TCP port**\
    The TCP port set in the "Simple Failover - Microsoft DNS update agent" on the Microsoft DNS server computer.

    - **Password**\
    The password set in the "Simple Failover - Microsoft DNS update agent" on the Microsoft DNS server computer.
