# What's the difference between TCP and HTTP?

## TCP: Transmission Control Protocol

TCP is a connection-oriented protocol, which means that it establishes a connection between two hosts before sending any data. This ensures that the data is delivered reliably, but it also makes the protocol less efficient.

## HTTP: Hyper Text Markup Language

HTTP is a stateless protocol, which means that each request and response is treated independently. This makes the protocol more efficient, but it also means that the reliability of the data is not guaranteed.

## TCP vs HTTP

| Feature             | TCP                                                        | HTTP                          |
| ------------------- | ---------------------------------------------------------- | ----------------------------- |
| Connection-oriented | Yes                                                        | No                            |
| Stateless           | No                                                         | Yes                           |
| Reliable delivery   | Yes                                                        | No                            |
| Efficiency          | Less efficient                                             | More efficient                |
| Scalability         | Less scalable                                              | More scalable                 |
| Example             | File Transfer, Streaming Media                             | Web Browsing, Email, Search   |
| Port                | No definite Port                                           | Uses port 80 , 443 for HTTPS  |
| Number of Way       | Uses Three way communication                               | HTTP uses single way protocol |
| OSI Model           | Layer 4: Transport Layer,works with IP (internet Protocol) | Layer 7: Application Layer    |

## How HTTP and TCP Work as a Pair

In the case of HTTP, before a client and server can exchange an HTTP request/response, they must establish a TCP connection first. Therefore, HTTP relies on the TCP standard in order to successfully do its job.

- TCP is typically used for applications that require reliable delivery of data, such as file transfers and streaming media.
- HTTP is typically used for applications that do not require reliable delivery of data, such as web browsing and email.

---

## Resources:

1. [By GoAnyWhere.com](https://www.goanywhere.com/blog/http-vs-tcp-whats-the-difference)
