---
Slug: e-mail-notification-defaults-dialog
DocID: 35
Keywords: E-mail notification defaults,E-mail,Notification
---
# E-mail notification defaults dialog

The E-mail notification defaults dialog  is used to specify default settings for e-mail notifications.

You reach this dialog either from the [Options dialog / Notification section](gui_opt_notification.md) by clicking the "E-mail notification defaults..." button, or from the [Notification properties dialog / Notify method section](gui_notify_method.md) selecting the "e-mail" notification method and clicking the "Edit defaults..." button at the bottom of the page.

![](images/603bda62546c.png)

 - **From e-mail address**\
The e-mail address that will appear as the From address in e-mail notifications.\
You may wish to use a unique e-mail address for this to allow the recipient to create special processing rules for this in their e-mail client software.

 - **Subject**\
The subject text that will appear in e-mail notification messages.\
You may wish to use a unique subject text to allow the recipient to create special processing rules for this in their e-mail client software.\
Optionally include one or more of the $...$ tags listed which will be replaced with context specific values at the time of execution.

 - **Message body**\
The message body text that will appear in e-mail notification messages.\
Optionally include one or more of the $...$ tags listed which will be replaced with context specific values at the time of execution.

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

 - **Test... button**\
Click this button to send a test e-mail using the settings specified above.
