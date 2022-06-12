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

### Testing APIs

**Chrome Dev Tools**

- Go to network

  **Curl**
  Curl is a library and command-line tool that completes IP transfers of data using URLs. One quick way to test your API while your API server is running is to run a curl command in another terminal window.
  Syntax:

  ```
  curl -X POST http://www.example.com/tasks/
  ```

Options (common)
CURL Options
You can find more options by entering the following command in the terminal. `curl --help`
Some frequently used options are:

-X or --request COMMAND
-d or --data DATA
-F or --form CONTENT
-u or --user USER[:PASSWORD]
-H or --header LINE

`curl --version`

#### Organizing API Endpoints

When organizing API endpoints, they should be based on the resources instead of on actions. The request methods will determine what action should be taken at a given URL endpoint. Your entire API's scheme should be consistent, clear and concise.

**Principles**

- **Should be intuitive**
- **Organize by resource**
  - Use nouns in the path, not verbs
  - The method used will determine the operation taken
  - GOOD:
    `https://example.com/posts`
  - BAD:
    `https://example.com/get_posts`
- Keep a consistent scheme
  - Plural nouns for collections
  - Use parameters to specify a specific item
  - GOOD:
    `https://example.com/entrees`
    `https://example.com/entrees/5`
  - BAD:
    `https://example.com/entree`
    `https://example.com/entree_five`
- **Don’t make them too complex or lengthy**
  - No longer than collection/item/collection
  - GOOD:
    `https://example.com/entrees/5/reviews`
  - BAD:
    `https://example.com/entrees/5/customers/4/reviews`

#### Methods & Endpoints Review

The request method used will determine the operation performed for the given resource URI. Though your API documentation should explain exactly what operation is performed and data returned via the response, it should be intuitive for anyone using your API.

#### Cross-Origin Resource Sharing CORS

Allows website with different origin to share data.

- 2 main components

1. CORS is all about security and based on the Same Origin Policy.
   The same-origin policy is a concept of web security that allows scripts in Webpage 1 to access data from Webpage 2 only if they share the same domain. This means that the `No 'Access-Control-Allow-Origin' header is present on the requested resource` error will be raised in the following cases:

   Different domains
   Different subdomains `(example.com and api.example.com)`
   Different ports `(example.com and example.com:1234)`
   Different protocols `(http://example.com and https://example.com)`

This is not, however, to say that it is really an error. It is behaving exactly as it should. This policy is there to protect you and your users. For instance, attackers may embed malicious scripts in advertisements. This policy prevents those scripts from successfully making requests to your bank's website as you access the website hosting the advertisement.

If you're sending any requests beyond very simple GET or POST requests, then before your actual request is sent, the browser sends a preflight OPTIONS request to the server. If CORS is not enabled, then the browser will not respond properly and the actual request will not be sent.

#### CORS Headers

In order for the requests to be processed properly, CORS utilizes headers to specify what the server will allow:

- Access-Control-Allow-Origin
  - What client domains can access its resources. For any domain use `*`
- Access-Control-Allow-Credentials
  - Only if using cookies for authentication - in which case its value must be true
- Access-Control-Allow-Methods
  - List of HTTP request types allowed
- Access-Control-Allow-Headers
  - List of http request header values the server will allow, particularly useful if you use any custom headers

#### Flask CORS

Installation

```
python3 -m pip install flask-cors
```

Initialization
Once Flask-CORS is installed, you simply import the CORS function and call it with your app instance as a parameter. This will initialize Flask-CORS will all default options.

```
  from flask_cors import CORS

  CORS(app)
```

Resource-Specific Usage There are multiple options you can use to specify your Flask-CORS behavior. One typical one is resources, which contains a dictionary whose keys are regular expressions and values are dictionary or kwargs

```
cors = CORS(app, resources={r"/api/*": {"origins": "*"}})
```

Route-Specific Usage
If you need to enable CORS on a given route, like those non-simple requests, you can use @cross_origin() to enable it.

```
@app.route("/hello")
@cross_origin()
def get_greeting():
 return jsonify({'message':'Hello, World!'})
```

#### Flask Route Decorator

The @app.route decorator in addition to taking the route path, it also allows:

1. Variable Rules
   In our endpoint naming scheme we follow collection/item/collection. In order to handle that variable item. In order to handle that variability in Flask, you add a` <variable_name>` within the path argument of the `@app.route` decorator, which is then passed to the function as a keyword argument variable_name.
   You can also specify the type of the argument by using `<converter:variable_name>` syntax.

2. HTTP Methods
   By default, the @app.route decorator answers only get requests. In order to enable more request types, pass the method parameter to the decorate including a list of string methods.

   ```
    @app.route('path/<type:variable>', methods= ['GET', 'POST'])
    def function_name('variable'):
      if request.method == 'POST':
        something = f'do something with the passed {variable}
      return something
   ```

#### Pagination in Flask

When handling large collections of data, attempting to serialize and send all of that data to the frontend will slow down the response and rendering to the client.

A common way to handle this issue is to paginate the data you're sending, and send it in chunks instead. Similar to variables discussed above, flask can handle request arguments to get additional request conditions such as page or search terms.

1. Query Parameters
   The below examples show the format of query parameters. When writing query parameters convention dictates that:

- A question mark precedes the query parameters
  `entrees?page=1`
- Parameters are in key=value pairs with an equal sign in between the key and value
  `page=1`
  ```
  www.example.com/entrees?page=1
  ```
- Sets of parameters are separated by an ampersand
  www.example.com/entrees?page=1&allergens=peanut
  ```
  www.example.com/entrees?page=1&allergens=peanut
  ```
  1. Request Arguments
     In flask, when a request is received with query params the route in the @app.route decorator remains the same and the request object arguments contain the parameter. You access it as shown below. `request.args` is a Python dictionary so we use the `get` method to access the value and provide a default value, in this case, 1.
     ```
     @app.route('/entrees', methods=['GET'])
     def get_entrees():
     page = request.args.get('page', 1, type=int)
     ```

#### Flask Error Handling

1. Use the `@app.errorhandler` decorator which takes the error code as argument
2. Name of the function should be logical
3. In the body state:

- success
- status code
- message => explain what went wrong and give direction if applicable

4. Be consistent with object formatting response
5. Pass the error code as a second argument in the returned jsonify method
