## Networking week 4:

[TOC]











































































# Name Resolution

Forward Look Up: Domain Name -> IP

Reverse Lookup: IP -> Domain Name

### Why UDP is used for a recursive DNS resolution rather than TCP: 



1. Total **8 packets** need to be send in case UDP

   ![image-20210509125930280](F:\ki-jani\daily-life\Networking\DNS_Lookup_UDP.png)

2. at least **44 packets ** for TCP

   ![image-20210509130302463](F:\ki-jani\daily-life\Networking\DNS_Lookup_TCP.png)



**Now, the question is how error recovery takes place?** simply the DNS resolver requests again if it doesn't receive the response.

Yet, it's no longer the common case that all DNS lookup responses can fit in a single UDP datagram, in this case a DNS name server responds with a packet explaining that the response is too large which means stream protocol (TCP) is needed. And, then the client establishes a  TCP connection.





# Resource Record Types

1. **A Records:**

   A single IP address is configured for a single domain name but single domain name can have multiple records (multiple IPs). By this load balancing is possible.  DNS Round Robin is used to balance traffic across multiple IPs. 

2. **Quad A:** difference with A records is that Quad A responds a IPv6 IP.

3. **CName:** used to redirect traffic from one domain to another.

4. **MX record:** 

5. **SRV record**

6. **TXT record**





# Anatomy of a Domain Name

A **Domain Name** consists of 3 parts, each serving 3 specific purpose. These are separated by two dots. Last part of a Domain Name is called **TLD (Top Level Domain Name)**. There are a few common TLD like- **.com, .net, , edu ** there are also some country specific **TLD** like **.bd**(For Bangladesh), **.cn**(For China).  Currently a number of **Vanity TLD**s are available.

The middle name of a Domain Name is known as the Domain. And the first portion of the Domain Name is known as the **sub-domain**, **host**. 

Three parts together is known as **Fully Qualified Domain Name**. 





# DNS Zone



Watch these helpful videos: 

- [DNS Tree Structure](https://www.youtube.com/watch?v=mLyAos32Hjw)
- [What are DNS Zone](https://www.youtube.com/watch?v=JIwi6ii-rzI)
- 

# DHCP

Dynamic Host Configuration Protocol is an **application layer** protocol that automates the configuration process of hosts on a network.

### Dynamic Allocation

A range of IP addresses is set aside for client devices and one of these IPs is issued to these devices when they request one.



### Fixed Allocation

Requires a manually specified list of MAC address and their corresponding IPs.



### DHCP Action

Although **DHCP** is a application layer protocol it entirely helps to config the **Network Layer**.



#### DHCP Discovery

As we've stated earlier, DHCP helps to config the Network Layer, now it's interesting to know how HDCP accomplishes communication without Network Layer configuration in place.

**The process by which a client configured to use DHCP attempts to get network configuration is known as DHCP Discovery.** It has four steps-

1. **Server Discovery:** Since the machine doesn't have the an IP and it doesn't know the IP of the DHCP serve, a special broadcast message is formed. DHCP server listens on port 67 and DHCP discovery message are always sent from UDP port 68. So a message, known as DHCPDISCOVER message, is encapsulated in a UDP datagram with a destination port of 67 and source port 68. The created UDP datagram is then encapsulated inside of a IP datagram with a destination IP of 255.2555.255.255, and a source IP of 0.0.0.0. And, finally the broadcast message would get delivered to every node on the LAN. And, then the DHCP server (if any) would receive the message and examine its own configuration to check if any IP address can be sent to the client.
2. **DHCP Offer**: The DHCPOFFER message is also a broadcast. But the original client would recognize that this message was intended for itself because the message has the field that specifies the client's MAC address. The client machine would now process this DHCPOFFER to see what IP is being offered to it. Technically, a DHCP client could reject this offer. It's totally possible for multiple DHCP servers to be running on the same network, and for a DHCP client to be configured to only respond to an offer of an IP within a certain range. But this is rare
3. **DHCPREQUEST:**  More often, the DHCP client would respond to the DHCPOFFER message with a DHCPREQUEST message. This message essentially says, yes, I would like to have an IP that you offer to me. Since the IP hasn't been assigned yet, this is again sent from an IP of 0.0.0.0, and to the broadcast IP of 255.255.255.255.
4. **DHCPACK:** Finally, the DHCP server receives the DHCPREQUEST message and responds with a DHCPACK or DHCP acknowledgement message. This message is again sent to a broadcast IP of 255.255.255.255, and with a source IP corresponding to the actual IP of the DHCP server. Again, the DHCP client would recognize that this message was intended for itself by inclusion of its MAC address in one of the message fields. The networking stack on the client computer can now use the configuration information presented to it by the DHCP server to set up its own network layer configuration.



# NAT(Network Address Translation)

It's a technique and should not be confused with any defined standard because different operating system and  network hardware vendors have implemented this in different ways except what it tries to accomplish being the same - it takes one IP address and translates it into another. NAT provides additional security measures to a network. Basically, NAT is a technology that allows a gateway, usually a router or firewall, to rewrite the source IP of an outgoing IP datagram while retaining the original IP in order to rewrite it into the response.

To understand it better let me copy paste an example:

Let's say we have two networks. Network A consists of the 10.1.1.0/24 address space and network B consists of the 192.168.1.0/24 address space. Sitting between these networks is a router that has an interface on network A with an IP of 10.1.1.1 and an interface on network B of 192.168.1.1. Now, let's put two computers on these networks. Computer 1 is on network A and has an IP of 10.1.1.100. And computer 2 is on network B and has an IP of 192.168.1.100. Computer 1 wants to communicate with a web server on computer 2. So it crafts the appropriate packet at all layers and sends this to its primary gateway, the router sitting between the two networks. So far, this is a lot like many of our earlier examples, but in this instance, the router is configured to perform NAT for any outbound packets. Normally, a router will inspect the contents of an IP datagram, decrement the TTL by 1, re-calculate the checksum, and forward the rest of the data at the network layer without touching it. But with NAT, the router will also rewrite the source IP address, which in this instance, becomes the router's IP on network B or 192.168.1.1. When the datagram gets to computer 2, it'll look like it originated from the router, not from computer 1.

Now, computer 2 crafts its response and sends it back to the router. The router, knowing that this traffic is actually intended for computer 1, rewrites the destination IP field before forwarding it along. What NAT is doing in this example, is hiding the IP of computer 1 from computer 2. This is known as IP **masquerading**. IP masquerading is an important security concept. The most basic concept at play here is that no one can establish a connection to your computer if they don't know what IP address it has. By using NAT in the way we've just described, we could actually have hundreds of computers on network A, all of their IPs being translated by the router to its own. To the outside world, the entire address space of network A is protected and invisible. This is known as one-to-many NAT, and you'll see it in use on lots of LANs today.



### NAT and the Transportation Layer

NAT at the network layer is pretty easy to follow. One IP address is translated to another by a device usually a router. But at the transport layer things get a little bit more complicated and several additional techniques come into play to make sure everything works properly. With one to many NAT, we've talked about how hundreds even thousands of computers can all have their outbound traffic translated via NAT to a single IP. This is pretty easy to understand when the traffic is outbound, but a little more complicated once return traffic is involved. We now have potentially hundreds of responses all directed at the same IP and the router at this IP needs to figure out which responses go to which computer. The simplest way to do this, is through **port preservation**. 

#### Port Reservation

 A technique where the source port chosen by a client is the same port used by the router.

A router setup to NAT outbound traffic will need to keep track of what source port is. 



### Port forwarding

A technique where specific destination ports can be configured to always be delivered to specific nodes.





# Network Security

### VPN (Virtual Private Networks)

A technology that allows for the extension of a private or local network to hosts that might not be on that local network.

A common security measure is to make the resources to only accessible through physical connection i.e. only the physically connected will be able to access these resources. Yet the employees may stay outside the office, by VPN, employees can access their business's network when they are not in the office. It's a tunneling protocol. 



### Proxy Services

A server that acts on behalf of a client in order to access another service.

