# urls
## what is a url?

  - "Uniform Resource Locator"

  - formatted string used to locate some resource on the web
  - provides systematic means of locating a resource (via an HTTP request)
  - subset of URI that includes the network location of some resource
  - unlike a URI, a URL *must* include some piece of data that allows us to locate the resource in question, this isn't a requirement for a URI

## what is a uri?

  - identifier for a particular resource within an information space (web)
  - any kind of uniform string that identifies a specific resource (???)

## components of a url

### scheme

  - tells us which protocol should be used to access some resource
  - `https` is a scheme
  - mandatory

### host

  - indicates where a resource is located (which server is the resource hosted on?)
  - DNS processes a domain name like `google.com` into that domain's IP address
  - mandatory

### port

  - an identifier for some specific process to which communication is to be routed
  - optional; if none given, uses the scheme's default port id number

### path

  - specifies the exact resource being requested by the client from the host server
  - mandatory; can be as simple as: `/`, this typically indicates a path/to/home

### query string

  - additional information, parameters: name-value pairs `=`
  - beginning denoted by `?` character
  - can be combined with `&`
  - NOT suited for sensitive info; have a max character limit
  - optional

## encoding

  - a technique whereby certain characters in a URL are replaced with an ASCII code
  - used to use characters which have a specialized purpose in the context of a url or are reserved characters or could cause confusion and break the url
