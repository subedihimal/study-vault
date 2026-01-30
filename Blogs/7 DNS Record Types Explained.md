---
tags:
  - Blogs
---
DNS stands for Domain Name System, it a distributed system made up of various servers working together to translate the domain name for example "abc.com" into its actual ip address.  The ip address is the actual address where the website services can be accessed from. DNS records are needed to ensure that these webpages can be accessed via their domain name and we don't need to remember or use the actual ip while trying to access these webpages or services.

**NS Record**
NS or Name Server Record is a type of dns record which tells you which dns providers server are authoritative for the dns you are searching for. These dns provider servers store **all DNS records** for that domain, such as A, AAAA, CNAME, MX, and TXT records. NS record generally point towards big DNS hosting providers such as godaddy,namecheap,cloudfare.

Some important DNS Record Types Explained in short:

- **A Record** -> Refers to the domain address in ipv4 format
- **AA Record** -> Refers to the domain address in ipv6 format
- CName -> Maps one domain to another domain Eg: (www.google.com is a cname for google.com)
- MX Server -> Specifies which domain server receives email for the domain
- TXT Record -> TXT record is a record that stores text information associated with the domain. Commonly used for domain ownership verification.

**Example Scenario How they all work together**
When you visit **`www.abc.com`**, the dns system first looks at the www in the **CNAME**
pointing towards **abc.com**. The DNS then looks up **`abc.com`** and finds the **A Record**
and the **AAAA Record** of the server hosting the website. This gives the actual address of where the servers of abc.com are. Now your browser is able to access the website. If you send email to @abc.com then all the traffics are routed to the **MX Record** of that particular url and the **TXT Record** is used to verify the ownership of the email through SPF?DKIM checks. All these records are stored in the DNS provider's authoritative servers, which are pointed towards by the **NS Record** ensuring everything works as intended and the end-user can browse the internet without having to deal with all the complex internal working mechanism.