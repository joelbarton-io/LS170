# internet layers ![internet](./internet_layers.jpg)

## what is the internet?  how does it work?

  - **the internet is a network of networks**
    - "job" of the internet is to connect these networks to enable the exchange of data

  - **A network exists when multiple devices are connected and able of exchanging data**

  - 2 pieces to "the internet":
    - physical infrastructure (wires, routers, switches, etc...)
    - protocols - sets of rules than enable inter-netowrk communication and govern it

  - _2 devices connected over a LAN = a network_
    - WLAN wireless LAN

  - switches allow us to communicate with multiple devices on the same LAN
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

### _network / internet layer_
  - Goal of internet protocol: end-to-end delivery
  - PDU: IP _packet_

  - IP addresses - IPv4, IPv6
    - devices on a network are _dynamically configured_ (assigned) an IP address
    - IP addresses are hierarchical
    - assigned by something (_? don't need to know ?_)
    - network addresses define a range of addresses within a particular subnet
    - first IP Address in the range is the network address

### _datalink / link layer_
  - Goal: hop-to-hop delivery (router to router)

  - adds logical **STRUCTURE** to binary data (stream of bits)
  - ethernet protocol
    - devices in a LAN, not outside that LAN
    - physical point-to-point connect between hosts on a local network

  - **PDU** - ethernet frame ![pdu](./data_link_pdu.png)

  - **TO REMEMBER:**
    - _Source/Destination MAC addresses_ used to direct frames between networked devices
       - burned in "flat" address
      - logical (as opposed to dynamic/hierarchical for IP address)
      - stored in a table in some piece of hardware
      - tables get too large to be realistic for large networks

    - Data payload
    - a checksum for corruption


          -> (/) encapsulation <-


### _physical layer_
  - bits and bytes
  - electrical, light (fiber optic), radio waves (cell and wifi)
  - stream of 1s and 0s


## what is an IP address?  what is a port number?
- IP address
  - used to identify a host (any device which sends/receives traffic) on a network

- Port number
  - identifies a process (also: "service") on a device
  - ranges 1-6xxxxx

  - used in conjunction with IP address to enable networked applications to communicate
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
  - browser gets the host from the domain
  - DNS - domain name system
  - DNS basics - looking up server ip addresses in tables using domain name as the map
  - send http request to the ip address of the server
  - we can use the IP address directly in the url bar of the browser
    - curl IP address too (or domain name)
  - domain name is for humans to remember


## client-server model of web interaction; role of HTTP within that model

  - it is a model client <> server
  - there are other models (peer to peer, distributed systems)
  - HTTP - hypertext transfer protocol
    - text messages between applications
  - client makes requests, server only response
  - http governs data exchange in this model
