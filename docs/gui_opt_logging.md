---
Slug: options-dialog-logging
DocID: 12
Keywords: Options dialog,Logging,Write log files to disk
---
# Options dialog - Logging

In this section of the Options dialog, you can configure general settings related to logging:

![](images/c0f557113bbf.png)

- **Number of log lines to cache and show in the main window 'Log' tab**\
The number of log lines cached, available in the main window - Log tab, and available through the [HTTP API](httpapi.md) "/log" URL.\
When this number of lines is exceeded, the oldest entries are removed to make room for new.

- **Write log files to disk**\
Check this to enable writing log files to disk.

    - **Directory**\
    Where to write the log files. Click the "..." to browse for directory.

    - **Create a new log file every**\
    How often a new log file should be started - every "Hour", "Day", or "Month".

- **Time zone for log time stamps, file naming and rollover**\
Time zone - "UTC" or "Local". Selecting "Local" will use the time zone configured in the Windows operating system.
