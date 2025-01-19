---
Slug: options-dialog-server-polling
Keywords: Options dialog,Server polling,Polling history database
---
# Options dialog - Server polling

In this section of the Options dialog, you can configure general settings related to server polling and the polling history database:

![](images/86880f407d34.png)

- **Max. concurrent servers polls**\
Defines the maximum number of servers that may be polled at the same time. 

- **Polling history database**\
Settings related to the polling history database - see also [Server polling history dialog](gui_hist.md).\
Note: The polling history is stored in a Microsoft SQL Server Compact database. The database file "poll-history.sdf" is stored in the application data directory (typically "C:\ProgramData\JH Software\Simple Failover").

    - **Only record poll result when server status changes**\
    To save disk space - and to make the log easier to read.

    - **To reduce disk space usage purge entries older than \_\_\_ days**\
    How long to retain history data.
