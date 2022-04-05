## **The Internet**
### *What is the internet and how does it work?*
  - the internet is a network of networks and the web is a service we access via the internet thru URLS.  The internet facilitates inter-network communications; the web is an information space made up of resources accessible through the use of URLS and HTTP (making GET/POST requests)
### *characteristics of the physical network, such as latency and bandwidth*
### *Have a basic understanding of how lower level protocols operate*
### *Know what an IP address is and what a port number is*
### *Have an understanding of how DNS works*
### *Understand the client-server model of web interactions, and the role of HTTP as a protocol within that model*



## **TCP & UDP**
### *Have a clear understanding of the TCP and UDP protocols, their similarities and differences*
### *broad understanding of three-way handshake and its purpose*
### *broad understanding of flow control and congestion avoidance*



## **URLs**
### *components of a URL, including query strings*
- scheme, host, port, path, query string
### *Be able to construct a valid URL*
### *Have an understanding of what URL encoding is and when it might be used*
- url encoding is when we prepend `%` to some number (a character's ascii code) to replace some character that isn't allowed in the context of a URL.



## **HTTP and the Request/Response Cycle**
### *Be able to explain what HTTP requests and responses are, and identify the components of each*
- a **request**: includes
- a **response** is composed of 1) status code, 2) headers, & 3) the message body (raw response data)
  1. three digit number signifies the status of the recieved request (was the request handled successfully?); 200 (OK), 302 (moved), 400s (not found), 500s (server side error)
  2. contain important meta-data that have subtle consequences on how some response data is returned/used/etc... This can include a redirect (ala 302), or something else
  3.
### *Be able to describe the HTTP request/response cycle*
- when you type in a url, you are making a GET request (requesting a resource at a specific address from a server). HTTP provides specific rules for the format/syntax/content of these requests/reponses; these rules are necessary as the Client and Server need to be able to understand the messages being sent and received in order to operate effectively
### *Be able to explain what status codes are, and provide examples of different status code types*
### *Understand what is meant by 'state' in the context of the web, and be able to explain some techniques that are used to simulate state*
### *Explain the difference between GET and POST, and know when to choose each*



## **Security**
### *Have an understanding of various security risks that can affect HTTP, and be able to outline measures that can be used to mitigate against these risks*
### *Be aware of the different services that TLS can provide, and have a broad understanding of each of those services*
