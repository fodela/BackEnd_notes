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
