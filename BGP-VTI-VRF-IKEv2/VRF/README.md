![VRF - BGP Tunnel to Host](https://user-images.githubusercontent.com/51066040/58631405-c7c33b00-8325-11e9-995e-38e9bc3cddeb.png)

## VRF

**A. POD 2 - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5**

**(1) Router Details (WAN):**
* a. Name: **POD-1**
* b. Interface Port: **G0/0**
* c. Ethernet Address: **no ip address**
* d. Sub-interface: **G0/0.10**
* e. Sub-interface IP address: **192.168.1.1/30**
* f. Encapsulation: **dot1Q 10**
* g. IP VRF Forwarding: **LINK**
* h. Sub-interface: **G0/0.20**
* i. Sub-interface IP address: **192.168.1.1/30**
* j. Encapsulation: **dot1Q 20**
* k. Loopback Address: **Loopback1 1.1.1.1 255.255.255.255**
* l. Loopback Address: **Loopback0 1.1.1.1 255.255.255.255**
* m. IP VRF Forwarding: **LINK**

**(2) Protocol:**
* a. Protocol: **BGP100**
* b. Router-id: **1.1.1.1**
* c. Network: **1.1.1.0/24**
* d. Network: **1.1.1.1/32**
* e. Timers: **BGP 5 20**
* f. Remote-As: **1.1.1.6 200**
* g. Update-Source: **1.1.1.6 Tunnel100**
* h. Static Link: **1.1.1.6/32 192.168.1.2**

**(3) VRF Details:**
* a. IP VRF: **LINK**
* b. rd: **1.1.1.1:1**
* c. Static VRF: **LINK 1.1.1.6/32 192.168.1.2**
* d. Static VRF: **LINK 172.16.0.2/32 192.168.1.2**

**(4) Tunnel Details:**
* a. Tunnel: **Tunnel100**
* b. Tunnel IP Address: **1.1.1.5/30**
* c. Source IP Address: **192.168.1.1**
* d. Destination IP Address: **192.168.1.2**
* e. Tunnel: **Tunnel200**
* f. Tunnel IP Address: **1.1.1.5/30**
* g. IP VRF Forwarding: **LINK**
* h. Source IP Address: **192.168.1.1**
* i. Destination IP Address: **172.16.0.2**
* j. Tunnel VRF: **LINK**

**B. POD 2 - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5**

**(1) Router Details (WAN):**
* a. Name: **POD-2**
* b. Interface Port: **G0/0**
* c. Ethernet Address: **no ip address**
* d. Sub-interface: **G0/0.10**
* e. Sub-interface IP address: **192.168.1.2/30**
* f. Encapsulation: **dot1Q 10**
* g. IP VRF Forwarding: **LINK**
* h. Sub-interface: **G0/0.20**
* i. Sub-interface IP address: **192.168.1.2/30**
* j. Encapsulation: **dot1Q 20**
* k. Loopback Address: **Loopback1 2.2.2.2 255.255.255.255**
* l. Loopback Address: **Loopback0 2.2.2.2 255.255.255.255**
* m. IP VRF Forwarding: **LINK**

**(2) Protocol:**
* a. Protocol: **BGP200**
* b. Router-id: **2.2.2.2**
* c. Network: **1.1.1.0/24**
* d. Network: **2.2.2.0/24**
* e. Network: **2.2.2.2/32**
* f. Timers: **BGP 5 20**
* g. Remote-As: **1.1.1.5 100**
* h. Update-Source: **1.1.1.5 Tunnel200**
* i. Static Link: **1.1.1.0/24 Null0**
* j. Static Link: **1.1.1.5/32 192.168.1.1**
* k. Static Link: **2.2.2.0/24 Null0**

**(3) VRF Details:**
* a. IP VRF: **LINK**
* b. rd: **2.2.2.2:1**
* c. Static VRF: **LINK 1.1.1.5/32 192.168.1.1**

**(4) LAN Details:**
* a. Interface Port: **Fa1/0**
* b. Interface Address: **no ip address**
* c. Sub-interface: **Fa1/0.30**
* d. Sub-interface IP address: **172.16.0.1/30**
* e. Encapsulation: **dot1Q 30**
* f. IP VRF Forwarding: **LINK**
* g. Sub-interface: **Fa1/0.40**
* h. Sub-interface IP address: **172.16.0.1/30**
* i. Encapsulation: **dot1Q 40**

**(5) Tunnel Details:**
* a. Tunnel: **Tunnel100**
* b. Tunnel IP Address: **1.1.1.6/30**
* c. Source IP Address: **172.16.0.1**
* d. Destination IP Address: **192.168.1.1**
* e. IP VRF Forwarding: **LINK**
* f. Tunnel VRF: **LINK**

**C. CoreService - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5**

**(1) Router Details (WAN):**
* a. Name: **CoreService**
* b. Interface Port: **Fa0/0**
* c. Ethernet Address: **no ip address**
* d. Sub-interface: **Fa0/0.30**
* e. Sub-interface IP address: **172.16.0.2/30**
* f. Encapsulation: **dot1Q 30**
* g. IP VRF Forwarding: **LINK**

**(2) Protocol:**
* a. Static Link Address: **1.1.1.6/32 - 192.168.1.2**

**(3) VRF Details:**
* a. IP VRF: **LINK**
* b. rd: **172.16.0.2:1**
* c. Static VRF: **LINK 192.168.1.1/32 172.16.0.1**

