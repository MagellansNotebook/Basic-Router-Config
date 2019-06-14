![BGP (Point-to-Point)](https://user-images.githubusercontent.com/51066040/58770445-4eac3800-85f2-11e9-9af3-74d2c2aa9a91.png)

**A. POD 1 - C2691-ENTSERVICESK9-M, Version 12.4(13b)**

**(1) Router Details (WAN):**
* a. Name: **POD-1**
* b. Interface Port: **Fa0/0 - Point-to-Point**
* c. Ethernet Address: **192.168.1.1/30**
* d. Loopback Address: **Loopback0 1.1.1.1/32**

**(2) Protocol:**
* a. Protocol: **BGP 100 - multihop 2 - Loopback0**
* b. Static Link Address: **2.2.2.2/32 192.168.1.2**

**B. POD 2 - C2691-ENTSERVICESK9-M, Version 12.4(13b)**

**(1) Router Details (WAN):**
* a. Name: **POD-2**
* b. Interface Port: **Fa0/0 - Point-to-Point**
* c. Ethernet Address: **192.168.1.2/30**
* d. Loopback Address: **2.2.2.2/32**

**(2) Protocol:**
* a. Protocol: **BGP 200 - multihop 2 - Loopback0**
* b. Static Link Address: **1.1.1.1/32 192.168.1.1**

