## What is the major benefit to how the data payload implements encapsulation?
- separation of the various protocols at different layers.  Protocols don't need to know the specifics of another protocol's implementation to interact with it.  A lower layer protocol only needs to know that it should provide a service (encapsulation) to the protocol above it.  Additionally, it provides a certain level of abstraction.

## What's the default port number for HTTP?
- 80; unless explicitly stated as something else.

## Ports identify specific services running on our host machine, how do they help us with multiplexing and demultiplexing?
- The source port and destination port numbers are listed in headers in the transport layer's PDU (both for UDP's datagram and TCP's segment) and thus can be used to provide end-to-end communication between the client process and the server process which the client needs to exchange data with.
- Multiplexing/demultiplexing essentially involve several streams of data
## A major part of the implementation of the Transmission Control Protocol (TCP) is finding the balance between?
- reliability and performance

## Why is it important to understand the history and evolution of the HTTP?
- provides us with insight into the workarounds used to deal with HTTP's limitations; informs our decisions

## "HTTP is a stateless protocol" - what is mean by this?
- each HTTP request/response cycle is independant. As such, separate requests have no direct bearing on the next/previous cycle.  Thus, each request needs to contain all necessary info to fulfill the request.

## what prevents data packets from existing in perpetuity and bouncing around the network forever?
- TTL (Time to Live); specifies the number of network 'hops' a packet can take before being dropped

## where is session data stored?
- on the server, somewhere. Session ID is stored on the client and used as a key to the stored session data.

## what are the three _primary_ server-side infrastructure pieces?
- web server, application server, data store (static assets)

## what are three circumstances where URL encoding might be required?
- when there is no corresponding ASCII character, when a character is unsafe (has a specific meaning in the context of a url, eg `?`, `&`), and for problematic characters like spaces (`%20` or `+`)

## what is the _same origin policy_?
- an _"origin"_ is comprised of a _scheme_, _hostname (domain)_, and _port number_
- is a cornerstone of web application security

## what is contained in a TLS certificate?
- Identify of issuer (who produced the cert?)
- Identity of subject
- Public key
- range of valid dates to be used within
- digital signature from issuer (the Authority)

# lacking...

- Asymmetric vs symmetric key encryption
- same origin policy
- TLS certificates