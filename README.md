# MPLS
Implementation of Multiprotocol Label Switching

#IMPORTANT!!!!!
#Copy the file c7200-adventerprisek9-mz.152-4.M7.image-512.ghost and past it to \mpls\project-files\dynamips


# MPLS Network Implementation with Traffic Engineering

This project demonstrates the implementation of a Multiprotocol Label Switching (MPLS) network to showcase its advantages over traditional IP routing. [cite_start]The primary goals were to highlight efficiency improvements in packet forwarding, reduce lookup times, and implement enhanced traffic engineering using GNS3. [cite: 2, 3]

## Project Overview

[cite_start]This project focuses on the practical implementation of an MPLS network to demonstrate its capabilities. [cite: 6] Key objectives included:
* [cite_start]**Faster Packet Forwarding:** Leveraging label-based switching to speed up packet forwarding compared to traditional IP lookups. [cite: 3]
* [cite_start]**Traffic Engineering:** Managing network traffic effectively through the implementation of specific policies and routing protocols. [cite: 4, 6]
* [cite_start]**Virtual Routing and Forwarding (VRF):** Isolating traffic from different customers to ensure privacy and security. [cite: 4]
* [cite_start]**Dynamic Routing:** Using OSPF for interior gateway routing and BGP for route redistribution. [cite: 4, 17]

[cite_start]The project successfully configured an MPLS network, demonstrating significant improvements in traffic management and forwarding efficiency. [cite: 20]

---

## Network Topology

[cite_start]The network was built in GNS3 and consists of the following components: [cite: 3, 7]
* **Provider (P) Routers:** Core routers within the MPLS network responsible for high-speed label switching.
* **Provider Edge (PE) Routers:** Routers at the edge of the MPLS network that connect to customer networks.
* **Customer Edge (CE) Routers:** Routers on the customer's premises that connect to the PE routers.

[cite_start]These routers were interconnected to create a functional MPLS network. [cite: 8]

---

## Key Configurations

### OSPF Configuration
[cite_start]OSPF was configured to establish connectivity between the P and PE routers, forming the backbone of the MPLS network. [cite: 11] [cite_start]Loopback addresses on the PE routers were used to simulate customer sites. [cite: 12]

### VRF Implementation
[cite_start]To isolate customer traffic, Virtual Routing and Forwarding (VRF) instances were configured on the PE routers. [cite: 15] [cite_start]This created separate routing tables for each customer (Bank A, Bank B, and Bank C), ensuring that their traffic remained isolated. [cite: 15]

### BGP for Route Redistribution
[cite_start]BGP was implemented on the PE routers to manage the routing information between different VRFs. [cite: 17] [cite_start]Static routes pointing to the customer edges were redistributed into BGP to ensure proper end-to-end route propagation. [cite: 16, 17]

### Communication Policies
[cite_start]Specific communication policies were enforced to control the flow of traffic between the different banks: [cite: 9]
* [cite_start]Bank B was explicitly blocked from communicating with Bank C. [cite: 10]
* [cite_start]All other communications were routed based on the MPLS labels and defined policies. [cite: 10]

---

## Verification and Results

[cite_start]The network's functionality was verified through a series of ping tests to confirm that the implemented policies were working correctly. [cite: 18]

* [cite_start]**Successful Pings:** Tests showed that Bank A could communicate with other banks, and that devices within the same customer network (e.g., Bank C to Bank C) could communicate successfully. [cite: 18, 92]
* [cite_start]**Restricted Communication:** The ping test from Bank B to Bank C failed, confirming that the communication restriction policy was successfully enforced. [cite: 101]

[cite_start]These tests validated the successful implementation of the MPLS network and the defined traffic engineering policies. [cite: 18]

---

## Conclusion

[cite_start]This project successfully demonstrated the configuration and operational benefits of an MPLS network compared to traditional IP routing. [cite: 19] [cite_start]By integrating OSPF, VRFs, and BGP, the project highlighted how MPLS can significantly improve traffic management and forwarding efficiency, making it a valuable solution for modern enterprise networks. [cite: 20, 21]
