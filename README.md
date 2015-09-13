# neobnc

Multi-tenant IRC bouncer (BNC), written in Go.

**Status**: Everything is hard-coded but it barely-works?

## Goals

* v1: Multi-user, low resource usage (target self-hosting on Raspberry Pi).
* v2: Out-of-band notifications (email? pushover?), listen on multiple IPs (load balance for multi tenants).
* v3: Built-in client (web? ssh?)
* v4+: focus more on web client, with drag-n-drop image uploads and whatnot.

## References

Related projects which we might use or refer to while implementing our BNC.

* BNC
  * https://github.com/xthexder/xbnc
  * https://github.com/neersighted/nbnc
* IRC Protocol
  * https://github.com/sorcix/irc
  * https://github.com/fluffle/goirc
  * https://github.com/edmund-huber/ergonomadic
* Other
  * https://github.com/lukevers/kittens IRC Bot with a swanky web UI.
  * https://www.irccloud.com/ BNC service with web-based UI.

## Notes

Basic protocol draft:

```
->  PASS bar
->  NICK foo
->  USER foo localhost remotehost :real name
<-  :remotehost NOTICE * :Connecting...
<-  :remotehost 001 foo :Welcome to neobnc
<-  :remotehost 002 foo :Your host is <servername>, running version <version>
<-  :remotehost 003 foo :This server was created <date>
<-  :remotehost 004 foo remotehost <version> <available user modes> <available channel modes>
<-  PING :remotehost
->  PONG remotehost
```

## License

MIT.
