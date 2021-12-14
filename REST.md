# [REST](https://en.wikipedia.org/wiki/Representational_state_transfer) and RESTful
[Architectural Styles and  the Design of Network-based Software Architectures, by Roy Fielding.](https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm)

---

**Representational state transfer** (**REST**) is a [software architectural style](https://en.wikipedia.org/wiki/Software_architecture#Architectural_styles_and_patterns "Software architecture") that was created to guide the design and development of the architecture for the [World Wide Web](https://en.wikipedia.org/wiki/World_Wide_Web "World Wide Web"). REST defines a set of constraints for how the architecture of an [[Internet]]-scale distributed [hypermedia](https://en.wikipedia.org/wiki/Hypermedia "Hypermedia") system, such as the Web, should behave. The REST architectural style emphasises the [scalability](https://en.wikipedia.org/wiki/Scalability "Scalability") of interactions between components, uniform [interfaces](https://en.wikipedia.org/wiki/Interface_(computing) "Interface (computing)"), independent deployment of [components](https://en.wikipedia.org/wiki/Component-based_software_engineering "Component-based software engineering"), and the creation of a [layered architecture](https://en.wikipedia.org/wiki/Abstraction_layer "Abstraction layer") to facilitate [caching](https://en.wikipedia.org/wiki/Cache_(computing) "Cache (computing)") components to reduce user-perceived [latency](https://en.wikipedia.org/wiki/Latency_(engineering) "Latency (engineering)"), enforce [security](https://en.wikipedia.org/wiki/Computer_security "Computer security"), and encapsulate [legacy systems](https://en.wikipedia.org/wiki/Legacy_systems "Legacy systems").

## Architectural constrains

### Client-server architecture
### Statelessness
### Cacheability
### Layered System
### Code on demand (optional)
### Uniform interface
Simplifies and decouples architecture, enabling each part to evolve independently.
-   Resource identification in requests - Individual resources are identified in requests, for example using [URIs](https://en.wikipedia.org/wiki/Uniform_resource_identifier "Uniform resource identifier") in RESTful Web services. The resources themselves are conceptually separate from the representations that are returned to the client. For example, the server could send data from its database as [[HTML]] or as [[JSON]]—none of which are the server's internal representation.
-   Resource manipulation through representations - When a client holds a representation of a resource, including any [metadata](https://en.wikipedia.org/wiki/Metadata "Metadata") attached, it has enough information to modify or delete the resource's state.
-   Self-descriptive messages - Each message includes enough information to describe how to process the message. For example, which parser to invoke can be specified by a [media type](https://en.wikipedia.org/wiki/Media_type "Media type").
-   Hypermedia as the engine of application state ([[HATEOAS]]) - Having accessed an initial URI for the REST application—analogous to a human Web user accessing the [home page](https://en.wikipedia.org/wiki/Home_page "Home page") of a website—a REST client should then be able to use server-provided links dynamically to discover all the available resources it needs. As access proceeds, the server responds with text that includes [hyperlinks](https://en.wikipedia.org/wiki/Hyperlink "Hyperlink") to other resources that are currently available. There is no need for the client to be hard-coded with information regarding the structure or dynamics of the application.