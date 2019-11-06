![dmvpn_topology](https://user-images.githubusercontent.com/51066040/68080330-5ac04e00-fe4d-11e9-8a0f-081319eb6974.png)

## DMVPN

Dynamic Multipoint Virtual Private Network is a secure network that enables multipoint GRE connections between sites. It eliminates additional bandwidth requirement, reduces delay and decreases the complexity of network configuration.

The topology above uses the Hub and Spoke concept. Spoke One and Two have a secure tunnel to the Hub using IKEv2. They also have a secure point-to-point connection between the two of them. The point-to-point connection is used if the primary link goes down.

All outbound traffic to the internet is routed to the Firewall LAN before it goes out to the ISP connection. However, local traffic uses default routes to reach its destination. Only the Firewall WAN is NAT'ted to connect to the outside network.

Also, all inbound traffic from the internet are directed to the Firewall WAN before it enters the internal network.






 
 

