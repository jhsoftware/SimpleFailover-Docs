---
Slug: main-window-server-sets-tab
DocID: 3
Keywords: Main window,Server Sets tab,Polling history,Ping
---
# Main window - Server Sets tab

The content area of main window Server Sets tab contains a list of server sets (left) and a status page for the currently selected server set (right):

![](images/357633437025.png)

Each server set in the list (left) also has an icon indicating the current overall status of the server set: green / check mark = all ok, red / cross = one or more problems, grey / ? = unknown status.

The status page (right) displays detailed status information for individual servers and for individual DNS servers / host names.

Click the white circle with the arrow down to "open" further details for each item.

For servers this reveals two buttons:

 - **Polling history...**\
Clicking this button opens the [Server polling history dialog](gui_hist.md) for this server.

 - **Ping...**\
Clicking this button opens a new command line window running "ping" with this server's IP address. For quick diagnostics.

## Toolbar buttons

When the Servers Sets tab is selected, the toolbar has the following extra buttons:

- **New server set**\
Click this button to create a new server set. Takes you to the [Server set properties dialog](gui_ssprop.md).

- **Pause**\
Pause / resume polling for the currently selected server set.

- **Poll now**\
Makes Simple Failover poll the currently selected server set immediately - not waiting for the next cycle.

- **Delete**\
Deletes the currently selected server set.

- **Properties**\
Opens the [Server set properties dialog](gui_ssprop.md) for the currently selected server set.
