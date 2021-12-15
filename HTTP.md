# HTTP
The **Hypertext Transfer Protocol** (**HTTP**) is an [application layer](https://en.wikipedia.org/wiki/Application_layer "Application layer") protocol in the [Internet protocol suite](https://en.wikipedia.org/wiki/Internet_protocol_suite "Internet protocol suite") model for distributed, collaborative, [hypermedia](https://en.wikipedia.org/wiki/Hypermedia "Hypermedia") information systems. HTTP is the foundation of data communication for the [World Wide Web](https://en.wikipedia.org/wiki/World_Wide_Web "World Wide Web"), where [hypertext](https://en.wikipedia.org/wiki/Hypertext "Hypertext") documents include [hyperlinks](https://en.wikipedia.org/wiki/Hyperlink "Hyperlink") to other resources that the user can easily access, for example by a [mouse](https://en.wikipedia.org/wiki/Computer_mouse "Computer mouse") click or by tapping the screen in a web browser.

### HTTP/1.0
In **HTTP/1.0** a separate [connection](https://en.wikipedia.org/wiki/Connection-oriented_communication "Connection-oriented communication") to the same server is made for every resource request.

### HTTP/1.1
In **HTTP/1.1** instead a TCP connection can be reused to make multiple resource requests (i.e. of HTML pages, frames, images, [scripts](https://en.wikipedia.org/wiki/Client-side_scripting "Client-side scripting"), [stylesheets](https://en.wikipedia.org/wiki/Cascading_Style_Sheets "Cascading Style Sheets"), etc.).

**HTTP/1.1** communications therefore experience less [latency](https://en.wikipedia.org/wiki/Latency_(engineering) "Latency (engineering)") as the establishment of TCP connections presents considerable overhead, specially under high traffic conditions.
### HTTP/2

**[HTTP/2](https://en.wikipedia.org/wiki/HTTP/2 "HTTP/2")** is a revision of previous HTTP/1.1 in order to maintain the same client-server model and the same protocol methods but with these differences in order:

-   to use a compressed binary representation of metadata (HTTP headers) instead of a textual one, so that headers require much less space;
-   to use a single TCP/IP (usually [encrypted](https://en.wikipedia.org/wiki/Encryption "Encryption")) connection per accessed server domain instead of 2..8 TCP/IP connections;
-   to use one or more bidirectional streams per TCP/IP connection in which HTTP requests and responses are broken down and transmitted in small packets to almost solve the problem of the HOLB ([head of line blocking](https://en.wikipedia.org/wiki/Head-of-line_blocking "Head-of-line blocking"); NOTE: in practice these streams are used as multiple TCP/IP sub-connections to [multiplex](https://en.wikipedia.org/wiki/Multiplexing "Multiplexing") concurrent requests/responses, thus greatly reducing the number of real TCP/IP connections on server side, from 2..8 per client to 1, and allowing many more clients to be served at once);
-   to add a push capability to allow server application to send data to clients whenever new data is available (without forcing clients to request periodically new data to server by using [polling](https://en.wikipedia.org/wiki/Polling_(computer_science) "Polling (computer science)") methods).
	
**HTTP/2** communications therefore experience much less latency and, in most cases, even more speed than HTTP/1.1 communications.

### HTTP/3

**[HTTP/3](https://en.wikipedia.org/wiki/HTTP/3 "HTTP/3")** is a revision of previous HTTP/2 in order to use [QUIC](https://en.wikipedia.org/wiki/QUIC "QUIC") + UDP transport protocols instead of TCP/IP connections also to slightly **improve** the average **speed** of communications and to **avoid** the occasional (very rare) problem of TCP/IP connection **[congestion](https://en.wikipedia.org/wiki/TCP_congestion_control "TCP congestion control")** that can temporarily block or slow down the data flow of all its streams (another form of "_head of line blocking_").