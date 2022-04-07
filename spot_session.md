# The Internet
#### Have a broad understanding of what the internet is and how it works
- **network**: a group of devices connected in such a way as they can exchange data and communicate with one another
  - LAN (or WLAN; wireless) group of devices connected via network bridging device like a *switch*
- a LAN needs a way to communicate to other networks; enter the *router*
  - facilitates inter-network communication

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
    - measure of capacity; **not** a measure of how long it takes
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
      - stream of 1s and 0s (pdu?)
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