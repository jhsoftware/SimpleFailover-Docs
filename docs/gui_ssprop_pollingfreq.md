---
Slug: server-set-properties-dialog-polling-frequency
DocID: 18
Keywords: Server set properties dialog,Polling frequency
---
# Server set properties dialog - Polling frequency

In this section of the Server set properties dialog, you can specify how often servers are polled:

![](images/d4d7557b798a.png)

- **Polling interval when all server polls are successful**\
How often this Server set is polled.\
You should balance this between how quickly you want problems detected, and how much traffic you want Simple Failover to cause.\
Note: Polling too often may be flagged as a DOS attack by some firewalls.

- **Polling interval when one or more server pools have failed**\
After a problem first is detected, subsequent polls will use this interval.

- **Retry failed polls \_\_ times - at an interval of**\
Retry failed polls this number of times / at this interval before considering the server failed.

- **Poll servers sequentially and stop at first successfully polled server**\
Enable this if you don't want to poll backup/standby servers as long as your primary servers are responding correctly.
