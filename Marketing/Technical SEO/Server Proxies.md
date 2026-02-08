### Forward Proxy

> A forward proxy, often called a proxy, proxy server, or web proxy, is a server that sits in front of a group of client machines. 

_source: [Cloudflare](https://www.cloudflare.com/en-gb/learning/cdn/glossary/reverse-proxy/)_

#### Use cases

Some example use cases of a forward Proxy might be:
- Accessing sites which have been blacklisted on the public internet: for users to access sites which are blacklisted by normal routing methodologies. A proxy server might have an I.P which is whitelisted, and can forward the request you make to a blacklisted I.P.
  
  Would be relevant for states with global Government restrictions on browing activity, such as China
- To block access to internet content on local networks, i.e: a computer network within a school's infrastructure may route all requests to the wider internet through a forward proxy with it's own I.P blacklisting/request filtering configuration, thus ensuring that children cannot access sites with explicit content on them
- To protect their online identity: recipients/interceptors of requests from forward proxies will find it harder to track the original sender, as only the forward proxy I.P will be visible (the forward proxy will relay the request back, too)
### Reverse Proxy

> A reverse proxy is a server that sits in front of one or more web servers, intercepting requests from clients. This is different from a forward proxy, where the proxy sits in front of the clients. With a reverse proxy, when clients send requests to the origin server of a website, those requests are intercepted at the [network edge](https://www.cloudflare.com/learning/serverless/glossary/what-is-edge-computing/) by the reverse proxy server. The reverse proxy server will then send requests to and receive responses from the origin server.

_source: [Cloudflare](https://www.cloudflare.com/en-gb/learning/cdn/glossary/reverse-proxy/)_
