The Richardson Maturity Model is a way to grade your [[API]] according to the constraints of [[REST]]. The Richardson Maturity Model knows 4 levels (0-3), where level 3 designates a truly RESTful API.

## Level 0: Swamp of POX

Level 0 uses its implementing protocol (normally [[HTTP]], but it doesn't have to be) like a transport protocol. That is, it tunnels requests and responses through its protocol without using the protocol to indicate application state. It will use only one entry point (URI) and one kind of method (in HTTP, this normally is the [[HTTP#POST|POST]] method). Examples of these are SOAP and XML-RPC.

## Level 1: Resources

When your API can distinguish between different resources, it might be level 1. This level uses multiple URIs, where every URI is the entry point to a specific resource. Instead of going through [http://example.org/articles](http://example.org/articles), you actually distinguish between [http://example.org/article/1](http://example.org/article/1) and [http://example.org/article/2](http://example.org/article/2). Still, this level uses only one single method like [[HTTP#POST|POST]].

## Level 2: HTTP verbs

> To be honest, I don't like this level. This is because this level suggests that in order to be truly RESTful, your API **MUST** use HTTP verbs. It doesn't. REST is completely protocol agnostic, so if you want to use a different protocol, your API can still be RESTful.

[What is the Richardson Maturity Model?](https://restcookbook.com/Miscellaneous/richardsonmaturitymodel/)

This level indicates that your API should use the protocol properties in order to deal with scalability and failures. Don't use a single [[HTTP#POST|POST]] method for all, but make use of [[HTTP#GET|GET]] when you are requesting resources, and use the [[HTTP#DELETE|DELETE]] method when you want to delete a resources. Also, use the response codes of your application protocol. Don't use [200](http://httpstatus.es/200) (OK) code when something went wrong for instance. By doing this for the HTTP application protocol, or any other application protocol you like to use, you have reached level 2.

## Level 3: [[Hypermedia]] Controls

Level 3, the highest level, uses [[HATEOAS]] to deal with discovering the possibilities of your API towards the clients

---

Related: [Richardson Maturity Model, by Martin Fowler](https://martinfowler.com/articles/richardsonMaturityModel.html)