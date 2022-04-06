# http request/response cycle
![VAHID'S DIAGRAM](./http_request_response_cycle.jpg)

## what are HTTP requests and responses?  use cases for GET and POST

- "Hyper-**_text_** transfer protocol": a HTTP r/r exchange involves the sending of text between (typically) a client and a server

-
## describe the HTTP request/response cycle





## what are status codes?  different types?

- part of the status line in an HTTP response; indicate the status of the current request

- types of errors

| status | meaning |
| - | - |
| 200 | "request successful"; resource transmitted; 2xx `=` big success! |
| 302 | requested resource has moved; indicate redirect status; automatically (?) follows the supplied url listed by the `Location` header |
| 404 | "resource not found"; client-side error w/ request |
| 500 | internal server error; a generic server-side error |

## what is meant by 'state' in the context of the web?  how does HTTP simulate state?

- a "stateful" application is one which retains client data from the activities of a past session

- _"HTTP is a stateless protocol; each cycle is independent of the one before and the one that came after"_
  - stateless protocols like `http` are _resilient_, _fast_, and _flexible_
  - `http` doesn't retain client data between individual response/request cycles so there's

- this information might pertain to the state of some aspect of the page (like the contents of their shopping cart) or the user's status of being "logged-in" to their account for the application

  - when the user adds an item to their cart they issue a new HTTP request

  - for this fictional application to do something useful, it needs to somehow retain it's current state post-new http request

  - while `http` is very much a _stateless protocol_; developers can _simulate_ statefulness, meaning that the application _feels like and appears_ to have a persistent connection to the resource, when in reality, it is simply the **_appearance of persistent state_**

    - achieved via session IDs, cookies, and AJAX
