---
tags:
  - study
---
The working mechanism of DNS. 
![[7.png]]
1. Browser checks its local cache if ip is not there
2. Request goes from browser to the Recursive DNS server
3. The recursive dns server forwards it to the root server
4. The root server provides the ip of the top level domain server.
5. The top level domain Server provides the authoritative DNS server's ip
6. The Authoritative DNS server gives the actual ip address of the website
7. The Browser uses that ip to access the website
