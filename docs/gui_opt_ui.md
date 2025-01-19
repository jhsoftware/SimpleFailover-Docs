---
Slug: options-dialog-user-interface
Keywords: Options dialog,User interface,System tray,Sound file
---
# Options dialog - User interface

In this section of the Options dialog, you can configure settings related to the Simple Failover user interface:

![](images/4ae9ddf5a3cc.png)

- **Launch user interface to system tray at Windows login**\
With this option enabled, the Simple Failover user interface will automatically be started as an icon in the [system tray](gui_tray.md) whenever you logon to Windows.\
Note that Simple Failover always runs in the background as a Windows service, even when no user logged into Windows. The Simple Failover user interface is a separate program which is only needed for configuring and monitoring Simple Failover.

- **Show system tray pop-up message when a problem is detected**\
With this option enabled, Simple Failover will show a balloon tip notification from the [system tray](gui_tray.md) icon whenever a problem is detected (only when a user is logged into Windows and the Simple Failover user interface is loaded).

- **Play a sound when a problem is detected / Sound file**\
With this option enabled, Simple Failover will play the specified sound file whenever a problem is detected (only when a user is logged into Windows and the Simple Failover user interface is loaded).
