***********************************************
## Chapter: 2. Secure Network Design
***********************************************
### VLANs and network segmentation
Configuring VLAN - Enable VLAN trunking, and assign switchports to VLANs. 

### Security device placement
SPAN port - port on switch that receives a copy of all traffic on a switch. 

Port mirroring - allows the monitoring of traffic on a single switchport 

SIEM - Gathers info from Collectors, then analyzes information with a cenralized aggregation and correlation engine. Collectors should be placed near systems generating records but Correlation Engine should be in a secure location only accessible by authorized admins. 

VPN Concentrators - Aggregates remote user connections. Often resides on its own VLAN where access controls are restricted for remote user activity. 

SSL Accelerators - Hand difficult cryptographic work of setting up TLS connections. Reside in DMZ 

DDoS Mitigation Tools - Block DDoS attacks, should be placed outside your network, ideally the service can be purchased from your ISP so it is blocked before reaching your network. 

### Software-defined networking (SDN)
Control Plane - Responsible for making routing and switching decisions of traffic around your network, will reroute data as it becomes congested.     Data Plane - Responsible for carrying out the instructions of the control plane. 

Software-Defined Networking (SDN) seperates the control plan from the data plane. Instead of each router being configured. The decisions come from an SDN controller. The controller is managed by network admins and algorithms. SDN makes the network programmable, developers can write code to modify network as requirements change.          SDN is made possible through Encapsulation (allows one protocol to carry traffic that uses another protocol.) 

VXLAN (SDN) - Builds overlay networks that operate at Layer 2 using Layer 3 equipment. 

SDN Security Benefits - Allow granular network config. Allows quicker response to security incidents. CONS - Increases complexity of network requiring strong access control to avoid bad actors gaining access and setting up eavesdropping or impersonation attacks.

***********************************************
## Chapter: 3. Network Security Devices
***********************************************
