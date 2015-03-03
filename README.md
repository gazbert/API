# Coinfloor Trade Engine APIs

Coinfloor's application programming interfaces (APIs) provide our clients programmatic access to control aspects of their accounts and to place orders on the Coinfloor trading platform.

Coinfloor provides two interfaces to our API: an [HTTP API][BIST] and a full [WebSocket API]. Using these interfaces, it is possible to make both authenticated and unauthenticated API calls.

Access keys are available on the Coinfloor logged-in dashboard page for verified users which, in conjunction with your account password, allow use of either API.

---
## General notes

To protect the performance of the system, Coinfloor imposes certain limits on the rates at which you may issue commands to the API. Please see [LIMITS.md].

All quantities and prices are transmitted and received as integers with implicit scale factors. For scale information, please see [SCALE.md].

Coinfloor has published [client libraries] for several popular languages to aid you in implementing your client application.

---
## Getting started with the HTTP API

The HTTP API is accessible via HTTPS connection to **webapi.coinfloor.co.uk** on port **8090**.

```text
https://webapi.coinfloor.co.uk:8090/bist/
```

[Click here for more details on how to use the HTTP Web API][BIST]

---
## Getting started with the WebSocket API

The WebSocket API is accessible on **api.coinfloor.co.uk** on port **80** for unencrypted transport and port **443** for TLS transport.

```text
ws://api.coinfloor.co.uk/ (unencrypted)
wss://api.coinfloor.co.uk/ (encrypted)
```

Commands, replies, and notifications traverse the WebSocket in text frames with JSON-formatted payloads.

***We strongly recommend that you use TLS transport for all connections.***

WebSocket connections to the API will timeout after 60 seconds of no traffic passing in either direction. To prevent timeouts, send a Ping frame approximately every 45 seconds while the connection is otherwise idle. You do not need to send Ping frames if you are otherwise sending or receiving data frames on the socket.

[Click here for more details on how to use the WebSocket API][WebSocket API]



[BIST]: https://github.com/coinfloor/API/blob/master/BIST.md
[WebSocket API]: https://github.com/coinfloor/API/blob/master/WEBSOCKET-README.md
[SCALE.md]: https://github.com/coinfloor/API/blob/master/SCALE.md
[LIMITS.md]: https://github.com/coinfloor/API/blob/master/LIMITS.md
[client libraries]: https://github.com/coinfloor/API/
