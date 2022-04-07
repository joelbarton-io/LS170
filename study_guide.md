# **The Internet**
## *What is the internet and how does it work?*
  - composed of a network of networks whose functioning is enabled by protocols

  - The internet facilitates inter-network communication; the web is a service and an information space made up of a 'web' of resources accessible through the use of URLS and HTTP (making GET/POST requests)

## *characteristics of the physical network, such as latency and bandwidth*
  - *latency*
    - is a measure of delay; the time it takes some data to get from one communication end point to another end point; there are different types of latency... the sum of which is the overall latency
      - propogation delay (A -> B; ratio between distance travelled and rate (speed))
      - transmission delay (intersection analogy)
      - processing delay (interchange/merging?)
      - queuing delay (buffer)
  - *bandwidth*
    - is the amount of data that can be sent at once; NOT the same from end-to-end
    - 'bottleneck': point where there's a change from high to low bandwidth

- combined, they measure the overall performance of the physical network
## *Have a basic understanding of how lower level protocols operate*
## *Know what an IP address is and what a port number is*
  - a logical address assigned to a device when that device joins a network
  - an IP address is NOT tied to any one device;

## *Have an understanding of how DNS works*
## *Understand the client-server model of web interactions, and the role of HTTP as a protocol within that model*



# **TCP & UDP**
## *Have a clear understanding of the TCP and UDP protocols, their similarities and differences*
## *broad understanding of three-way handshake and its purpose*
## *broad understanding of flow control and congestion avoidance*



# **URLs**
## *components of a URL, including query strings*
- scheme, host, port, path, query string
## *Be able to construct a valid URL*
## *Have an understanding of what URL encoding is and when it might be used*
- url encoding is when we prepend `%` to some number (a character's ascii code) to replace some character that isn't allowed in the context of a URL like a space character or a & character.



# **HTTP and the Request/Response Cycle**
## *Be able to explain what HTTP requests and responses are, and identify the components of each*
  - a **request** is composed of 1) http method, 2) path/to/file, and 3) Host header, 4) (optional!): parameters, other headers, message body...
    1. a verb that indicates the desired action to perform on some resource (GET some resource, POST some data to some server)
    2. the actual path to some desired resource(s), included in the URL
    3. the domain name of the server we are requesting resources from (e.g. `www.reddit.com`)


  - a **response** is composed of: 1) (required) status code, 2) (optional) headers, & 3) (optional) message body (raw response data from server)
    1. three digit number signifies the status of the recieved request (was the request handled successfully?); 200 (OK), 302 (moved), 400s (not found), 500s (some server side error)
    2. contain important meta-data that have subtle consequences on how some response data is returned/used/etc... This can include a redirect (ala 302), or something else
    3. the actual requested data (html, css, javascript, png, mp3, txt, etc...);
## *Be able to describe the HTTP request/response cycle*
  - when you type in a url, you are initiating some type of request (ie: requesting a resource at a specific address from some host server). HTTP provides specific rules (a protocol) for the format/syntax/content of these requests/reponses; these rules are necessary as the Client and Server need to be able to understand each other and the messages being sent and received in order to operate effectively
## *Be able to explain what status codes are, and provide examples of different status code types*
- check
## *Understand what is meant by 'state' in the context of the web, and be able to explain some techniques that are used to simulate state*
## *Explain the difference between GET and POST, and know when to choose each*



