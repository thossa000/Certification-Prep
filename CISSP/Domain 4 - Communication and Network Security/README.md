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
### Network access control
NAC authentication occurs through 802.1X 

NAC Posture Checking - Conducting security checks on supplicant machine before allowing network access.

### Firewall rule management
Shadowed Rules - Firewall rules that are never executed due to order of rules being executed. 

Promiscuous rules - allow more access than necessary

### Router configuration security
Orphaned Rules - rules to allow access to decommissioned systems and services. Pose risk if the IP of the decommissioned server is reused for another server. 

Firewalls vs Router ACL - Firewalls are purpose specific so much more efficient. Firewalls an make conditional rules. Firewalls offer more advanced security, integrate with IDS/IPS, perform traffic inspection, and threat intel. 

Placing some ACL rules on routers can reduce burden on firewalls. 

Routers allow Quality of Service (QOS) controls that prioritize critical network traffic by assigning bandwidth.

### Switch configuration security
VLAN Security -1. VLAN Pruning, limit unnecessary exposure of VLANs by limiting the number of switches that are trunked. 2. VLAN Trunk Negotiation, prevents VLAN hopping. 3. Port Security, only authorized MAC addresses to connect to switch. 4. DHCP Snooping, switch inspects DHCP messages to ensure they are coming from authorized DHCP servers.

### Maintaining network availability
Network Availability attacks - SYN Flood, flood connection state table on firewalls with half-open connections. MAC Flood, Fill MAC address table with many entries, flooding traffic on all ports. 

Routing Loops - Allow broadcast storms, solution use Spanning Tree Protocol (STP) to prevent broadcast storms, by preventing loops. 

STP - Uses Bridge Protocol Data Units, or BPDUs. If an attack can spoof BPDU they can cripple network. Ensure BPDU Guard is enabled to block malicious STP updates.

### Network monitoring
Ingress Filtering - logs for inbound traffic (monitor for inbound attacks). Egress Filtering - logs for outbound traffic (monitor for malicious activity on your network). 

NetFlow Data - doesn't record full packets, instead captures source and destination system, source and destination ports, timestamps, and amount of data transferred.    

NetFlow data logs are better than storing full packet logs because of storage considerations. And the missing info in NetFlow data logs can often be inferred based on the information.

### SNMP
SNMP - 3 components, 1. managed device (network device that receives SNMP commands) 2. Agent, agent that is installed on device for SNMP communication. 3. Network Management System, admin device for administration.    

Requests are GetRequest/SetRequest and agent sends a Response. If the agent needs to send a message to the NMS it will send an SNMP Trap.

### Deception technologies
Darknets - Unused but monitored IP address space on a network, use of these IP address will trigger security response..  Honeyfiles - False sensitive data to alert admins of attack attempts. DNS Sinkhole - Altered DNS records on company DNS to reroute botnet traffic, alerting security team of botnet attack.

***********************************************
## Chapter: 5. Specialized Networking
***********************************************
### Telephony
VoIP - Telephones over IP (convert analog voice to digital), should be secured with Encryption, and Network Segmentation when encryption isn't possible.

### Multimedia collaboration
Extensible Messaging and Presence Protocol (XMPP) - XMPP provider an open-source messaging protocol. 

SMS Vulnerabilities, no encryption, and no authentication (easily spoofed)

### Storage networks
SAN vs NAS - NAS, shows as fileshare, SAN as dedicated drive. SAN come from dedicated network. 

SAN can be used over Fiber-Channel, Fiber Channel over Ethernet, or iSCSI.

***********************************************
## Chapter: 6. Transport Encryption
***********************************************
### TLS and SSL
Session Key for TLS encryption. Also known as ephemeral key. 

SSL Inspection - inspects encrypted network traffic through a man-in-middle attack from your own firewall. 

OpenSSL - Opensource TLS package.

### IPsec
IPsec - secures entire packet payload. IPsec uses Encapsulating Security Payload (ESP) provides confidentiality and integrity protection for packet payloads. Authentication Header (AH) Provides integrity protection (tamper proofing) for packet headers and payload. 

IPsec - provides a list of cryptographic algorithms that a server is using through a Security Association (SA). 

IPsec used in VPNs, Tunnel mode to create site-site VPNs making the two sites transparent to users. Transport Mode for end-user VPNs. Transport Mode VPNs are no longer common in favour of TLS VPNs.

### Remote network access
Remote Shell - Provide cmd access to a remote system (originally Telnet, now SSH). Remote Desktop - Graphical interface for remote systems (RDP).

### Securing common protocols
HTTPS - Uses TLS to first confirm website digital cert, then creating a session key (symmetric key) with the server. 

SSH - Also creates ephemeral/session key to begin session with server. 

Secure Copy (SCP) provides command-line file transfer over SSH. 

FTPS - Adds TLS to FTP. SFTP - Adds SSH to FTP. 

Real-Time Protocol (RTP) based VoIP service should instead use Secure RTP (SRTP). 

Network time Protocol (NTP) should use NTPsec. 

Email ports - POP - port 110 (encrypted port 995). IMAP port 143 (encrypted port 993). SMTP port 25 (encrypted port 465). 

S/MIME - encrypt email at app layer. 

DNSsec - Adds digital signature to DNS allowing verification of DNS records. 

LDAPS - secure LDAP.

***********************************************
## Chapter: 7. Wireless Networking
***********************************************
### Understanding wireless networking
Wifi devices use radio transmitters and receivers for communication. 

Wifi Standards - 802.11 (1997) allows 2Mbps | 802.11b (1999) allows 11Mbps | 802.11g (2003) allows 22Mbps | 802.11n (2009) allows 600Mbps with MiMo antennas  | 802.11ac (2014) allows 1Gbps+

### Wireless encryption
WEP - wifi encryption, vulnerable. WPA - replaced WEP in 2003. Uses TKIP to rapidly rotate encryption key, now vulnerable. WPA2 - Released in 2004, uses AES encryption with CCMP, has potential vulnerabilities but still secure.  WPA3 (2020)-  Also supports CCMP but uses SAE (Simultaneous Authentication of Equals) for key exchange (based on DiffieHelmen).

### Wireless authentication
Wifi Authentication - Pre-shared keys (home wifi password) that is encrypted with PBKDF2 (key stretching). | Enterprise Authentication - Authorize wifi through Authentication Server. Used Lightweight EAP (LEAP) created by Cisco, insecure protocol using MS-CHAP. Using Protected EAP (PEAP) is recommended, tunnels EAP variant inside TLS session tunnel. 

EAP Variants - There are over 100 versions of EAP. These are some: EAP-TLS, secure. EAP-TTLS, secure. EAP-FAST (Cisco), secure. EAP-MD5, insecure. 

Captive Portals - another variant of wifi authentication, redirects to web page to authenticate.

### Wireless signal propagation
Omnidirectional antennas - send radio waves in all directions. Directional antennas, point waves in single direction. 802.11ac WAP - steers signal from omnidirectional antennas towards device. 

Site Survey - Determine optimal AP placement through hardware and software testing. 

Adjust radio frequency channels of wifi to avoid interference from nearby networks. 

Manipulate WAP power level to adjust coverage.

### Wireless networking equipment
FAT Access Points - Contain all the hardware and software needed to operate wireless network. Thin Access Points - Rely on wireless controllers for configuration. Wireless controllers can improve wifi coverage by reducing interference, and adjusting power among WAPs. 

Aircrack-ng - Wifi Analyzer used to search for rogue networks and test wifi security.

***********************************************
## Chapter: 8. Mobile Device Security
***********************************************
### Mobile device tracking
Asset Tracking Lifecycle - 1. Device Request 2. Ordering and Receiving 3. Initial Configuration 4. Device Assignment 5. Device Decommissioning.

### Mobile deployment models
Choose Your Own Device - Employee picks device for company to purchase them to standardize hardware in company environment. 

Company Owned, Personally Enabled - Allows generous personal use of Corporate owned devices.

***********************************************
## Chapter: 9. Host Security
***********************************************
### Malware prevention
Virus - Malicious Code that spread by human action (Email Attachment, Download). Worms - Carry same payloads as Virus but spread by themselves on a network. Trojan Horses - Hides in what appears and functions like legitimate software, but with hidden payload. Spyware - Gather info from infected system (ie. Keystroke logger). 

Endpoint Detection and Response (EDR) trigger automated response to attack on endpoint host. Can use Sandboxing to isolate malicious software.
