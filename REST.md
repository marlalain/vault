---
aliases: RESTful, RESTful Web Services
---

# [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) and [[HATEOAS|RESTful]]
[Architectural Styles and  the Design of Network-based Software Architectures, by Roy Fielding](https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm) ^0f969c

> RESTful Web Services shows you how to use those principles without the drama, the big words, and the miles of indirection that have scared a generation of web developers into thinking that web services are so hard that you have to rely on BigCo implementations to get anything done. Every developer working with the Web needs to read this book.

[\- David Heinemeier Hansson (RESTful Web Services, O'REILLY)](https://www.amazon.com/gp/product/0596529260) ^595851

---

**Representational state transfer** (**REST**) is a [software architectural style](https://en.wikipedia.org/wiki/Software_architecture#Architectural_styles_and_patterns "Software architecture") that was created to guide the design and development of the architecture for the [World Wide Web](https://en.wikipedia.org/wiki/World_Wide_Web "World Wide Web"). REST defines a set of constraints for how the architecture of an [[Internet]]-scale distributed [[Hypermedia|hypermedia]] system, such as the Web, should behave. The REST architectural style emphasises the [scalability](https://en.wikipedia.org/wiki/Scalability "Scalability") of interactions between components, uniform [interfaces](https://en.wikipedia.org/wiki/Interface_(computing) "Interface (computing)"), independent deployment of [components](https://en.wikipedia.org/wiki/Component-based_software_engineering "Component-based software engineering"), and the creation of a [layered architecture](https://en.wikipedia.org/wiki/Abstraction_layer "Abstraction layer") to facilitate [caching](https://en.wikipedia.org/wiki/Cache_(computing) "Cache (computing)") components to reduce user-perceived [latency](https://en.wikipedia.org/wiki/Latency_(engineering) "Latency (engineering)"), enforce [security](https://en.wikipedia.org/wiki/Computer_security "Computer security"), and encapsulate [legacy systems](https://en.wikipedia.org/wiki/Legacy_systems "Legacy systems").

## Architectural constrains

### Client-server architecture

> Separation of concerns is the principle behind the client-server constraints. By separating the user interface concerns from the data storage concerns, we improve the portability of the user interface across multiple platforms and improve scalability by simplifying the server components. Perhaps most significant to the Web, however, is that the separation allows the components to evolve independently, thus supporting the Internet-scale requirement of multiple organizational domains.

\- [Fielding Dissertation Chapter 5.1.2: Client-Server](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)

![[Pasted image 20211215112607.png]]

### Statelessness

> [...] each request from client to server must contain all of the information necessary to understand the request, and cannot take advantage of any stored context on the server. Session state is therefore kept entirely on the client.

\- [Fielding Dissertation Chapter 5.1.2: Client-Server](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)

![[Pasted image 20211215112817.png]]

### Cacheability

> Cache constraints require that the data within a response to a request be implicitly or explicitly labeled as cacheable or non-cacheable. If a response is cacheable, then a client cache is given the right to reuse that response data for later, equivalent requests.

![[Pasted image 20211215113031.png]]

### Layered System
### Code on demand (optional)
### Uniform interface
Simplifies and decouples architecture, enabling each part to evolve independently.
-   Resource identification in requests - Individual resources are identified in requests, for example using [URIs](https://en.wikipedia.org/wiki/Uniform_resource_identifier "Uniform resource identifier") in RESTful Web services. The resources themselves are conceptually separate from the representations that are returned to the client. For example, the server could send data from its database as [[HTML]] or as [[JSON]]—none of which are the server's internal representation.
-   Resource manipulation through representations - When a client holds a representation of a resource, including any [metadata](https://en.wikipedia.org/wiki/Metadata "Metadata") attached, it has enough information to modify or delete the resource's state.
-   Self-descriptive messages - Each message includes enough information to describe how to process the message. For example, which parser to invoke can be specified by a [media type](https://en.wikipedia.org/wiki/Media_type "Media type").
-   Hypermedia as the engine of application state ([[HATEOAS]]) - Having accessed an initial URI for the REST application—analogous to a human Web user accessing the [home page](https://en.wikipedia.org/wiki/Home_page "Home page") of a website—a REST client should then be able to use server-provided links dynamically to discover all the available resources it needs. As access proceeds, the server responds with text that includes [hyperlinks](https://en.wikipedia.org/wiki/Hyperlink "Hyperlink") to other resources that are currently available. There is no need for the client to be hard-coded with information regarding the structure or dynamics of the application.

---

Related: [[HTTP]], [[HATEOAS]], [[HAL]], [REST Cookbook](https://restcookbook.com/), [[Richardson Maturity Model]], [[Client Server Communication]]