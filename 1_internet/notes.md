## **network**
- a group of devices connected in such a way as they can exchange data and communicate with one another

- LAN (or WLAN; wireless) group of devices connected via network bridging device like a *switch*
- a LAN needs a way to communicate to other networks; enter the *router*
  - facilitates inter-network communication

## **protocols**
- 'set of rules governing exchange & transmission of data'
- why so many protocols?
  - 1) to address diff. aspects of communication
    - *message structure* vs *flow and order*
  - 2) address same aspect in diff. way or a specific use-case
    - all concerned with *flow and order* of communication
    - TCP + UDP -> address same basic aspect of comm; in diff. ways
    - TCP + HTTP -> address diff aspect of communication

## **a layered system**
- protocol groups function within varied layers of communication systems
  - logical message structure, logical message transfer, physical message creation/interpretation, physical message transfer
- communication systems are HIGHLY COMPLEX; by layering (or modularizing), we can more precisely zoom into specific layers to understand some aspect

- many models of the above modularization; two most popular are OSI and IPS
  - both roughly map to one another; but are different in their approaches
  - both have utility, but there is no one-size-fits-all model to fit real world implementation
  - FOR MY PURPOSES, these are just mental models to grasp higher-level ideas

## **data encapsulation**
- similar to former concept of *encapsulation* in programming
- "in networking, we are *hiding data* from one layer by encapsulating it within a data unit of the layer below"
- Protocol Data Units (PDU): block of data transferred over network, @ diff layers they are called different names, sometimes referred to as a *frame* (Link/Data Link), *packet* (Internet/Network), *segment* (Transport), or *datagram* (Transport)
  - at all layers, the PDU consists of header, data payload, and (sometimes) a trailer/footer

  **header and tailer**
  - purpose: provide protocol-specific metadata about the PDU

  **data payload**
  - the data we want to transport over the network
  - the KEY to how the encapsulation is implemented
  - the ENTIRE PDU at one layer is set as the data payload for the next (below layer)
  - ![PDU](./PDU.png)
  - this approach creates separation between protocols at different layers
  - these separate layers can interact without knowing anything about the other layer's specific protocol implementation
  - lower layers provide 'service' to upper layer; some data in upper layer is encapsulated by the layer above and passes the result of this encapsulation process to the below layer

## **physical network**
- The previous concepts and models are logical abstractions that help explain network communication.  At the lowest level (e.g. the bottom) is some physical, tangible thing (wires, cables, devices) and are thus bound by physical laws (physics; electrical signal, speed of light, radio wave max distance)

- at this level, we are concerned with the transfer of *bits* (binary data)
  - "Depending on the transportation medium used, bits are converted to electrical signals, light signals, or radio waves."
- KHAN ACADEMY VIDEO: WATCH?

**characteristics of physical network**
- *[latency](https://launchschool.com/lessons/4af196b9/assignments/097d7577)*: measure of time it takes for some data to go from point A to point B; 'a measure of delay'
  - types: *propogation*, *transmission*, *processing*, *queuing*; the sum of which is the **TOTAL LATENCY** between A and B
  - also: *last-mile* and *round-trip time (RTT)*

- network hops (`traceroute`): the journey some data takes across a network; the ms values returned indicate the *RTT*


- *bandwidth*: measure of the amount of data sent in some unit of time (typically, seconds)
  - is **NOT** constant from start to finish; the bandwidth in the core network will be **MUCH** higher than the bandwidth of the LAN
  - bottlenecks are where there is a change in bandwidth from high to low

**limitations**
- understanding limitations is important to the decisions we make in our apps



## **link/data link layer**
- can be thought of as the *interface* between the physical and network layers
- most commonly used protocol: ETHERNET; *framing* and *addressing*

- **frame**: a PDU; encapsulates data from internet/network layer
  - adds logical **STRUCTURE** to the info (stream of bits)
  - consist of *preamble and SFD*, **source/destination MAC address**, *length*, *DSAP, SSAP, Control*, **data payload**, and *Frame check sequence*
  - THESE DIFF FIELDS ADD STRUCTURE TO ENCAPSULATED DATA

- **interframe gap**: brief pause between each transmission of a frame

- *"The main elements to focus on are the Data Payload field being used as an encapsulation mechanism for the layer above, and the MAC Address fields being used to direct the frame between network devices. These particular fields exist across all the different Ethernet standards."*

- **addressing** -> source/destination MAC address
  - each receiving device checks its MAC address against the Destination MAC address in the FRAME, if it doesn't match, frame is ignored by device
  - *switches*: hardware that direct a frame to a destination MAC address
  - MAC addresses are *flat* not *hierarchical*; can't be subdivided; run into issues of scalability
  - solution? -> Internet protocol (IP)


## **internet/network layer**
- primary goal of protocols in this layer: faclitate communication between hosts (e.g. computers) on different networks
- **IP** primary features: routing capability via IP addressing and encapsulation of data into packets
- Data packets (PDU within IP): comprised of data payload & a header
  - the data payload of a packet is the PDU from the above layer (transport layer)
  - header consists of various fields: version, flags, TTL, protocol, checksum, source address, destination address
- **IP addresses**
  - logical in nature (unlike MAC addresses, not tied to any specific device)
  - broadcast address and network address
  - network addresses define a range of addresses within a particular subnet
  - dividing IP addresses (sub-netting) helps to establish tiers and hierarchies

  ****************************************************************

## **routing/+ tables**
- when an IP packet is received, router checks the Destination address against the addresses in its routing table, then determines the proper route to take

## **networked applications**
- communication between devices isn't enough if we want applications to be able to communicate over a network. For these, we need the protocols of the transport layer
