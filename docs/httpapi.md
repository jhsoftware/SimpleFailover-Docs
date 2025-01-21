---
Slug: http-api
DocID: 42
Keywords: HTTP API,REST,JSON
---
# HTTP API

Nearly all the functions found in the Simple Failover UI are also available through a REST based HTTP API.

The HTTP API is enabled and configured in the [Options dialog / HTTP API section](gui_opt_httpapi.md).

The HTTP API URLs which return or accept data do so in JSON format.

In order to learn the data format for POST / PUT methods, copy/examine the data returned by the corresponding GET methods.

The following table describes the available URLs and HTTP methods available with the HTTP API:

|**URL**|**HTTP Method**|**Description**|**Remarks**
|---|---|---|---|
|/log|GET|Fetch the latest log lines|The number of log lines cached is configured in the Options dialog / Logging section|
|/options|GET|Fetch current program options||
|/options|PUT|Update program options|Request body must include complete program options in JSON format|
|/pauseall|POST|Pauses all server polling|Same as checking "Pause all polling" button in GUI
|/pollall|POST|Polls all server sets immediately|Same as clicking "Poll all server sets" button in GUI|
|/problems|GET|Fetch a list of current problems||
|/resumeall|POST|Resumes all server polling|Same as un-checking "Pause all polling" button in GUI|
|/serversets|GET|Fetch list of server sets||
|/serversets|POST|Create a new server set|Request body must include complete server set configuration in JSON format|
|/serversets/\<server-set-id\>|GET|Fetch short info (name, status) for server set||
|/serversets/\<server-set-id\>|DELETE|Delete server set||
|/serversets/\<server-set-id\>/config|GET|Fetch a server set configuration||
|/serversets/\<server-set-id\>/config|PUT|Update a server set configuration|Request body must include complete server set configuration in JSON format|
|/serversets/\<server-set-id\>/pause|POST|Pause server set.|Same as checking the "Pause" button in GUI.|
|/serversets/\<server-set-id\>/poll|POST|Poll the server set immediately.|Same as clicking the "Poll now" button in GUI.|
|/serversets/\<server-set-id\>/resume|POST|Resume server set.|Same as un-checking the "Pause" button in GUI.|
|/serversets/\<server-set-id\>/status|GET|Fetch detailed current status of a server set, including individual servers and  DNS servers / host names statuses.||

 

Note: The Simple Failover v. 2.0 (and later) HTTP API is not compatible with that from Simple Failover v. 1.x (v. 2 is REST based and uses JSON / v. 1.x is not REST based and uses XML)
