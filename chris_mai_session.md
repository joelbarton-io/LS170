client authenticates server ()


http request/response

source / destination port
source / destination IP
source / destination Mac addresses


Focus on transport layer, security, and application layer protocols


http requests sends highest available version (w the version )

the web uses ASCII

session ID is a 'key' -> checks to find the value of some data (a state)


ajax (from the client) ->




packet sniffing -> content is intercepted
  -> third party intercepts a message somewhere between client and server
  -> if it's not encrypted, they can act on the intercepted info

session hijacking -> spoofing

x site scripting ->


packet

session hijacking -> session time out, new session id given

x site -> user input MUST be sanitized (e.g. remove html tags/disable js)



**need to review**

transport layer : end to end connection between processes and that data is transportable


-> same-origin policy


-> asymmetric encryption: (uni-directional) encryption and decryption use different keys

-> symmetric encryption: (bi-directional) pre-master key used to create master key ()


_steps..._
client hello (tls version + encryption algo)

server received message; must decide version and algos for key encryption

server hello (sends the above info and digital cert (issuer, public key, naked message + encrypted form (signature)))

hello done (server will send no more info, you can process now)

client uses digital cert, public key; decrypts signature and sees if it matches naked message (if they match, server is who they say they are)

client issues two keys (private key, public key), public key is used to create pre-master key

client sends public key to server


understand the basics of encryption, basic high-level authentication process, http 3 uses diff form of authentication