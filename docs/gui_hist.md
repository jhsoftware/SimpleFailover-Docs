---
Slug: server-polling-history-dialog
DocID: 36
Keywords: Server polling history dialog,Polling history database
---
# Server polling history dialog

The Server poling history dialog lists recent polls for a server.

You reach this dialog from the [main window / Server Sets tab](gui_main_sstab.md) by selecting a server set in the left list, expand the details for a server (right pane of content area), and clicking the "Polling history..." button.

Note: In the [Options dialog / Server polling section](gui_opt_serverpolling.md), you can configure Simple Failover to "Only record poll result when server status changes", and "purge entries older than \_\_\_ days" which reduces the number of events listed here.

![](images/6b9780e6c506.png)

 - **Filter by**

    - **Event type**\
    Can limit the events listed by event type.

    - **Dates**\
    Can limit the events listed by date.

 - **Save to disk... button**\
Save the list to disk in .csv (command separated values) format.

 - **Close button**\
Closes this dialog.

Note: The polling history is stored in a Microsoft SQL Server Compact database. The database file "poll-history.sdf" is stored in the application data directory (typically "C:\ProgramData\JH Software\Simple Failover").
