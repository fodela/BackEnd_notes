# APIs

An API is an interface. It's something that has been created to help two different systems interact with one another.

#### Benefits

1. It doesn't expose the implementation to those who shouldn't have access to it
2. The API provides a standard way of accessing the application
3. It makes it much easier to understand how to access the application's data

Frequently used APIs are

- [Google Maps API](https://developers.google.com/maps/documentation/) allows users to access a large amount of data related to maps, routes, and places around the world.
- [Stripe API](https://stripe.com/docs/api?utm_source=zapier.com&utm_medium=referral&utm_campaign=zapier&utm_source=zapier.com&utm_medium=referral&utm_campaign=zapier) allows users to accept payments, send payouts, and manage businesses online.

* [Facebook API](https://developers.facebook.com/docs) allows developers to integrate directly with the Facebook platform.

- [Instagram Basic Display API](https://developers.facebook.com/docs/instagram-basic-display-api) allows users of your app to get basic profile information, photos, and videos in their Instagram accounts.
- [Spotify API](https://developer.spotify.com/documentation/web-api/) allows users to access a large amount of data related to music artists, albums, and tracks, directly from the Spotify Data Catalogue.

#### Client-Server Communication

1. Client sends a request to the API server
2. The API server parses that request
3. Assuming the request is formatted correctly, the server queries the database for the information or performs the action in the request
4. The server formats the response and sends it back to the client
5. The client renders the response according to its implementation

#### Internet Protocols (IPs)

**IP made simpler**

- Say we want to send an email to someone.
- Our language (english) must be translated into computer language (binary -> 1010001).
- This translation is handle in the computer by the separate modules in the communication protocols (rule of conducts)
- Because this protocols usually communicate with 2 or more modules, they are best described as layers in a stack of protocols.
- There are 5 layers namely:

The messages we send are through this layers and broken down into small chunks of data called packets

1. Application layer => Creates our message. An example of protocol here is HTTP (hypertext transfer protocol )
2. Transport layer => Uses the Transmission Control layer or TCP to encapsulate the data block from the application layer which then moves to
3. Internet layer => Where Internet protocol (IP) delivers the packets. This packets are delivered through the
4. Link layer => an Ethernet cable to the
5. Physical layer => the basic hardware of your computer network.

The computer that receives these data packets moves them through the protocol stack in a reversed order so that the message can be interpreted and understood.

Internet communications are governed on multiple levels by internet protocols.

Internet Protocol (IP) is the protocol for sending data from one computer to another across the internet. Each computer must have a unique IP address that identifies it from all other computers connected to the internet.

There are many other internet protocols including:

Transmission Control Protocol (TCP) which is used for data transmission
Hypertext Transmission Protocol (HTTP) which is used for transmitting text and hyperlinks
File Transfer Protocol (FTP) which is used to transfer files between server and client

Our API will transmit data to our client via HTTP so we will primarily focus on that protocol.

#### RESTful APIs

REST stands for Representational State Transfer, which is an architectural style introduced by Roy Fielding in 2000.

- **Uniform Interface**: Every rest architecture must have a standardized way of accessing and processing data resources. This includes unique resource identifiers (i.e., unique URLs) and self-descriptive messages in the server response that describe how to process the representation (for instance JSON vs XML) of the data resource.

- **Stateless**: Every client request is self-contained in that the server doesn't need to store any application data in order to respond to subsequent requests. It does not remember anything about the previous request. This minimizes failures.

- **Client-Server**: There must be both a client and server in the architecture

- **Cacheable & Layered System**: Caching and layering increases networking efficiency. We can store information to make them faster (stateful) using caching, cookies etc to make our application work a bit faster.

Why RESTful are stateless?
It might appear easier to design a server that isn't stateless. There is a reason why RESTful web servers are not allowed to remember anything about the previous requests that the user has sent. In short, stateless servers make your applications scalable.

### Introduction to HTTP

**Features**

- Connectionless: When a request is sent, the client opens the connection; once a response is received, the client closes the connection. The client and server only maintain a connection during the response and request. Future responses are made on a new connection.
- Stateless: There is no dependency between successive requests.
- Not Sessionless: Utilizing headers and cookies, sessions can be created to allow each HTTP request to share the same context.
- Media Independent: Any type of data can be sent over HTTP as long as both the client and server know how to handle the data format. In our case, we'll use JSON.-

**Elements:**

- Universal Resource Identifiers (URIs): An example URI is `http://www.example.com/tasks/term=homework.` It has certain components:

  - Scheme: specifies the protocol used to access the resource, HTTP or HTTPS. In our example http.
  - Host: specifies the host that holds the resources. In our example www.example.com.
  - Path: specifies the specific resource being requested. In our example, /tasks.
  - Query: an optional component, the query string provides information the resource can use for some purpose such as a search parameter. In our example, /term=homework.

- Messages: Requests and Responses

-Status Codes (e.g 404 NOT FOUND): gives us feedback on the request or response. Thus was it successful or was there an error.

#### URI vs URL

You may be unsure what the difference is between a URI (Universal Resource Identifier) and a URL (Universal Resource Locator). These terms tend to get confused a lot, and are even frequently used interchangeably—but there is a distinction.

The term URI can refer to any identifier for a resource—for example, it could be either the name of a resource or the address of a resource (since both the name and address are identifiers of that resource). In contrast, URL only refers to the location of a resource—in other words, it only ever refers to an address.

So, "URI" could refer to a name or an address, while "URL" only refers to an address. Thus, URLs are a specific type of URI that is used to locate a resource on the internet when a client makes a request to a server.

#### HTTP Request Elements

HTTP requests are sent from the client to the server to initiate some operation. In addition to the URL, HTTP requests have other elements to specify the requested resource.
Elements:

- Method: Defines the operation to be performed
- Path: The URL of the resource to be fetched, excluding the scheme and host
- HTTP Version
- Headers: optional information, such as Accept-Language
- Body: optional information, usually for methods such as POST and PATCH, which contain the resource being sent to the server

#### HTTP Request Methods

Different request methods indicate different operations to be performed. It's essential to attend to this to correctly format your requests and properly structure an API.

- GET: ONLY retrieves information for the requested resource of the given URI
- POST: Send data to the server to create a new resource.
- PUT: Replaces all of the representation of the target resource with the request data. e.g if you only changed your name in your profile without adding a picture, PUT will delete (replace it with nothing) your picture and change your name to the newly specified one.
- PATCH: Partially modifies the representation of the target resource with the request data. e.g It will update your name in the profile without erasing your profile picture. Best for updating the database.
- DELETE: Removes all of the representation of the resource specified by the URI. Alert the user on the front end before executing delete.
- OPTIONS: Sends the communication options for the requested resource

### HTTP Responses

#### Elements:

- Status Code & Status Message
- HTTP Version
- Headers: similar to the request headers, provides information about the response and resource representation. Some common headers include:
  - Date
  - Content-Type: the media type of the body of the request
- Body: optional data containing the requested resource

**Codes fall into five categories**:
1xx Informational
2xx Success
3xx Redirection
4xx Client Error
5xx Server Error

**Common Codes**: --> Request type
100: Continue --> OPTIONS
200: OK --> GET
201: Created --> POST
304: Not Modified --> UNSUCCESSFUL PUT OR PATCH
400: Bad Request --> CLIENT ERROR OR BAD REQUEST FORMATION
401: Unauthorized --> YOU DO NOT HAVE ACCESS
404: Not Found --> REQUEST DOES NOT EXIST IN THE BACKEND
405: Method Not Allowed --> REQUEST METHOD USED IS NOT SUPPORTED (e.g using GET on a form that requires data be presented via POST, or PUT)
500: Internal Server Error --> SOMETHING HAPPEN IN THE SERVER THAT WE COULD NOT PROCESS THE VALID REQUEST FROM THE SERVER
