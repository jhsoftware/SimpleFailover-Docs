---
Slug: server-set-properties-dialog-polling-method
DocID: 17
Keywords: Server set properties dialog,Polling method,PING,TCP connect,HTTP,HTTPS,SSL,FTP,SMTP,POP3,NNTP,IMAP,WSH,Execute command line,Command line
---
# Server set properties dialog - Polling method

In this section of the Server set properties dialog, you can specify how servers are polled:

![](images/daa350cb51ed.png)

- **Polling method**

Select one of the available polling methods:

- [Ping (ICMP ECHO)](gui_ssprop_pollingmethod.md#ping)

- [HTTP](gui_ssprop_pollingmethod.md#http)

- [TCP connect](gui_ssprop_pollingmethod.md#tcp)

- [DNS](gui_ssprop_pollingmethod.md#dns)

- [Execute command line](gui_ssprop_pollingmethod.md#cmd)

---

## Polling method - Ping (ICMP ECHO){#ping}

With this polling method, an ICMP Echo Request (ping) is sent to the server IP address. If the server responds with a matching ICMP Echo Reply, then the server is considered functional. If a negative response (for example "destination unreachable") is received from a router somewhere in between Simple Failover and the server, or if no response is received, then the server is considered non-functional.

The advantage of this polling method is that it is very simple and lightweight (no TCP connection overhead), it uses very little bandwidth (ping packets are very small), and it can be used for any type of Internet service. 

The disadvantage is that it can only detect if a server computer is running and is connected to the network. Unlike the other polling methods, ping cannot determine if a specific service on the server computer is running and functioning correctly. 

 Please note that some firewalls are configured to filter out PING packets (ICMP protocol), in which case this polling method cannot be used (check this by pinging your server IP from a command prompt first).

This polling method has no configurable settings.

---

## Polling method - HTTP{#http}

With this polling method, an HTTP request is sent to the server, and the response is evaluated:

![](images/c2f31399e623.png)

- **HTTP method**\
Can be either GET or HEAD.\
With GET, a full HTTP response is requested from the server, with HEAD, only the response headers are requested.\
Using HEAD saves bandwidth, but you will not be able to evaluate the body content (see success criteria below). 

- **Poll URL**\
The full URL of the content you wish to retrieve from the server.\
Start the URL with https:// to use SSL. URL may include a non-standard port number.

- **Success criteria (in addition to getting a valid HTTP response)**\
Specify criteria for when the server is responding correctly.

    - **Response status code**\
    Enable to evaluate the response status code. Typically, a successful HTTP response has status code 200.

    - **Response content length is**\
    Enable to evaluate the response content length

    - **Response body text**\
    Enable to evaluate the body text.\
    You can choose either "contains", "does not contain", "matches regular expression", or "does not match regular expression".\
    For more on regular expressions, see [http://en.wikipedia.org/wiki/Regular\_expression](http://en.wikipedia.org/wiki/Regular_expression)

---

## Polling method - TCP connect{#tcp}

This polling method can be used to check any type of service that uses the TCP protocol - which includes most software communicating via the Internet protocol.

Once the TCP connection is established, many such services send back a greeting message including some kind of status code. It is possible to wait for and evaluate this greeting.

Pre-configured settings are available for FTP, SMTP, POP3, NNTP, and IMAP servers.

![](images/fbc0113790fa.png)

- **Server type**\
Choose "Custom" to configure the remaining settings manually, or choose between "FTP", "SMTP", "POP3", "NNTP", and "IMAP" to use standard values for these types of servers.

- **TCP port**\
The TCP port number (1 to 65535) to connect to.

- **Success criteria (in addition to establishing TCP connection):**\
Specify criteria for when the server is responding correctly.

- **Wait for getting (first line / 100 characters received)**\
Enable this to wait for the server greeting.

    - **Timeout**\
    How long to wait for the server greeting.

    - **Greeting must**\
    Enable to evaluate the greeting text.\
    You can choose either "start with", "not start with", "contain", "not contain", "match regular expression", "not match regular expression".\
    For more on regular expressions, see [http://en.wikipedia.org/wiki/Regular\_expression](http://en.wikipedia.org/wiki/Regular_expression)

 ---

## Polling method - DNS{#dns}

With this polling method, a DNS request is sent to a DNS server, and the response is evaluated:

![](images/e37c046c5011.png)

- **Send DNS request for host name**\
Specify the host name to query the DNS server about.

- **Request record type**\
Specify the record type to query the DNS server about (A / AAAA).

- **Request recursion (set RD flag in request)**\
Specify if the DNS request RD flag should be set. Typically used if testing the DNS server's ability to do recursion / the host name is not hosted on the DNS server itself.

- **Success criteria (in addition to receiving a valid DNS response)**

    - **Response must contain host record pointing to IP address**\
    Specify the expected IP address.

    - **Response must be authoritative (AA flag set)**\
    Specify if the response must be authoritative (host name is hosted in the DNS server itself)

---

## Polling method - Execute command line{#cmd}

With this polling method, you can use your own program or script to poll the servers. Simple Failover can evaluate the exit code and/or standard output (STDOUT) from your program / script in order to determine if the server poll was successful.

It is possible to run executables (.exe) and batch (.bat) files directly, as well as most types of script languages through Windows Scripting Host (WSH) by executing "cscript.exe". For more on WSH see [http://en.wikipedia.org/wiki/Windows\_Script\_Host](http://en.wikipedia.org/wiki/Windows_Script_Host)

![](images/382364691f8c.png)

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
    The exit code is an integer value which you can evaluate for equality (= / not =) or greater/lesser than (\> / \<) against a specified value.\
    Typically exit code 0 (zero) indicates success while other exit codes indicate some type of error condition.

    - **Standard output**\
    Enable to evaluate the standard output (STDOUT) returned by your program / script.\
    You can choose either "contains", "does not contain", "matches regular expression", or "does not match regular expression".\
    For more on regular expressions, see [http://en.wikipedia.org/wiki/Regular\_expression](http://en.wikipedia.org/wiki/Regular_expression)

 - **Don't wait for process to exit. Assume success.**\
Choose this option if your program / script does not return any usable exit code or standard output.\
The server poll will be considered successful as long as the process starts.
