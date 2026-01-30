---
tags:
  - Blogs
---
Domain Name System (DNS) is like a phonebook for the internet. Every website has an IP address and we use DNS to find the ip address of those website with human readable names like `google.com`. This process is called a domain name resolution and it removes the necessity of users to remember the actual ip of the webpage.

**`dig`** Command : dig is a command line tool used to query dns server and see how the dns is resolved. 

`dig . NS` -> shows all the available root servers
dig com NS -> shows all Top Level Domain Servers from .com
dig google.com NS -> shows the authoritative name server for google.com

When the `dig` command is used to resolve a domain like google.com. It emulates the full DNS lookup. First dig . Ns queries the root name servers are responsible for the top-level domain (TLDs) such as .com . After that `dig com NS` asks the .com TLD servers to identify the authoritative name server for `google.com`. Then `dig google.com NS` gets the authoritative  name server that actually stores the dns of `google.com`. Finally this authoritative name server provides the DNS records like A (ipv4 address) and AAAA (ipv6 address) of the website. Using dig allows you to trace the full DNS resolution path from root to the TLD to authoritative server and finally till the domains ip address.

**Example of using `dig` command**

![[9.png]]