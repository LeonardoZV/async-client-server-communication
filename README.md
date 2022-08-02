# Asyncronous Client Server Interaction
This guide has the objective to show the difference between the most common methods of asynchronous communication between client and server, as well to show how to implement them.

## Polling

Example Architecture:

## WebSocket

Your front-end opens a long-lasting, bi-directional communication with your back-end through a WebSocket protocol. Thus, the back can push a message as soon as necessary and vice versa.

The only standard and official solution supported by AWS.

Best use cases: Google Wave type of applications, Chat Applications, anything that needs bidirecional communication.

Example Architecture:

## Server-Sent Events

Your front-end opens a long-lasting, uni-directional (from server to client) communication from your back-end through the HTTP protocol. Here as well, the back-end can push a message as soon as necessary. If you want client to server communication, you need do make a separated POST request.

Best use cases: Stock prices updates, notifications, anything that needs unidirecional communication.

Example Architecture:

## HTTP2 Push :skull:	

Developers from Chromium removed the support of this feature. As Chrome has 70% of market share (2022), they are effectively killing HTTP2 Push. As HTTP2 Push is not mandatory, Chromium keeps being HTTP2 compliant.

Chromium Team announcement (2021): https://groups.google.com/a/chromium.org/g/blink-dev/c/K3rYLvmQUBY/m/0o4J1GEjAgAJ
