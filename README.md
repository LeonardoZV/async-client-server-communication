# Asyncronous Client Server Interaction
This guide has the objective to show the difference between the most common methods of asynchronous communication between client and server, as well to show how to implement them.

## (Long) Polling

Your front-end has the responsibility of regularly asking your back-end if there is any fresh data. Hence the front will make the same call every few seconds/minutes. Sometimes one of those calls will have a fresh data to handle. Latency is increased, as the front-end has to wait for the next pool to get the most updated data. Bandwidth is increased, as the front-end creates lots of requests (requests contain data) to the back-end even when there is no data for the back-end to return, which is waste.

Long polling is different in the fact that the request is kept open by the server as long as possible until it eventually returns a fresh data or reaches a timeout.

Example Architecture:

## WebSocket

Your front-end opens a long-lasting, bi-directional communication with your back-end through a WebSocket protocol. Thus, the back can push a message as soon as necessary and vice versa. Latency and Bandwidth are decreased, as the data will be exchanged exactly when it's available.

This is the only standard and official solution supported by AWS.

Best use cases: Google Wave type of applications, chat applications, anything that needs bi-directional communication.

Example Architecture:

## Server-Sent Events

Your front-end opens a long-lasting, uni-directional communication from your back-end to your front-end through the HTTP protocol. Here as well, the back-end can push a message as soon as necessary. If you want client to server communication, you'll need do make a separated POST request.

Best use cases: Stock prices updates, notifications, anything that needs uni-directional communication.

Example Architecture:

## HTTP2 Push :skull:	

Developers from Chromium removed the support for this feature. As Chrome has 70% of market share (2022), they are effectively killing HTTP2 Push. As HTTP2 Push is not mandatory, Chromium keeps being HTTP2 compliant.

Chromium Team announcement (2021): https://groups.google.com/a/chromium.org/g/blink-dev/c/K3rYLvmQUBY/m/0o4J1GEjAgAJ
