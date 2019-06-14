![VTI - Tunnel to host](https://user-images.githubusercontent.com/51066040/58454957-6489ab00-8163-11e9-8244-97ba1816f5f5.png)

## VTI

**A. POD 1 - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5**

**(1) Router Details (WAN):**
* a. Name: **POD-1**
* b. Interface Port: **Fa0/0 - Point-to-Point**
* c. Ethernet Address: **192.168.1.1/30**
* d. Loopback Address: **Loopback0 - 1.1.1.1/32**

**(2) Protocol:**
* a. Protocol: **BGP100**
* b. Network: **1.1.1.0/24**
* c. Remote-AS: **200**
* d. Update-Source: **Tunnel200**
* e. Static Link Address: **1.1.1.6/32 - 192.168.1.2**

**(3) Tunnel Details:**
* a. Tunnel: **Tunnel200**
* b. Tunnel IP Address: **1.1.1.5 255.255.255.252**
* c. Source IP Address: **192.168.1.1**
* d. Destination IP Address: **172.16.0.2**
* e. Static Link Address: **172.16.0.2/32 192.168.1.2**

**B. POD 2 - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5**

**(1) Router Details (WAN):**
* a. Name: **POD-2**
* b. Interface Port: **Fa0/0 - Point-to-Point**
* c. Ethernet Address: **192.168.1.2 255.255.255.252**
* d. Loopback Address: **Loopback0 2.2.2.2/32**

**(2) Protocol:**
* a. Protocol: **BGP 200**
* b. Network: **1.1.1.0/24**
* c. Network: **2.2.2.0/24**
* d. Remote-AS: **100**
* e. Update-Source: **Tunnel100**
* f. Static Link Address: **1.1.1.5/32 192.168.1.1**

**(3) Tunnel Details:**
* a. Tunnel: **Tunnel100**
* b. Tunnel IP Address: **1.1.1.6/30**
* c. Source IP Address: **192.168.1.2**
* d. Destination IP Address: **172.16.0.1**

**(4) LAN Details:**
* a. Interface Port: **Fa1/0**
* b. Interface Address: **172.16.0.1/24**


