# Basic-Router-Config
Simple routing configurations

***BGP*** 

A. POD 1 - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5

(1) Router Details:
* a. Name: **POD-1**
* b. Ethernet Address: **192.168.1.1/30**
* c. Interface Port: **Fa0/0 - Point-to-Point**
* d. Loopback Address: **1.1.1.1/32**
* e. Protocol: **BGP 100 - multihop 2**
* f. Static Link Address: **2.2.2.2/32 - 192.168.1.2**

B. POD 2 - C7200-ADVIPSERVICESK9-M Ver 15.2(4)S5

(1) Router Details:
* a. Name: **POD-2**
* b. Ethernet Address: **192.168.1.2/30**
* c. Interface Port: **Fa0/0 - Point-to-Point**
* d. Loopback Address: **2.2.2.2/32**
* e. Protocol: **BGP 200 - multihop 2**
* f. Static Link Address: **1.1.1.1/32 - 192.168.1.1**



