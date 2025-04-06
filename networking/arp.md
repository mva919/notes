# ARP (Address Resolution Protocol)
ARP is a protocol that maps two different kinds of protocol addresses together, a hardware
address and a logical address. The hardware address is generally the MAC address found
on devices that are used for link layer packet switching. The logical address is generally
an IPv4 address, IPv6 does not use ARP as it uses its own Neighbor Discovery Protocol.
ARP was made to be general therfore IPv4 is not required to be used as the logical address
and other protocol addresses could be used but generally are not. ARP is used for direct
delivery (communication in the same subnet).

### How It Works
ARP works in a request/reply model, where a computer will send an ARP request to figure
out the hardware address (MAC address) associated with a logical address (IP address). The
request will be sent to the broadcast address (`ff:ff:ff:ff:ff:ff`) on the network so it goes to all of the 
devices that are connect to the subnet even if they are a non-IP device. This request will
contain the senders MAC address and IP address along with the IP address they wish to get the
MAC address from (e.g. `arp who-has 10.0.0.23 tell 10.0.0.34`). When the device containing the
requested MAC address receives the ARP request it will reply with its MAC address and also 
fill in its ARP cache with the IPv4 to MAC address mapping that was in the ARP request. The
reason this is done is due to the logical reasoning that if a ARP request is being made it 
is usually followed up with a packet being sent to that address, meaning the receiving computer 
(the one that replied to the ARP request) will most likely also need to reply to the packet
that was sent to them. Therefore, to avoid making another ARP request to get the MAC address 
of the sender of the packet, we cache the MAC address from the ARP request so it can be used 
in future communication. 

### ARP Cache
The ARP cache helps reduce the traffic of ARP requests/replies by caching previous 
ARP traffic. Each device will have an ARP cache including the router. Each entry in
the ARP cache will have a TTL value which is usually 20 minutes for complete entries 
(entries with both address) and 3 minutes for imcomplete entries (entries with only one address).
A custom TTL can be injected into the cache if the device administrator wishes to do so.
Usually the 20 minutes TTL is refreshed when the entry in the ARP cache is used, so another
20 minutes must go by for the entry to expire. This actually goes against RFC1122, but most 
host implement it this way. This is an example of `soft state` which is information that is
discareded if its not refreshed by a certain time. 

### ARP Proxy
It is possible to setup a ARP Proxy that responds to ARP request on behalf of another
host. This was done historically when there were two networks that weren't compatible 
or when two hosts needed to communicate but also wanted their hardware address to be 
hidden from one another.

### Gratuitous ARP
When a machine sends an ARP request to discover its own addresses (e.g. `arp who-has 10.0.0.45 tell 10.0.0.45`). 
This is usually done when a computer is configured "up" at bootstrap time. Gratuitous ARP has two purpouses:

1. Figure out if another computer is using the same IP address as itself. Since when sending a 
gratuitous ARP request the host is not expecting a response. If it does receive a response it
means there are two devices configured with the same IP address in which case a warning will be
shown so the system administrator can act accordingly.

2. To notify everybody on the subnet of any changes to the host hardware address. This could
happen if the host was shutdown, then the network card was replaced, and it was booted
back online. This works since any host that receives the ARP request will update its 
ARP cache if it already contains an entry with the `tell` address. 

Although there are ways for gratuitous ARP to see a conflict of IP addresses, it has
no method of resolving that conflict other than showing a warning. This is where
**Address Conflict Detection (ACD)** comes into play.

### Address Conflict Detection (ACD)
ACD is ARPs way to dealing with conflicting IP addresses. It works by having two
types of messages, an ARP probe and an ARP annoucement. An ARP probe checks whether
an address that a host is interested in assuming for its own is available for use. 
It does this by sending an ARP request with the Sender Protocol Address field set 
to 0 so it doesn't contaminate any ARP caches. If it gets a reply back it means
that the IP address is in use. Once a host finds an IP address that is not being 
used it uses the ARP annoucement in order to let other hosts know that it is intending
on using that address for itself. It does thing by sending an ARP request with 
the Source and Target protocol as the intented address it wishes to use. 

While doing an ARP probe if the host receives a reply when doing so it means that address 
is already taken by another host and the sending host will need to pick another address. If the 
sending host receives a similar request it means that there is another host trying to do the same 
simultaneously, in which case it should report the conflict and try using another address. If 
no reply or similar requests is seeing then two ARP annoucements are sent to show
that the host will use that IP address.

