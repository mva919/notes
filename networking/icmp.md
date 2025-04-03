# ICMP (Internet Control Message Protocol)
ICMP is a network layer protocol (technaiclly is neither network nor transport and it sits between the two but Berghel said otherwise)
that is used to configure the IP stack. It utilizes IP (it is embedded in the IP protocol, resides in the IP packet payload) and it is crucial to the operation of the TCP/IP stack. ICMP works by 
giving informational messages based on types and codes. There are differnt types of messages, which contains codes to further give information
about the specific message type. ICMP message types can be broken down into informational messages and error messages.

**Attributes of ICMP:**
* ICMP does not have port numbers like in TCP/UDP instead it will either have the offending packet (packet that caused an issue or packet that requested information)
in its dat field (given that it does not exceed the MTU of the IP packet) or it will utilize sequece numbers and PID to determine which process made the request.
* ICMP does not establish a connection before sending traffic, therfore, it is not a reliable protocol and messages can be dropped or lost.
* ICMP will never reply to an ICMP error message (it could cause infinite recursive messages).
* ICMP does not expect a response to be sent when it send a request/message.
* ICMP does not differentiate between client and server.

Routers and host depend on ICMP to route traffic in an efficient and reliable way. Source quench (slow down traffic to destination) used to be used but is not 
deprecated with the use of TCP congestion controls and other technologies. 

#### Programs That Use ICMP
Famous programs are built using ICMP like `ping` to determine if a host is reachable and `traceroute` to find out the 
route take to get to a given host. Both of these of features of ICMP in order to function. `ping` uses the Echo Request/Reply
message types of ICMP to check for a reachable host. `traceroute` uses the TTL value of the IP header and uses the Time Exceeded
message from ICMP to get infomation of the sender of said message. It is able to map the route taken to a specific host by 
incrementing the TLL value by first starting at 1.

#### Malicious Use of ICMP
##### DOS 
There are various ways that ICMP can be used for a DOS attack. One way is to send a Echo request to a broadcast address and spoof
the source address to be that of the victims. When we do this the victim will receive Echo replies from all of the computers on that 
address and if done fast enough it can cause the victim to exhaust all of its resources trying to process of all the Echo reply messages. This 
attack is called a **smurf** attack. 

Another way to create a DOS attack is to utilize the Redirect Message of ICMP. The Redirect message tells a host what route is more 
efficient to take when sending traffic to a given address. One way of exploiting this is to set the route address to the victim's own
address, effectively making the victim send itself packets. If the attacker also continues to flood the victim with these Redirect messages
the victim will exhaust its resources by both updating its routing entries and sending packets to itself and processing them. 

ICMP is also used in DDOS attacks (Tribe Flooding Attacks) by allowing the synchronazation of the botnet utilizing ICMP.

##### Network Mapping
Attackers can map a network using Echo Requests to see what address are assigned and what hosts are online. By scanning the entire network
using this an attacker can get a mapping and structure of said network, only downside is that this type of scan is very noisy and can be detected
rather easily. Another way of scanning is to send the Echo Request to the broadcast address this way it makes a lot less noise (only sending one
request per subnet) and we get all of the hosts on that network to Echo reply to us. The downside of this is that a proper network will most likely
have Echo request from an outside address to the broadcast address disabled and the packet will get dropped. Lastly, an attacker can check the range 
of an address by sending Echo requests to common subnet addresses (192.169.0.64, usally the address increment by 64). This allows the attacker to 
get a rough idea of the network without all of the noise made by a full scan. 

It can also see what ports are open on a specific host by checking what kind of Host Unreachable code they receive. A 
port unreachable message lets the attacker know that the port is closed.

Using the Address Mask request message we can get information of the address range.

##### Covert Channeling
Data can be sent convertly by injecting data in the payload of the ICMP message. 

How to tell when data is being sent out covertly:
* Echo reply packets are consistely bigger than the Echo requests (sending extra dat out).
* Consistely a larger amount of Echo reply packets than Echo requests (need more reply packets to send out data).

##### Misc
With the Timestamp requests an attacker might be able to break cryptography algorithms if those algorithms are using
pseudo-random algorithms that utlize the computers system time in order to generate encrypted values. 


