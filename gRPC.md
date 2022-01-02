gRPCs (gRPC [Remote Procedure Calls](https://en.wikipedia.org/wiki/Remote_procedure_call)) use [Protocol Buffers](https://en.wikipedia.org/wiki/Protocol_Buffers "Protocol Buffers") to encode data. Contrary to [[HTTP]] [[API|APIs]] with [[JSON]], they have a more strict specification. Due to having a single specification, gRPC eliminates debate and saves developer time because gRPC is consistent across platforms and implementations

---
## [Why?](https://youtu.be/u4LWEXDP7_M)

### [The Problem with Client Libraries](https://youtu.be/u4LWEXDP7_M?t=44)

^d7232c

- Any communication protocol needs a client library for your language of choice
	- SOAP Library
	- HTTP Client Library

- Hard to maintain and patch client libraries
	- HTTP/1.1 HTTP/2, new features, security etc

## Modes

- Unary RPC (works like [[HTTP]])
- Server streaming RPC (like watching a video)
- Client streaming RPC (like uploading a huge file)
- Bidirectional streaming RPC (like chats, games, etc)

---

Related: [[Protocol Buffers]]