---
Slug: options-dialog-http-api
DocID: 13
Keywords: Options dialog,HTTP API
---
# Options dialog - HTTP API

In this section of the Options dialog, you can configure settings related to the [HTTP API](httpapi.md):

![](images/7b7d959e6301.png)

- **Enable HTTP API**\
Enable / disable the HTTP API interface.

    - **URL prefix**\
    The URL prefix that Simple Failover should listen for HTTP API requests on.\
    The default "http://127.0.0.1:8100" will listen for HTTP requests on IP 127.0.0.1 port 8100.\
    Read more about the URL prefix format at <http://msdn.microsoft.com/en-us/library/windows/desktop/aa364698(v=vs.85).aspx>

    - **Password**\
    Specify a password for the HTTP API (the username is always "admin").\
    Leave the password field blank if you do not wish to password protect the HTTP API.

    - **Log HTTP API requests**\
    Check this to enable logging of HTTP API requests.
