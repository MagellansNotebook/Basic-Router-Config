# Basic-Router-Config


## BGP

A. POD 1 - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5

(1) Router Details (WAN):
* a. Name: **POD-1**
* b. Ethernet Address: **192.168.1.1/30**
* c. Interface Port: **Fa0/0 - Point-to-Point**
* d. Loopback Address: **1.1.1.1/32**
* e. Protocol: **BGP 100 - multihop 2 - Loopback0**
* f. Static Link Address: **2.2.2.2/32 192.168.1.2**

B. POD 2 - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5

(1) Router Details (WAN):
* a. Name: **POD-2**
* b. Ethernet Address: **192.168.1.2/30**
* c. Interface Port: **Fa0/0 - Point-to-Point**
* d. Loopback Address: **2.2.2.2/32**
* e. Protocol: **BGP 200 - multihop 2 - Loopback0**
* f. Static Link Address: **1.1.1.1/32 192.168.1.1**

![BGP (Point-to-Point)](https://user-images.githubusercontent.com/51066040/58451474-f50dbe80-8156-11e9-908f-2cfb7ec36535.png)

## VTI

A. POD 1 - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5

(1) Router Details (WAN):
* a. Name: **POD-1**
* b. Ethernet Address: **192.168.1.1/30**
* c. Interface Port: **Fa0/0 - Point-to-Point**
* d. Loopback Address: **1.1.1.1/32**
* e. Protocol: **BGP100**
* f. Network: **1.1.1.0/24**
* g. Remote-AS: **200**
* h. Update-Source: **Tunnel200**
* i. Static Link Address: **1.1.1.6/32 - 192.168.1.2**

(2) Tunnel Details:
* a. Tunnel: **Tunnel200**
* b. Tunnel IP Address: **1.1.1.5 255.255.255.252**
* c. Source IP Address: **192.168.1.1**
* d. Destination Address: **172.16.0.2**
* e. Static Link Address: **172.16.0.2/32 192.168.1.2**

B. POD 2 - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5

(1) Router Details (WAN):
* a. Name: **POD-2**
* b. Ethernet Address: **192.168.1.2 255.255.255.252**
* c. Interface Port: **Fa0/0 - Point-to-Point**
* d. Loopback Address: **2.2.2.2/32**
* e. Protocol: **BGP 200**
* f. Network: **1.1.1.0/24**
* g. Network: **2.2.2.0/24**
* h. Remote-AS: **100**
* i. Update-Source: **Tunnel100**
* j. Static Link Address: **1.1.1.5/32 192.168.1.1**

(2) Tunnel Details:
* a. Tunnel: **Tunnel100**
* b. Tunnel IP Address: **1.1.1.6 255.255.255.252**
* c. Source IP Address: **192.168.1.2**
* d. Destination Address: **172.16.0.1**

(3) LAN Details:
* a. Interface Port: **Fa1/0**
* b. Interface Address: **172.16.0.1/24**

![VTI - Tunnel to host](https://user-images.githubusercontent.com/51066040/58454957-6489ab00-8163-11e9-8244-97ba1816f5f5.png)

## VRF

B. POD 2 - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5

(1) Router Details (WAN):
* a. Name: **POD-2**
* b. Ethernet Address: **192.168.1.2 255.255.255.252**
* c. Interface Port: **Fa0/0 - Point-to-Point**
* d. Loopback Address: **2.2.2.2/32**
* e. Protocol: **BGP 200**
* f. Network: **1.1.1.0/24**
* g. Network: **2.2.2.0/24**
* h. Remote-AS: **100**
* i. Update-Source: **Tunnel100**
* j. Static Link Address: **1.1.1.5/32 192.168.1.1**

C. CoreService - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5

(1) Router Details (WAN):
* a. Name: **CoreService**
* b. Ethernet Address: **no ip address**
* c. Interface Port: **Fa0/0**
* d. Sub-interface: **Fa0/0.30**
* e. IP address: **172.16.0.2/30**
* f. Encapsulation: **dot1Q 30**
* g. IP VRF Forwarding: **LINK**
* h. Static Link Address: **1.1.1.6/32 - 192.168.1.2**

(2) VRF Details:
* a. IP VRF: **LINK**
* b. rd: **172.16.0.2:1**
* c. Static VRF: **LINK 192.168.1.1/32 172.16.0.1**




