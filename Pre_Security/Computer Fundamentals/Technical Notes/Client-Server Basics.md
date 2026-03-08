# Client-Server Basics - TryHackMe

## 1. Web communication in practice
Hypertext Transfer Protocol (Secure), abbreviated as HTTP(S), is a stateless client-server protocol used for the World Wide Web. This means that each request is processed independently, without the server retaining information about previous requests.

For example, when you log into a website using your credentials, the server creates a session identifier (often stored in a cookie or token) that is sent with each subsequent request.

### HTTP(S) Commands
- GET - MOST COMMON
- POST - MOST COMMON
- PUT
- DELETE
- PATCH
- HEAD
- OPTIONS
- CONNECT
- TRACE

### GET Method
The GET method is actually pretty straightforward. We can use this method to retrieve a resource from web server.

**Information about GET requests:**

- Scheme: Tells us which protocol was used: HTTP or HTTPS.
- Host: Tells us the name of the host we request resources from.
- Filename: Indicates which file we requested from the host. In our request, this is "/", which actually translates to "index.html".
- Address: Displays the IP address where the website is hosted. In our example, we are hosting the website on the same device. That's why the address 127.0.0.1 is shown.
- Status: This field indicates whether the request was successful. In our example, we received a "200 OK" status, which means that the request was successful.