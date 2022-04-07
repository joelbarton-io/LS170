# internet layers ![internet](./internet_layers.jpg)

## what is the internet?  how does it work?

  - **the internet is a network of networks**

  - **A network exists when multiple devices are connected and able of exchanging data**

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

## characteristics of physical network

- concerned with transmitting signals (in the form of _bits_); over coaxial or fiberoptic cables, or a wireless medium

- *[latency](https://launchschool.com/lessons/4af196b9/assignments/097d7577)*: measure of time it takes for some data to go from point A to point B; 'a measure of delay'
  - types: *propogation*, *transmission*, *processing*, *queuing*; the sum of which is the **TOTAL LATENCY** between A and B

  - important terms: *last-mile* and *round-trip time (RTT)*

- *bandwidth*: measure of the amount of data sent in some unit of time (typically, seconds)
  - measure of network capacity

  - is **NOT** constant from start to finish; the bandwidth in the core network will be **MUCH** higher than the bandwidth of the LAN
  - bottlenecks are where there is a change in bandwidth from high to low

  - taken together, latency & bandwidth are a measure of the performance of a physical (?) network

## how do lower level protocols operate?

- _network / internet_
  - internet protocol (IP)
    - LAN to LAN communication
  - PDU - IP packet
  - IP addresses - IPv4, IPv6
    - protocol different for v4 vs v6?
    - we're running out of addresses! need more with v6
    - changable based on your connection
    - assigned by something (_? don't need to know ?_)
    - IP address range
    - first IP Address in the range is the network address
    - hierarchical
      - saves us from one single, massive lookup table
      - ranges are managed separately
      - lookup tables/routing tables can scale
    - 4 numbers separated by periods, 0-255

- _datalink / link_
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

- _physical_
  - bits and bytes 1, 0
  - electrical, light (fiber optic), radio waves (cell and wifi)
  - stream of 1s and 0s (pdu?)


## what is an IP address?  what is a port number?

- Port number
  - identifies a process (also: "service") on a device
  - ranges 1-6xxxxx

  - used in conjunction with IP address to enable networked applications to communication
  - i.e. netflix assigned a port number (occupies the port number)
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


## how does DNS work?




## client-server model of web interaction; role of HTTP within that model






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
