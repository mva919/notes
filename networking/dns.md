# DNS (Domain Name System)
The Domain Name System is a system that was created in order to map names to 
address on the Internet. Resovling this mapping between a name to an address is called
**name resolution**. Using domain names dates back to the ARPANET days where orgs
kept files that contained the domain name mapping to an Internet address. This file
was called `HOSTS` and it was a simple text file. As the Internet grew and more
hosts had to be tracked, it became challenging to update this file manually. This
is where the idea of DNS came from. 

DNS is a distributed system of name servers in a hierchical structure that acts as
databases to store various types of records regarding domains. It can be thought of
as a tree. It starts off with a root server, which has information about top level domain
(TLD) name servers. There are only 13 root servers in the world, named (A-M). Top level domains
are split into different categories, the most promeneat being country code Top Level Domains
(ccTLD) and generic Top Level Domains (gTLD). ccTLDs consists of .us, .jp, and so on while
gTLD consists of .net, .com, .io, etc. This TLDs then point to the authoritative name servers 
that contain the information about a domain. Authoritative means that the resource record (RR)
belongs to that name server since RRs can be cached by other servers. A resource record is any 
type of DNS record (like a domain name to an IPv4 address - A record). 

### Distributed Nature of DNS
The distributed nature of DNS helps with the enourmous size of the Internet. Let's say we are 
trying to reach my website `marcosva.com`, instead of having to query one name server that 
contains all the information for domain names, we first ask the root server to give us the 
address of the gTLD for `.com`. We then ask that name server for `marcosva.com` and the 
gTLD will redirect us to the authoritative name server that contains RRs for that domain.
We then query that authoritative name server to get the A record that contains the
IPv4 address for my website. This DNS query response is then cached on our local machine
and also our DNS resolver with a TTL value for future use. 

From that example we can observe how in each layer we were able to get rid of many types of domains 
by going down the hiearhcy. Each step down the hiearchy we remove millions if not billions of domains, 
narrowing down our search and making the domain query much faster. In truth DNS might be distributed but 
it is still not fault taularent, a authoritative name server might be replicated between two servers a primary
and secondary, but if the two of them go down all DNS queries for my domain and any domains 
in those servers will not get resolved.

### Zones
In DNS a zone is a set of domains t

Recursive

DNS syntax

Caching

DNS query path

UDP + transaction ID

Zones

Zone Transers


### Types of Records (the important ones)
* **A**: Domain name to IPv4 address.
* **AAAA**: Domain name to IPv6 address.
* **CNAME**: Domain name to other domain name mapping. Stands for canonical name.
* **NS**: Information about name server.
* **PTR**: Used for reverse DNS queries (get domain name from IP address).
* **MX**: Used for mail exchangers addresses. 
* **SOA**: Contains information about the zone. 

