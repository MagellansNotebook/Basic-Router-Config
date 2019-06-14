![ikev2_connection](https://user-images.githubusercontent.com/51066040/58810841-16dcd900-8662-11e9-9436-e36c27238d05.png)

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

