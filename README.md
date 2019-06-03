# Basic-Router-Config


## BGP

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

![BGP (Point-to-Point)](https://user-images.githubusercontent.com/51066040/58770445-4eac3800-85f2-11e9-9af3-74d2c2aa9a91.png)

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

![VTI - Tunnel to host](https://user-images.githubusercontent.com/51066040/58454957-6489ab00-8163-11e9-8244-97ba1816f5f5.png)

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

![VRF - BGP Tunnel to Host](https://user-images.githubusercontent.com/51066040/58631405-c7c33b00-8325-11e9-995e-38e9bc3cddeb.png)

## IKEv2

**A. Hub - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5**

**(1) Router Details (WAN)**
* a. Name: **Hub**
* b. Interface Port: **Fa2/0**
* c. Fast-Ethernet Address: **170.16.1.5/30**
* d. Looback Address: **170.16.0.1/32**

**(2) Protocol:**
* a. Protocol: **BGP200**
* b. Network: **192.168.1.0**
* c. Neighbor: **192.168.1.9**
* d. Remote-As: **100**
* e. Update-Source: **Tunnel200**

**(3) Tunnel:**
* a. Tunnel: **Tunnel200**
* b. Tunnel IP Address: **192.168.1.8/31**
* c. Source IP Address: **170.16.0.1**
* d. Destination IP Address: **170.16.1.6**
* e. Tunnel mode IPsec: **ipv4**
* f. Tunnel Protection IPsec Profile: **IPSEC**

**(4) Crypto IKEv2 Proposal:**
* a. Name: **IKE-PROPOSAL**
* b. Encryption: **aes-cbc-256**
* c. integrity: **sha512**
* d. Group: **19**

**(5) Crypto IKEv2 Policy:**
* a. Name: **IKE-POLICY**
* b. Match address local: **170.16.0.1**
* c. Proposal: **IKE-PROPOSAL**

**(6) Crypto IKEv2 Keyring:**
* a. Name: **IKE-KEYRING**
* b. Peer: **200**
* c. Description: **TRANSEC**
* d. Address: **170.16.1.6**
* e. Pre-shared-key: **TEST123**

**(7) Crypto IKEv2 Profile:**
* a. Name: **IKE-PROFILE**
* b. Match address local: **170.16.0.1**
* c. Match identity remote address: **0.0.0.0**
* d. Authentication remote: **pre-share**
* e. Authentication local: **pre-share**
* f. Keyring local: **IKE-KEYRING**
* g. Lifetime: **3600**
* h. DPD: **10 3 periodic**

**(8) Crypto IPSEC Transfrom-set:**
* a. Name: **AES256-SHA256-TUNNEL**
* b. AES Encryption: **esp-aes 256**
* c. ESP Encryption: **esp-sha256-hmac**
* d. Mode: **tunnel**

**(9) Crypto IPsec Profile:**
* a. Name: **IPSEC**
* b. Set Transform-set: **AES256-SHA256-TUNNEL**
* c. Set PFS: **group19**
* d. Set IKEv2-profile: **IKE-PROFILE**

**B. Spoke - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5**

**(1) Router Details (WAN)**
* a. Name: **Spoke**
* b. Interface Port: **Fa2/0**
* c. Fast-Ethernet Address: **170.16.1.6/30**
* d. IP VRF Forwarding: **TEST**
* e. Looback Address: **192.168.1.1/32**

**(2) Protocol:**
* a. Protocol: **BGP100**
* b. Network: **192.168.1.0**
* c. Neighbor: **192.168.1.8**
* d. Remote-As: **200**
* e. Update-Source: **Tunnel100**
* f. Static Link: **192.168.1.0/24 NULL0**

**(3) Tunnel:**
* a. Tunnel: **Tunnel100**
* b. Tunnel IP Address: **192.168.1.9/31**
* c. Source IP Address: **170.16.1.6**
* d. Destination IP Address: **170.16.0.1**
* e. Tunnel VRF: **TEST**
* f. Tunnel mode IPsec: **ipv4**
* g. Tunnel Protection IPsec Profile: **IPSEC**

**(4) VRF Details:**
* a. IP VRF: **TEST**
* b. rd: **192.168.1.1:1**
* c. Static VRF: **TEST 170.16.0.1/32 170.16.1.5**

**(5) Crypto IKEv2 Proposal:**
* a. Name: **IKE-PROPOSAL**
* b. Encryption: **aes-cbc-256**
* c. integrity: **sha512**
* d. Group: **19**

**(6) Crypto IKEv2 Policy:**
* a. Name: **IKE-POLICY**
* b. Match FVRF: **TEST**
* c. Proposal: **IKE-PROPOSAL**

**(7) Crypto IKEv2 Keyring:**
* a. Name: **IKE-KEYRING**
* b. Peer: **200**
* c. Description: **TRANSEC**
* d. Address: **170.16.0.1**
* e. Pre-shared-key: **TEST123**

**(8) Crypto IKEv2 Profile:**
* a. Name: **IKE-PROFILE**
* b. Match FVRF: **TEST**
* c. Match identity remote address: **0.0.0.0**
* d. Authentication remote: **pre-share**
* e. Authentication local: **pre-share**
* f. Keyring local: **IKE-KEYRING**
* g. Lifetime: **3600**
* h. DPD: **10 3 periodic**

**(9) Crypto IPSEC Transfrom-set:**
* a. Name: **AES256-SHA256-TUNNEL**
* b. AES Encryption: **esp-aes 256**
* c. ESP Encryption: **esp-sha256-hmac**
* d. Mode: **tunnel**

**(10) Crypto IPsec Profile:**
* a. Name: **IPSEC**
* b. Set Transform-set: **AES256-SHA256-TUNNEL**
* c. Set PFS: **group19**
* d. Set IKEv2-profile: **IKE-PROFILE**

![ikev2_connection](https://user-images.githubusercontent.com/51066040/58810841-16dcd900-8662-11e9-9436-e36c27238d05.png)
