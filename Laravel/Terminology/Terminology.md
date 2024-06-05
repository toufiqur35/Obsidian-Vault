#### Client Side
* The Server refers to the browser on a users device that sends a request to a server for your application code.
* It then turns the response it receives from the server info an interface the user can interact with.
#### Server Side
* The Server refers to computer in a data center that storages your application code, Receives requests from a client, does some computation, and sends back an appropriate response.

#### Request Response Routing & Controller
* Routing is the URL/URL path to send request to server.
* Controller is function /class/ code respond on request and process response.
* Controller acts as a bridge between a request and a response.

#### Middleware
* Middleware is a special types of controller executed after request but before in response.
* It is a type of filtering mechanism to ensure API Securities and more.
* Middleware acts as a bridge between a request and a response.

![[11-01.png]]
#### Uses of Middleware
* Use to implement API key, user agent restriction, CSRF, XSRF security, token based API authentic