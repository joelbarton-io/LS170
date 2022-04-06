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



# The Internet
#### Have a broad understanding of what the internet is and how it works
  - **A network is multiple devices connected to chase and exchange data**
  - **internet is a network of networks**
  - 2 pieces:
    - physical infrastructure
    - protocols - sets of rules than enable inter-netowrk communication and govern it
  - 2 devices connected via LAN is a network
    - WLAN wireless LAN
  - switches allow us to communicate with multiple devices on the same LAN
  - switches replaced hubs
  - routers (among other devices) connect multiple LAN together
  - The word router is pretty overused/overloaded

  - web vs internet
    - internet = infrastructure to exchange information
    - web = a "blanket" of information being passed across the internet

https://howdns.works/
#### Understand the characteristics of the physical network, such as latency and bandwidth
  - latency
    - a **measure of delay (time)**
    - end to end
    - different types of latency
      - propagation delay
        - general measurement (distance travelled/speed)
      - transmission delay
        - "intersection" of modes or types of data exchange (
      - processing delay
        - literal processing
      - queuing delay
        - buffer time to be "processed"
    - round trip travel/time
    - used to assess performance of the physical network
  - bandwidth
    - a **measure of the amount of data** can sent at a single moment
    - not a measure of how long it takes
    - measure of capacity
    - bandwidth varies based on where data is in the process of transfer
    - bottlenecks
  - taken together, they are a measure of performance of a physical (?) network
#### - Have a basic understanding of how lower level protocols operate

  - TCP/IP
    - application
      - HTTP (SMTP, FTP)
      -
    - (security)
      - TLS
    - transport
      - UDP - user datagram protocol
        - PDU - datagram
      - TCP - transmission control protocol
        - PDU - segment
    - network / internet
      - internet protocol (IP)
        - LAN to LAN communication
      - PDU - IP packet
      - IP addresses - IPv4, IPv6
        - protocol different for v4 vs v6?
        - we're running out of addresses! need more with v6
        - changable based on your connection
        - assigned by something
        - IP address range
        - first IP Address in the range is the network address
        - hierarchical
          - saves us from one single, massive lookup table
          - ranges are managed separately
          - lookup tables/routing tables can scale
        - 4 numbers separated by periods, 0-255
    - datalink / link
      - ethernet protocol
        - devices in a LAN, not outside that LAN
        - physical point-to-point connect between hosts on a local network
      - PDU - ethernet frame
        - includes a checksum for corruption
      - MAC addresses
        - burned in "physical" "flat" address
        - logical (vs dynamic/hierarchical for IP)
        - can change but doesn't usually
        - stored in a table in some piece of hardware
        - tables get too large to be realistic for large networks
    - physical
      - bits and bytes 1, 0
      - electrical, light (fiber optic), radio waves (cell and wifi)
      - stream (no pdu?)
  - OSI

#### - Know what an IP address is and what a port number is
  - Port number
    - ranges
    - identifies a process (also: "service") on a device
    - used in conjunction with IP address to enable networked applications to communication
    - i.e. netflox assigned a port number (occupies the port number)
    - 65535 max
    - wellknown ports
    - registered ports - private entities
    - ephemeral ports - usable on demand, dynamically assigned
  - socket
    - IP address + port number = socket
    - conceptual socket vs socket object
      - conceptual - socket is an endpoint
  - demultiplexing and multiplexing
    - happens at transport layer (TCP UDP)
    - multiplexing - transmitting multiple signals over one communication channel
    - demultiplexing - receving multiple signals and parsing them, received over one line
    - antimultiplexing!?
  - connection vs connectionless systems
    - connectionless - 1 concierge that takes messages
    - connection oriented - concierge creates a new socket object to deal with messages
#### - Have an understanding of how DNS works
  - browser gets the host from the domain
  - DNS - domain name system
  - DNS basics - looking up server ip addresses in tables using domain name as the map
  - send http request to the ip address of the server
  - we can use the IP address directly in the url bar of the browser
    - curl IP address too (or domain name)
  - domain name is for humans to remember

#### - Understand the client-server model of web interactions, and the role of HTTP as a protocol within that model
  - it is a model client <> server
  - there are other models (peer to peer, distributed systems)
  - HTTP - hypertext transfer protocol
    - text messages between applications
  - client makes requests, server only response
  - http governs data exchange in this model

# TCP & UDP
#### - Have a clear understanding of the TCP and UDP protocols, their similarities and differences
  - TCP - email
    - reliability
    - Additional services
      - flow control (buffer)
        - don't send as much if the buffer is full
      - congestion avoidance
      - retransmission
      - all these services add additional overhead and latency
  - UDP - Video chat
    - simplicity grants speed and flexibility
      - sacrifices reliabiltiy for speed and accessability
    - Does not provide so many additional services
      - ability to be extended


#### - Have a broad understanding of the three-way handshake and its purpose
  - purpose: establish dedicated channel (socket object)
  - head of line blocking
    - result of TCP three-way handshake
    - synchronization
    - retransmit causes waiting in the queue for sending messages
  -
  - this established the reliable connection
    - **SYN**chronize: _sender asks receiver "ready to receive?"_ -> **SYN**
    - **ACK**nowledge: _receiver says, "message received"_ -> **SYN ACK**
    - **ACK**nowledge: _sender says, "message received"_   -> **ACK**

- UDP is essentially one way traffic and doesn't care about the reliability of the connection

https://www.youtube.com/watch?v=IP-rGJKSZ3s
#### - Have a broad understanding of flow control and congestion avoidance
  - purpose: avoids overloading something (typically server to client)
  - aren't accessible to UDP - TCP specific and must be implemented custom for UDP if desired

#### - ADDED connectionless vs connection oriented
  - TCP - connection-oriented (handshake)
    - data in the socket object is IP and port of the source, destination IP and port (four tuple)
  - UDP - connectionless (no handshake)

# URLs
- uri - uniform resource identifier
  - url - uniform resource locators
    - uri pertaining to network location of some desired resource
  - urn - uniform resource name

#### - Be able to identify the components of a URL, including query strings
https://www.example.com:88/home?item=book&author=me%20+andmary

_tls necessitates tcp, currently*_

- http -> scheme ()
- www.example.com -> host name
- 88 ->port number id
- /home -> path
- ?item=book -> search query

- :// -> "separator"

#### - Be able to construct a valid URL
#### - Have an understanding of what URL encoding is and when it might be used

# HTTP and the Request/Response Cycle
#### - Be able to explain what HTTP requests and responses are, and identify the components of each
#### - Be able to describe the HTTP request/response cycle
#### - Be able to explain what status codes are, and provide examples of different status code types
#### - Understand what is meant by 'state' in the context of the web, and be able to explain some techniques that are used to simulate state
#### - Explain the difference between GET and POST, and know when to choose each

# Security
#### - Have an understanding of various security risks that can affect HTTP, and be able to outline measures that can be used to mitigate against these risks
#### - Be aware of the different services that TLS can provide, and have a broad understanding of each of those services