![nat_translation](https://user-images.githubusercontent.com/51066040/64831874-f5a16680-d61a-11e9-8154-86e2898f26da.png)

**Server** is set to _no ip routing_. The interface IP address is 192.168.1.1 with an  _ip default-gateway_ of 192.168.1.254 which is the interface address of the Gateway router.

**Gateway** router is where the network translation happens. The 192.168.1.1 from the Server is translated to 192.168.12.100 and 192.168.13.100. In order to assign two different IP address on the same host address an _extendable_ command must be added at the NAT rule.

NOTE: The router version used for this lab is Cisco IOS Software, 2600 Software (C2691-ENTSERVICESK9-M), Version 12.4(13b), RELEASE SOFTWARE (fc3) via GNS.
