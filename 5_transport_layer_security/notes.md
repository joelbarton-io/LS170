## transport layer security protocol (tls)

**SSN was forerunner to TLS**
- assumes TCP is being used at the transport layer*

**provides three important security services**

- *Encryption:* encoding messages
  - encryption process initiated via *the TLS handshake*
  - uses a combination of symmetric and asymmetric cryptography
  - concerned with 1) TLS version, 2) algorithms included in cipher, 3) exchange of symmetric keys enabled for use with message encryption
  - **VERY COMPLEX; adds latency (up to double round-trip) impacting performance**

- *Authentication:* identity verification
  - a partial function of the certificate is to provide means of id for the party providing said certificate

  - server sends cert (including public key)->server creates signature with server's private key->signature is transmitted with original data->client decrypts signature using server's public key->compares decrypted data to original data, if they match, then the encrypted version could only have been created by an entity in possession of private key.
  - authenticity of a certificate can be verified by a Certificate Authority
    - there are different issuers of certificates; google has it's own, etc...
    - the cert hierarchy is known as the 'chain of trust'
    - root certs are essentially the end point in a chain
  - whole system still relies on trust and humans

- *Integrity:* interference detection
  - it can be useful to think of TLS as operating between HTTP (application layer) and  TCP (transport layer)
  - MAC field; layer of security that ensures a messages hasn't been altered/tampered with in transit
    - implemented through a hashing algorithm... ********************************


- all three provided services are not all used at all times; use-case dependant


## summary

- HTTP Requests and Responses are transferred in plain text; as such they are essentially insecure.**

- We can use the Transport Layer Security (TLS) Protocol to add security to HTTP communications.**
- TLS encryption allows us to encode messages so that they can only be read by those with an authorized means of decoding the message**
- TLS encryption uses a combination of Symmetric Key Encryption and Asymmetric Key Encryption.
- Encryption of the initial key exchange is performed asymmetrically, and subsequent communications are symmetrically encrypted.**
- The TLS Handshake is the process by which a client and a server exchange encryption keys.**
- The TLS Handshake must be performed before secure data exchange can begin; it involves several round-trips of latency and therefore has an impact on performance.**
- A cipher suite is the agreed set of algorithms used by the client and server during the secure message exchange.**
- TLS authentication is a means of verifying the identity of a participant in a message exchange.**
- TLS Authentication is implemented through the use of Digital Certificates.**
- Certificates are signed by a Certificate Authority, and work on the basis of a Chain of Trust which leads to one of a small group of highly trusted Root CAs.**
- Certificates are exchanged during the TLS Handshake process.**
- TLS Integrity provides a means of checking whether a message has been altered or interfered with in transit.**
- TLS Integrity is implemented through the use of a Message Authentication Code (MAC).**