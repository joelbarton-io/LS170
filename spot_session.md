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
  - reserved (/?:@&) or unsafe ( %'"#>?{}[]~) -> code injection security concerns


# HTTP and the Request/Response Cycle
#### - Be able to explain what HTTP requests and responses are, and identify the components of each
  - hypertext transfer protocol
  - it's all about sending text
  - client-server model/paradigm
    - generally
  - requests have methods
    - GET, POST are common
  - components of an HTTP request
    - method (Verb)
    - path
    - version
    - headers
      - destination is here in the
      - domain / IP
      - host (domain name) is now a required header
    - body
      - common to include form data
#### - Be able to describe the HTTP request/response cycle
1. Enter URL in web browser.
2. URL components are uses to create an **HTTP Request**.
    - Request headers: Request line (method, path), Host, body, query parameters.
3. Lookup IP address corresponding to host. Check DNS cache and **DNS** servers.
4. Send HTTP Request from application’s **port (socket)**. Use **multiplexing** if multiple applications are sending messages.
5. Split up HTTP Request and encapsulate in **TCP Segments**.
    - Segment headers: Source & Destination Ports, Seq #, Ack#, Flags
6. Perform **TCP Three-Way Handshake** to establish connection between client and server.
7. Perform **TLS Handshake** to exchange encryption keys and establish a secure channel. Encrypt the HTTP Request into a **TLS Record**. <---- LOTS OF QUESTIONS ****
8. Encapsulate each Segment in an **IP Packet**.
    - Packet headers: IP address of Source (local IP of device) & Destination (server)
9. Encapsulate each Packet into an **Ethernet Frame**.
    - Frame headers: **MAC address** of Source (device NIC) and Destination (router). MAC addresses previously discovered using **ARP**.
10. Transmit Frame to **Switch**, then to **Router** (specified by MAC).
11. Perform **NAT** (network address translation) to convert local device IP to router IP.
12. Transmit Frame → **Modem** → **ISP** → routers on the Internet.
13. At each router:
    - Drop Packet if TTL is zero, checksum fail, or network is congested.
    - **Decapsulate** Frame to inspect IP address in Packet.
    - Check routing table to find closest IP, or a default IP to provide greater exposure.
    - Use ARP table to convert closest or default IP to MAC address of next router.
    - **Encapsulate** Packet back into a Frame, with new Source and Destination MAC.
14. Frame hops to next router. Repeat previous step.
15. Frame arrives at the final MAC address, the server **NIC**.
16. Server decapsulates Frame → Packet → Segment.
17. Wait until all Segments arrive, and **reassemble** into HTTP Request (using Sequence #).
18. Use Segment’s port/socket info (80, 443) to send HTTP Request to Application/Service. Use **demultiplexing**.
19. Server processes HTTP Request, and creates an **HTTP Response**.
    - Response headers: Status line, status code, Content-Type, body (e.g. HTML)
20. Send HTTP Response from server’s port (socket). Use multiplexing.
    - Source and Destination IP address and port are swapped.
21. Return to client: HTTP Response → TLS Record → TCP Segment → IP Packet → Ethernet Frame
22. Client decapsulates, reassembles response from segments, and sends HTTP Response to Application.
23. Browser performs additional HTTP Requests if HTML references CSS/JS/images.
24. Browser displays web page.

Ethan's article that links to 2 videos: https://medium.com/launch-school/video-series-a-trip-across-the-internet-ec129c9175eb
https://vahid.blog/post/2020-12-15-how-the-internet-works-part-i-infrastructure/

https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods

##### HTTP response
  - components
    - status code
      - examples: 200s, 300s, 500s
      - 200 is OK
      - 300s moved resource (redirect?)
        - location header included in the response
        - redirect location
      - 400s is an issue from the client side
      - 500s is an issue from the server side
    - string to explain the code
    - optional headers
    - body



#### - Be able to explain what status codes are, and provide examples of different status code types
| status | category | meaning |
| - | - | - |
| 1xx | informational | (loading?) eventually changes to another status |
| 2xx | success | "request successful"; resource transmitted; 2xx `=` big success! |
| 3xx | redirection | requested resource has moved; indicate redirect status; automatically (?) follows the supplied url listed by the `Location` header |
| 4xx | client error | "resource not found"; client-side error w/ request |
| 5xx | server error | internal server error; a generic server-side error |


#### - Understand what is meant by 'state' in the context of the web, and be able to explain some techniques that are used to simulate state
- state : _retaining_ session info (current state of page)of other requests (from before and after)
- persistence of session information; HTTP is _stateless_
- _stateful_ web apps; the _feeling or sense_ of statefulness

- ex:
  - logging into Reddit.com (retaining my login info; still logged in!)
  - use of cookies!
  - where are username/password stored?
  - session id (in this case called `reddit_session`) located in Application/storage/cookies (for chrome)
-> https://quizlet.com/508912048/ls170-networking-foundations-flash-cards/
#### - Explain the difference between GET and POST, and know when to choose each
- **Get** -> retrieve some info (resource)
  - requests you don't mind being repeated
  - don't want to perform a _destructive_ tasks

- **Post** -> change some value on server, 'post' some form information to server
  - requests you only want to occur/happen once (username/password auth)

- use cases are clearly delineated
# Security
#### - Have an understanding of various security risks that can affect HTTP, and be able to outline measures that can be used to mitigate against these risks

- **session hijacking:**_ someone gets ahold of session id
  - spoofing as the victim
    - entity who has your session id doesn't even need to know the actual username/password
    - can avoid by using session timeouts
    - TLS services

- **packet sniffing** (data transfer is intercepted) -> encryption!

- **Cross site scripting:**
  - occurs when user input isn't sanitized
  - injected code can maliciously execute on either client or server side
  - _injection_ of html, css, js, into page content -> ebay hack (xss) -> added Location header; server processes input; redirect to new URL -> ebay.com (the server) executes injected code
  - (gets around Same Origin Policy)

  - "Origin" just means -> (scheme, hostname, port); these are the required components
    - scheme: indicates family of protocols (e.g. http)
    - host name (google.com)
    - port number id



  - CORS (Cross origin resource sharing)

https://blog.checkpoint.com/2016/02/02/ebay-platform-exposed-to-severe-vulnerability/



#### - Be aware of the different services that TLS can provide, and have a broad understanding of each of those services
-
- http is inherently secure since it's text based; follow standard syntactic structure; easy to "sniff"
  - https (secured http) -> uses TLS (which includes a bunch of security-oriented services)
    - uses cyptography (asymmetric, then -> symmetric encryption) (...)

confidentiality - encryption (asymmetric & symmetric)
authentication - each party of the message exchange is confirmed PKI (public key infrastructure)
Data integrity - version of the check

#### What is pipe-lining protocols? What are the benefits of it?

https://www2.tkn.tu-berlin.de/teaching/rn/animations/gbn_sr/