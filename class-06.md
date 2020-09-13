## HTTP and REST

- HTTP definition:
  
  - The Hypertext Transfer Protocol (HTTP) is a stateless application-lever protocol for distributed, collaborative, hypertext information systems. HTTP is the foundation for the world wide web.

- HTTP Requests:

  - A HTTP/1.1 request is formatted in text ant transferred using TCP (Transmission Control Protocol). The first line of the request contains the `METHOD`, `URL`, and `HTTP VERSION`. The following lines ar the request `HEADERS`. Each header is separated by a newline character. A header is a key value pair separated using a colon. headers containing more than one value separate each value using a semicolon. The header section of the request is terminated with an empty line. An optional body follows the header section.

- HTTP Response:

  - A HTTP/1.1 response is also formatted in text and transferred using TCP. The first line of the response contains the `HTTP VERSION`, `STATUS CODE`, and `STATUS MESSAGE`. The following lines are the request headers and are formatted exactly the same way as the request headers. The header section fo the response is terminated with an empty line. An optional body follows the header section.

- REST definition:

  - REST is an acronym for REpresentational State Transfet. It is a means tby which we can reference, manipulate, and transfer state. REST uses a common set of methods (called 'verbs") to operate on the state of a resource ("noun"), generally using HTTP as the transfer protocol.

- A "RESTful Endpoint" is a URI (Uniform Resource Identifier) that identifies the resource. When addressed with a proper method, you are able to effect state. In normal terms, this means "Performing CRUD operations over HTTP".

- Generally speaking, RESTful endpoints deliver data in JSON format. The best practice is to supply a header with metadata and a collection of results.

- REST Documentation (Swagger)

  - The standard for documenting REST APIs is with a "live" documentation system: Open API (formerly "Swagger").

  - Once generated, Swagger Docs present developers a way not only to see how to use an API, but to actually use it. This documentation actually allows for live requests from within it.
