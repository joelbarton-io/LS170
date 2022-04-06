## **to focus on**

**role of http**

**break down http/urls into composite elements; understand purposes**


## **application layer/protocols**
- application layer does *NOT* include the application itself; rather a set pf protocols that provide communication services to applications
- application layer protocols focus on the structure of messages and what data is contained in the message
- focused on the rules of *how* applications talk to each other (the syntax of that communication)

## **http and the web**
- primary protocol used for communication on the Web
- 'web' and 'internet' are distinct; internet: network of networks that enable communication between networks; web: service accessed by internet
- HTTP is the primary means by which applications interact with resources on the web
- resources needed uniformity, earliest incarnation of the web was faciliated mainly through html, ur(i/l), and http
- http is a set of rules (protocol) which provide uniformity to the way resources on the web are transferred between applications


- ** NEED TO GO BACK AND DO NOTES FOR HTTP BOOK **


## **background and diagrams**
- understanding where you are when looking at a piece of code
- **a *"server's"* composition:**
  1. web server -> responds to requests for static assets (files, images, css, js...)
  2. application server -> server-side code lives, complex requests, business logic
  3. data store -> relational database; also simple files, key/value stores...

- **http, tcp/ip**
  - all three are separate protocols operating at different 'layers' of the network
  - http(s) operates at the application layer (messages between applications)
  - tcp/ip do all the heavy-lifting in the request response cycle between client and server

## **urls**
- URL is a subset of URI that includes the network location of some resource

**schemes&protocols** <- spend more time here.
- "scheme" identifies which protocol is to be used (http, https, etc...)
- "protocol" in the previous context, refers to a "family" of some protocol (e.g. HTTP, HTTP 1.0, HTTPS)
- scheme names are lowercase, protocol names are UPPERCASE

**urls and filepaths**
- most web content is generated dynamically, on the server side, then sent as the response to the client
- how the path portion of a url is used varies depending on the application/framework

## **request response cycle**
- client is usually a web browser
- server is whatever software is running on the machine (server)

1. http request initiated (typed in a url into browser)
2. request created -> method (GET/POST), path (to resource), parameters (due=today)
3. server receives http request from client
4. common (verify session, load tasks from database, render html)
5. server serves response
6. response (status: 200) (headers) (body)
7. client looks at content type header, acts accordingly
8. displays webpage to user



## **summary**

- **The Domain Name System (DNS) is a distributed database which translates a domain name such as google.com to an IP Address such as 216.58.213.14.**

- **A URI is an identifier for a particular resource within an information space.**
- **A URL is a subset of URI, but the two terms are often used interchangeably.**
- **URL components include the scheme, host (or hostname), port, path, and query string.**
- **Query strings are used to pass additional data to the server during an HTTP Request. They take the form of name/value pairs separated by an = sign. Multiple name/value pairs are separated by an & sign. The start of the query string is indicated by a ?.**
- **URL encoding is a technique whereby certain characters in a URL are replaced with an ASCII code.**
- **URL encoding is used if a character has no corresponding character in the ASCII set, is unsafe because it is used for encoding other characters, or is reserved for special use within the url.**
- **A single HTTP message exchange consists of a Request and a Response. The exchange generally takes place between a Client and a Server. The client sends a Request to the server and the server sends back a Response.**
- **An HTTP Request consists of a request line, headers, and an optional body.**
- **An HTTP Response consists of a status line, optional headers, and an optional body.**
- **Status codes are part of the status line in a Response. They indicate the status of the request. There are various categories of status code.**
- **HTTP is a stateless protocol. This means that each Request/ Response cycle is independent of Request and Responses that came before or those that come after.**
- **Statefulness can be simulated through techniques which use session IDs, cookies, and AJAX.**
- **HTTP is inherently insecure. Security can be increased by using HTTPS, enforcing Same-origin policy, and using techniques to prevent Session Hijacking and Cross-site Scripting.**

