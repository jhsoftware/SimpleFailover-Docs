---
Slug: notification-properties-dialog-notify-method
Keywords: Notification properties dialog,Notify method,E-mail,HTTP,Windows event log,Notification,Execute command line,Command line
---
# Notification properties dialog - Notify method

In this section of the Notification properties dialog, you specify how to send the notification:

![](images/1cd5806420b2.png)

 - **Notification method**\
Select one of the available notification methods:

    - [E-mail](gui_notify_method.md#email)

    - [HTTP](gui_notify_method.md#http)

    - [Execute command line](gui_notify_method.md#cmdline)

    - [Windows Events Log](gui_notify_method.md#winevent)

 - **Test... button**\
Click this button to send a test notification using the settings specified in the Notify method section.

---

## Notification method - E-mail{#email}

Use this notification method to send notifications via e-mail:

 ![](images/a24fd7611f31.png)

- **To e-mail address**\
The e-mail address to send the notification to.

- **Use default from e-mail address**\
Check this option to use the default from e-mail address specified in the [E-mail notification defaults dialog](gui_emaildef.md).\
Click the "Edit defaults..." button at the bottom of the page to edit the e-mail notification default settings.

- **From e-mail address**\
The e-mail address that will appear as the From address in e-mail notifications.\
You may wish to use a unique e-mail address for this to allow the recipient to create special processing rules for this in their e-mail client software.

- **Use default subject and message body**\
Check this option to use the default subject and message body specified in the [E-mail notification defaults dialog](gui_emaildef.md).\
Click the "Edit defaults..." button at the bottom of the page to edit the e-mail notification default settings.

- **Subject**\
The subject text that will appear in e-mail notification messages.\
You may wish to use a unique subject text to allow the recipient to create special processing rules for this in their e-mail client software.\
Optionally include one or more of the $...$ tags listed which will be replaced with context specific values at the time of execution.

- **Message body**\
The message body text that will appear in e-mail notification messages.\
Optionally include one or more of the $...$ tags listed which will be replaced with context specific values at the time of execution.

- **Use default server and authentication**\
Check this option to use the default server and authentication specified in the [E-mail notification defaults dialog](gui_emaildef.md).\
Click the "Edit defaults..." button at the bottom of the page to edit the e-mail notification default settings.

- **SMTP server (host name or IP address)**\
The SMTP server host name or IP address that you want Simple Failover to send e-mail notifications through.

- **Port**\
The TCP port number of the SMTP server. Most SMTP servers use port 25.

- **Use SSL / TLS**\
Check this to use encryption when sending e-mail notifications.

- **Use SMTP authentication**\
To block spam and viruses, many e-mail servers require authentication for outgoing e-mail.\
Check this option and enter your User ID and Password as required by the SMTP server.\
Make sure to use the "Test..." button to ensure that Simple Failover can successfully authenticate before relying on this feature.

- **Edit defaults... button**\
Click to open the [E-mail notification defaults dialog](gui_emaildef.md).

--- 

## Notification method - HTTP{#http}

With this notification method, Simple Failover will send the notification data via HTTP. Use this to trigger a script on a web-server to handle notification - for example an SMS / texting service.

![](images/572b6c1f8007.png)

- **HTTP method**\
Select GET, POST, or PUT

- **URL**\
The full URL to send notification data to.\
Optionally include one or more of the $...$ tags listed which will be replaced with context specific values at the time of execution.

- **Custom request headers**\
Custom HTTP request headers for web-services that require this (optional).\
Optionally include one or more of the $...$ tags listed which will be replaced with context specific values at the time of execution.

- **Request body** (only available when HTTP method is POST or PUT)\
Data to be included in the body of requests.\
Optionally include one or more of the $...$ tags listed which will be replaced with context specific values at the time of execution.

- **Use HTTP authentication**\
Check this option if the URL is password protected to enter User ID and password.

---

## Notification method - Execute command line{#cmdline}

With this notification method, you can use your own program or script to send the notification.

It is possible to run executables (.exe) and batch (.bat) files directly, as well as most types of script languages through Windows Scripting Host (WSH) by executing "cscript.exe". For more on WSH see [http://en.wikipedia.org/wiki/Windows\_Script\_Host](http://en.wikipedia.org/wiki/Windows_Script_Host)

![](images/29bf034eca47.png)

- **File to execute**\
Specify the full path to the file to be executed. Optionally click the "..." button to browse for the file.

- **Arguments**\
Specify any command line arguments needed.\
Optionally include one or more of the $...$ tags listed which will be replaced with context specific values at the time of execution.

---

## Notification method - Windows Event Log{#winevent}

This notification method simply writes an entry to the Windows Event Log (see Windows Control Panel / Administrative Tools / Event Viewer).

This notification method has no configurable settings.
