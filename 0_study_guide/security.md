# **Security**

## Have an understanding of various security risks that can affect HTTP, and be able to outline measures that can be used to mitigate against these risks
- **main risks:**
  1. Session Hijacking
    - occurs when a hacker impersonates a user by using the user's session id.
  2. Cross-site scripting
    - when some script (HTML/JS) is injected into a web application's server which is then interpreted by the client's browser and run
  3. packet sniffing
- **risk mitigation strategies**
  1. resetting sessions; session timeouts, HTTPS (secure HTTP)
  2. user input sanitation (eliminate script tages; disallow JS/HTML inputs); escape all user input so it isn't interpreted as code

## Services provided by TLS protocol
### 1. Encryption

  - encryption is the process of encoding a message which can only be read by those with an authorized means of decoding the message.

  - uses a combination of symmetric and asymmetric cryptography (asym for the initial key exchange; sym for the actual message transfer)

  - initiated via the  *TLS handshake*
    - concerned with 1) TLS version, 2) algorithms included in cipher, 3) exchange of symmetric keys enabled for use with message encryption
    - VERY COMPLEX; adds latency (up to double round-trip) impacting performance
### 2. Authentication
  - ID verification of some participant in a message exchange

  - a partial function of the certificate is to provide means of id for the party providing said certificate

  - PROCESS: server sends cert (including public key) -> server creates signature with server's private key -> signature is transmitted with original data -> client decrypts signature using server's public key -> compares decrypted data to original data, if they match, then the encrypted version could only have been created by an entity in possession of private key.

  - the authenticity of a certificate is verified by a Certificate Authority
    - there are different issuers of certificates; google has its own...
    - the cert hierarchy is known as the 'chain of trust'
    - certs for lower-level authorities are signed by the CA one level above them
    - root certs are essentially the end point in the chain; self signers

  - whole system still relies on trust and humans; thus fallible
### 3. Integrity
  - process to detect message tampering/interference

  - implemented through the use of a Message Authentication Code (MAC) which is a field (metadata) of the PDU of the TLS protocol and a hashing algo
  - like other protocols' PDUs, the TLS PDU is composed of a data payload and headers/footers (metadata)
