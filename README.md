# notes-301-06.md
<h2>HTTP</h2>
1. The Hyper Text Transfer Protocol (HTTP) is a stateless request-response application layer protocol. <br>
2. Clients (such as web browsers) are hosts that make requests to that service. The HTTP specification defines how requests and responses should be formatted, but not what a service should represent.</br> 
3. HTTP is often associated with serving .html files but is also used to transfer images, videos, .json, .xml, binary executables, and much more.

<h2>HTTP Requests</h2>
<p> A request is formatted in text and transferred using TCP. The first line of the request contains the METHOD, URL, and HTTP VERSION. The the rest are the request HEADERS. Each header is separated by a newline character. Header contain key value pairs.</p>

<p>I really really really liked this table so I decided to keep it in and put it in table format for future reference in my Markdown. I often just go with Post, Get, Put and Delete and it's great to know there are other options out there. </p>

HTTP Method | Request Has Body | Response Has Body | Safe | Idempotent | Cacheable | Function
------------ | ------------- | ------------ | ------------- | ------------ | ------------- | ------------  
GET	| No | Yes | Yes| Yes | Yes | Retrieve a resource
HEAD | No | No | Yes | Yes | Yes | Like GET but headers only
POST | Yes | Yes | No | No | Yes | Create a resource
PUT	| Yes | Yes | No | Yes | No	| Update a resource
DELETE | No | Yes | No | Yes | No | Delete a resource
CONNECT | Yes |	Yes | No | No | No | Create TCP/IP tunnel
OPTIONS	| Optional | Yes | Yes | Yes | No | Returns supported methods for a URL
TRACE | No | Yes | Yes | Yes | No | Echos retrieved request
PATCH | Yes | Yes | No | No | No | Partial modification of resource

<b>(in reference to table above) Safe methods should only be used for information retrieval and should not change the server state. Idempotent methods means if two identical requests are made they should get an identical response. Cacheable means the client should be able to cache the response.</b>

Example HTTP Request<br>
<code>POST /api/note HTTP/1.1 - <i>A post request for api with note being the resource.</i><br>
Host: api.example.com - <i>this is the API website</i><br>
Origin: www.example.com- <i>this is the website</i><br>
Authorization: Bearer - <i>this is where the token goes</i><br> bHVsIHRoaXMgaXMgYSBmYWtlIHNlY3JldCB0b2tlbg== - <i>a token<br></i>
Accept: application/json - <i>needed to make the request talk to the API</i><br>
Content-Type: application/json; charset=UTF-8<br>
Content-Length: 58<br>

{"title":"kata","content":"get 100 points on hacker rank"} -<i>this is the "payload" or what is actually being sent, this case 'a note'</i> </code><br>
<h4>HTTP Response</h4>
1. A HTTP/1.1 response is which the first line of the response contains the HTTP VERSION, STATUS CODE, and STATUS MESSAGE. <br>
2. The following lines are the request headers and are formatted exactly the same way as the request headers. 

Example HTTP Response
HTTP/1.1 200 OK (could use 404 not found, 502 bad gateway, etc)

### REST
* REST is acronym for REpresentational State Transfer. 
* In layman’s terms, is a means by which we can reference, manipulate, and transfer state. 
* <b>Rest uses a common set of methods (called “verbs”) to operate on the state of a resource (“noun”), generally using HTTP as the transfer protocol.</b>


#### REST Documentation (Swagger)
The standard for documenting REST APIs is with a “live” documentation system: Open API (formerly “Swagger”)

Once generated, Swagger Docs present developers a way not only see how to use an API, but to actually use it. Yes, this is documentation that allows for live requests from with it.

##### Directions for Swagger.io 
* Visit and review the docs and overview at Swagger.io
* Sign in to the Swagger Inspector
* Visit your API, using all applicable REST endpoints and data
* Note that on the right side, it’ll keep your history
* Once you’ve gone through all of your routes, use the radio buttons select the routes you want to document
* Click the “Create API Definition” button
* Follow the instructions to import your new API documentation to Swagger Hub
* You can leave it running there, or download the definition as .yml or .json and use it in your own project

Additional Resources: 
Videos<br>
http and rest - watched<br>
Bookmark / Skim-bookmarked all and read the first three<br>
* http basics
*  what is ReST
* swagger documentation
* swagger editor
* http reference
* rest reference