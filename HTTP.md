# HTTP

> HTTP and HTML are the Whoopee Cushion and Joy Buzzer of Internet protocols, only comprehensible as elaborate practical jokes. For anyone who has tried to accomplish anything serious on the Web, it's pretty obvious that of the various implementations of a worldwide hypertext protocol, we have the worst one possible.  
  	Except, of course, for all the others.

\- [In Praise of Evolvable Systems, Clay Shirky](https://web.archive.org/web/20010617011404/http://www.shirky.com/Articles/evolve.html)

---

The **Hypertext Transfer Protocol** (**HTTP**) is an [application layer](https://en.wikipedia.org/wiki/Application_layer "Application layer") protocol in the [Internet protocol suite](https://en.wikipedia.org/wiki/Internet_protocol_suite "Internet protocol suite") model for distributed, collaborative, [[Hypermedia|hypermedia]] information systems. HTTP is the foundation of data communication for the [World Wide Web](https://en.wikipedia.org/wiki/World_Wide_Web "World Wide Web"), where [hypertext](https://en.wikipedia.org/wiki/Hypertext "Hypertext") documents include [hyperlinks](https://en.wikipedia.org/wiki/Hyperlink "Hyperlink") to other resources that the user can easily access, clicking or tapping the screen in a web browser.

## Versions

### HTTP/0.9

![[Pasted image 20211215070156.png]]

![[Pasted image 20211215070303.png]]

\- [[REST#^595851|RESTful Web Services]]

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

## Methods

### GET

### POST

> The HTTP methods POST and PUT aren't the HTTP equivalent of the CRUD's create and update. They both serve a different purpose. It's quite possible, valid and even preferred in some occasions, to use PUT to create resources, or use POST to update resources.
> [...]
> If you do not know the actual resource location, for instance, when you add a new article, but do not have any idea where to store it, you can POST it to an URL, and let the server decide the actual URL.
	
\- [When should we use PUT and when should we use POST?](https://restcookbook.com/HTTP%20Methods/put-vs-post/)

```http
POST /articles HTTP/1.1
<article>
    <title>blue stapler</title>
    <price currency="eur">7.50</price>
</article>

HTTP/1.1 201 Created
Location: /articles/63636
```

### PUT

Use `PUT` when you can update a resource completely through a specific resource. For instance, if you know that an article resides at [http://example.org/article/1234](http://example.org/article/1234), you can `PUT` a new resource representation of this article directly through a `PUT` on this URL.

```http
PUT /article/1234 HTTP/1.1
<article>
    <title>red stapler</title>
    <price currency="eur">12.50</price>
</article>
```

### PATCH

> The HTTP methods PATCH can be used to update partial resources. For instance, when you only need to update one field of the resource, PUTting a complete resource representation might be cumbersome and utilizes more bandwidth

[When should we use the PATCH HTTP method?](https://restcookbook.com/HTTP%20Methods/patch/)

```http
PATCH /user/jthijssen HTTP/1.1
<user>
    <firstname>Joshua</firstname>
</user>
```

### DELETE

### HEAD

### OPTIONS

The way to check what methods are supported by an API.

```http
OPTIONS /my/resource HTTP/1.1
Host: example.org

HTTP/1.1 200 OK
Allow: HEAD,GET,DELETE,OPTIONS
```

Even when undefined, the method will most likely return an `Allow` header, showing the available methods.

```http
OPTIONS /a/resource HTTP/1.1
Host: example.org

HTTP/1.1 200 OK
Allow: HEAD,GET,OPTIONS
```

If resources require authentication, it is possible that OPTIONS returns more methods once you added authentication headers to the request.

```http
OPTIONS /a/resource HTTP/1.1
Host: example.org
Authentication: .....

HTTP/1.1 200 OK
Allow: HEAD,GET,PUT,POST,DELETE,OPTIONS
```

Related: [The HTTP OPTIONS method and potential for self-describing RESTful APIs](http://zacstewart.com/2012/04/14/http-options-method.html).

## Status Codes

Related: [HTTP Status Codes](https://httpstatuses.com/)

	httpstatuses.com is an easy to reference database of HTTP Status Codes with their definitions and helpful code references all in one place. Visit an individual status code via `httpstatuses.com/code` or browse the list below.
	
---

Related: [[HTTPS]], [[Internet]], [[gRPC]]