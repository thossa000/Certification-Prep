# CISSP Cert Prep : 4. Communication and Network Security
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
### Routers, switches, and bridges
Switches - Used to connect endpoint devices to network. Also connects WAPs to provide WFI networks. Switches typically function at Layer 2 using MAC addresses only. Layer 3 switches can provide the function of routers as well as switches. 

Routers - Connect networks together as a central aggregation point. Makes intelligent packet routing decisions. Have some security controls, like ACLs to limit traffic entering or leaving a network. Operates at Layer 3. 

Bridges - Simple switch that only connects two networks together by MAC address.

### Firewalls
Stateless Firewalls - evaluate each connection independently instead of tracking connections, inefficient method that can't make decisions based on context. 

Stateful Inspection - Tracks open connection, once approved the firewall allows the connection without reinspecting for a duration of time. More efficient. 

Firewall Rules should contain - Action (Allow or Block), Source IP, Destination IP, Destination Port, and TCP/UDP Protocol. 

Next-Gen Firewalls (NGFW) - incorporates contextual information into decision making (can consider user identify, nature of request, and time of day) before allow/blocking connection. 

Firewall other roles - Being the NAT Gateway (converting private and public IPs). Content/URL Filtering. 

Web App Firewalls - Run on HTTP and monitor web connections looking for signs of attacks. 

Organizations use both - Network hardware firewalls and host-based software firewalls for defense-in-depth.

### Proxy servers
Forward Proxy Servers - Proxies user connections to external web servers. All traffic passes through Proxy server and the user isn't directory interacting with the web. Benefits: Anonymization (web servers don't receive your IP), performance boosting through cached sites on proxy server, content filtering. 

Reverse Proxy Servers - Works on behalf of the servers instead of user. 

Transparent (In-line or Forced) Proxy Server - Sits on clients network and handles traffic both ways. Not practical due to TLS encryption.

### Load balancers
Load Balancer - Manages demand by having multiple servers that can auto-scale to meet demand. A load balancer holds a Virtual IP that the world sees as the web server IP. They also can provide security functions: SSL certificate management, URL filtering,  Limiting access to website based on IP range. 

Load Balancing Techniques - Round-Robin Scheduling, rotate which server gets the request one-by-one. 

Session-Persistance, the user maintains their web session on the same server and isn't rotated from that server, the Load-Balancer tracks the sessions and gives them a inactive time-limit.

### VPNs and VPN concentrators
VPN Endpoints - Devices that accept remote connections (Site-to-Site or Remote Access). These devices are commonly firewalls, routers, server, or VPN Concentrator (best option for high demand environments because of VPN resource intensive encryption). 

VPN encryption for Site-to-Site commonly occurs through IPSEC (Network layer 3) but supports Layer 2 Tunneling Protocol (L2TP). 
Remote Access (user) VPNs occur through SSL/TLS VPNs at the application layer over TCP port 443. HTML5 VPNS work entirely within the web browser from web servers and proxies. 

Full-Tunnel VPN - All traffic leaving connected devices is routed through VPN tunnel, regardless of final destination. 
Split-Tunnel VPN - Corporate traffic is routed through VPN while regular traffic is routed directly to destination. Less resource intensive but not recommended as some traffic is suseptible to eavesdropping.
Always On VPN - VPN automatically connects when device powers on.

### Network intrusion detection and prevention
IDS can be used to detect - SQL Injections, Malformed Packets, Unusual Logins from users, and BotNet traffic.
IPS just like IDS but takes immediate corrective action by blocking traffic of attacks above. 

1st method - IDS/IPS most commonly use Signature Detection Systems (AKA Rule-Based Detection) to identify rules for malicious activity from databases. Has low false positive rate. Downside is cannot detect zero-day attacks.
2nd method - Anomaly Detection System (AKA behaviour based/heuristic detection) - Builds model for normal activity and alerts/blocks on anomalous activity. Can potentially detect zero-day. Downside is has higher false-positive rate. 

IPS Deployment: In-Band - IPS sits on path of network traffic, blocking suspicious traffic from entering the network. Downside, an issue with the IPS can disrupt communication.
Out-of-Band (passive) - Sits outside the flow of network traffic, sits on SPAN port of a switch receives a copy of all traffic but cannot disrupt the flow of traffic. The IPS can then block future traffic to the offending system once an alert is triggered but cannot block the initial attack.

### Protocol analyzers
WireShark - most popular | TCPDump - Command-line Protocol Analyzer | both share the same language built on libpcap library.
TCPreplay - Command-Line tool that takes packet captures from Wireshark or TCPDump and allows you to edit and replay the traffic.

### Unified threat management
UTM - Unified Threat Management - Solution for small orgs, packing security appliances into one. Basic UTMs are Router and Firewall. 
Additional Features include VPN Connectivity, IPS, and IDS. 
Also can include URL Filtering, content inspection, malware inspection, and email/spam filtering.

UTMs still require regular security monitoring. Not designed for large orgs that require dedicated devices for the above mentioned features. 

### Content distribution networks
Content Distribution Networks (CDN) (AKA Content Delivery Networks) - Seeks to address web server scaling issues by providing a shared web infrastructure on the cloud. Servers located around the world known as Points of Presence retrieve your web server content and cache it for nearby users.    BENEFITS: On-demand scaling, more cost efficient than scaling your on-prem infra, locality of content to users, and security benefits (DDos Protection and web app firewalls).

***********************************************
## Chapter: 4. Network Security Techniques
***********************************************
