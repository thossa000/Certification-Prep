# CISSP Cert Prep : 3. Security Architecture and Engineering

***********************************************
## Chapter: 1. Secure Design
***********************************************
### Secure design principles
Access requests should be designated Subjects (Users, Processes) and objects (File, Memory) to improve design quality. 

Failure Modes - Fail Open, security controls are bypassed when failed. Fail Secure/Closed, locks down upon failure so no access can be granted. 

Isolation and Segmentation, Network Segmentation - Reside functions in different networks to limit access. Process Isolation - Processes cannot access eachother to isolate software. Memory Segmentation - Different processes cannot access other processes memory. Virtual Isolation - VMs cannot use each others resources. 

### Security models
Multilevel security - Computers need to process information of different security levels for people with different security levels.

Bell-LaPadula Model - Enforces confidentiality, ensure users don't get access to info higher than their security level. RULE1 - Simple Security Rule, no subject can "Read Up". RULE2 - *(Star)Property, no "Write Down" ie. top secret user can only create top secret files. Bell-LaPadula is only used in military very rare outside this case.

Biba Model - Enforces Integrity, RULE1 - Simple Integrity Property no "read down", to prevent corrupting the integrity of lower level files.  RULE2 - *-Integrity Property, no "write up" you cannot write to files higher to prevent corruption.

### Security evaluation models
Orange Book (TCSEC) used by government to guide security, now replaced by the Common Criteria. Used to guide system development for NATO countries.

Certification and Accreditation - Certification, a product meets a certain level of security government wide. Accreditation/Authorization, after a system is certified it is decided if the system will be used in a certain environment. 4 options of Accreditation 1. Authorization to Operate (ATO) last 3 years 2. Interim Authorization to Operate (IATO) Last 6 months giving time to fix security issues 3. Interim Authorization to Test (IATT) allowed for testing only 4. Denial of Authorization to Operate (DATO). 

### Separation of duties
Two-Person Control - Requires the authorization of two people to conduct a single action. ie missile launch facility 

Seperation of Duties and 2 person controls used to limit fraud in a company. 

### Selecting security controls
Security Controls are used to - Reduce the likehood of a security issue, reduce the impact of a successful attack, or to detect a security issues when it happens. 

Security Controls are used to keep our risk profile in line with our Risk Appetite.

Defense in Depth - Security Controls used to achieve the same objective, incase on control fails.

Compensating Control - Used to fill known gaps in existing controls ie. place guard at locked door to monitor tailgating.

Technical Controls - Use of technology to achieve security objective. Operational Controls - Human-Driven processes to manage technology (Ie. User access review, log monitoring) Managerial Control - Improved security and risk processes ie. conducting security planning and risk assessments.

### Privacy by design
Privacy By Design - More effective and effiecient and reduced implementation of privacy in an org by doing it during design period has 7 principals. 1. Proactive, Not reactive; Preventive, Not Remedial.    2. Privacy as the Default Setting (protect privacy without needing user action) 3. Privacy Embedded into Design 4. Full Functionality (minimize tradeoff with other objectives like security or business) 5. End-to-End Security Full Lifecycle Protection (Info should be collected, contained and disposed securily) 6. Visibility and Tranparency: Keep It Open (Keep design open for inspection by user or admins) 7. Respect for User Privacy: Keep It User-Centric.

### Secure defaults
Secure Default design, configurations should have a secure state by default ie. firewall default is deny everything, the failure of the firewall won't bypass the control. KISS - Keep It Simple Stupid.

Zero-Trust - Applies least privilege to network access. Do not provide access based on IP or location. Today's environment recognizes sensitive data can be located anymore, in the office, home, on the go. Zero-Trust replaces network focused security with strong authentication and authorization to provide more granular control RBAC. Zero-Trust allows flexibility and doesn't limit access based on location.

Trust but Verify - verify that users are working correctly and security controls are implemented correctly.

***********************************************
## Chapter: 2. Virtualization and Cloud Computing
***********************************************
### Cloud computing roles
Cloud Service Partner - Offers add-on services on the cloud.

### Virtualization
Type 1 Hypervisor (Bare-Metal) - Runs on physical hardware, most common. Type 2 - Server has OS and Hypervisor runs as a program on OS, common on Personal computers (VirtualBox, Parallels) 

VM Sprawl - Unused and unmaintained servers. Can be a source of vulns in the environment. 

### Desktop and application virtualization
VDI - Virtual Desktop Infrastructure - Virtualizing Desktop computing. (ie. Amazon Workspace) 

Application Virtualization - Accessing apps on a system that are running from somewhere else (ie. Citrix XenApp, VMware ThinApp, Microsoft App-V

### Containerization
Containers - Lightweight application virtualization. VMs are heavy, each VM requires an OS. However containerization packages apps into their own platform, not having an OS, and run on the host OS.

Containers must strictly enforce Isolation just like VMs.

### Cloud activities and the Cloud Reference Architecture
ISO 17789 - Cloud Computing reference architecture. Defines responsibilities of cloud service customers which are Use cloud service, Perform service trials, monitor services, administer security, provide billing reports, handle problems, administer tenancies, Perform business administration, select services, and request audit reports.

Cloud Service Provider Activities - Prepare systems and services, monitor services, manage assets, provide audit data, manage customer relationships, perform peering, ensure compliance, provide connectivity to other clouds.

Cloud Service Partner Activities - Design create and maintain services, test services, perform audits, set up legal agreements, acquire/assess customers, assess the marketplace.

Cloud Controls Matrix - Help providers and customers understand detailed security controls to achieve cloud security objectives.

### Edge and fog computing
Edge Computing - Do data processing on device then send to cloud to limit cloud computing. Fog Computing - Compute at central computer in remote location before sending data to the cloud to lower cloud computing.

***********************************************
## Chapter: 3. Hardware Security
***********************************************
### Hardware and firmware security
Secure Boot - Ensure boot integrity by checking OS public key against the boot loader's hash. Decrypting the hash with the vendor's public key for integrity check.

Remote Attestation - After secure boot is completed a compliance report is sent to an external server with the hash values calculated to provide assurance that malicious code isn't being run.

Measured Boot - Each device in the boot chain measure the trust of the next device in the boot chain. Relies on attestation of trusted hashes on TPM.

Hardware Root of Trust - Ensure UEFI is not tampered. Storing keys to verify firmware integrity.

***********************************************
## Chapter: 4. Server Security Issues
***********************************************
### Server and database security
Data Flow Control - Use Network devices and server OS to control bandwidth consumption, not controlling can lead to DOS attack.

Database Attacks - Aggregation, putting together information by corelating low access data. Inference, mapping information to infer outcomes.

### NoSQL databases
NoSQL - database that holds key-value for data and does not require a consistent table format.

Values are retrieved by reference the key associated to the values. Very fast database popular in web apps. Each key may have a different structure of values.

DynamoDB (NoSQL) Permissions - All Item Action (*), Full access. BatchGetItem/GetItem, retrieve many items/single item. BatchWriteItems/PutItem, Store many items/single item. DeleteItem, Remove item. UpdateItem, modify an item. Query, search items.

### Distributed and high performance computing
GRID Computing - Using unused processing capability of several computers in different locations as a virtual supercomputer with centralized controller.

Large-Scale Parallel Data, extremely large data sets processed by several computers working together. ie. SETI (Search for Extraterrestrial Intelligence).

peer2peer (p2p) - decentralized computing ie. bitcoin, BitTorrent, tor browser.

***********************************************
## Chapter: 5. Web Security Issues
***********************************************
### OWASP Top 10
1. Broken access control 2. Cryptographic Failures 3. Injection Flaw 4. Insecure Design 5. Security Misconfiguration 6. Vulnerable and Outdated Components 7. Identifcation and Authentication Failures 8. Software and Data Integrity Failures 9. Security Logging and Monitoring Failures 10. Server-Side Request Forgery.

### Cross-site scripting prevention
XSS - Crosssite scripting - Malicious code injected injected into a website. When other users visit the website they are attacked by the sites malicious script <script> </script>. SOLUTION: Validate user inputs to the site.

### Cross-site request forgery prevention
XSRF/CSRF/SeaSurf - Cross site request forgery. A site using the user's browser to send illegitimate requests to another site with persistent authentication sessions. XSRF requests are often sent using images on websites that execute the code on your browser when clicked on.

SOLUTIONS for CSRF - Rearchitect web app to use encrypted communication for requests. Prevent the use of HTTP GET requests. Automatically log users out after idle period.

SSRF - Server-Side Request Forgery, Requests that attack a targets server rather than the user like in XSRF. By manipulating servers into retrieving malicious data from what it believes to be a trusted source.

### Privilege escalation
Mitigate Privilege escalation through, input validation, OS/Platform/App patching, Least privilege, and DEP(Data Execution Prevention) / ASLR(Address Space Layout Randomization) technologies.

***********************************************
## Chapter: 6. Embedded Systems Security
***********************************************
### Industrial control systems
3 Types ICS - SCADA (Supervisory Control and Data Acquisition) DCS (Distributed Control Systems) and PLC (Programmable Logic Controllers)

SCADA - Remote monitoring of infra. Uses remote telemetry sending reports back to control systems.

DCS - Often used in water and waste water treatment, powerplants, production lines, and refineries. Uses sensors and feedback systems to adjust processes based on info received. Like SCADA, an attack can involve providing incorrect feedback info resulting in a shutdown, overproduction, or delay in the systems.

PLC - Special purpose computers to handle specialized input/output systems. Used in difficult environments with special temp, vibration conditions. Handle input/output without delay. PLC connect to human machine interface. They do not have monitors on their own. Commonly used with SCADA and DCS systems.

PLC use a specialized communication protocol called ModBus, uses simple communication over serial interfaces popular in industrial apps.

### Securing smart devices
Security Wrappers - Vulnerable devices are accessed through a wrapper system that monitors for security issues of the device being accessed and only passes vetted requests to the system.

### Embedded systems
FPGA (Field-Programmable Gate Arrays) - Computer chips that allow the end-user to reprogram the hardware. Allow to customize and update embedded systems.

eFUSE - IBM tech to reprogram chip on embedded systems when necessary.

Real-Time OS (RTOS) provide reliable and secure computing for IOT devices.

CAN (controller area network) Bus - Allows embedded devices to communicate with each other without TCP IP.

Embedded System Constraints - Power capacity, Compute capabilities, network capacity. Running cryptography and patching are difficult.

Embedded Systems often use implied trust principals (every device on the network is friendly) strong authentication is required to mitigate risk.

### Communications for embedded devices
Zigbee and Z-wave - standards providing short-range communication for smart devices.

Wifi is often not available in Embedded system environments so cellular networks are used. 4G 5G requires SIM cards (digital or physical).

Radio is used where cellular is also not available.

***********************************************
## Chapter: 7. Encryption
***********************************************
### Symmetric and asymmetric cryptography
Keys are required for each person in the group of communication. To calculate the number of keys use the following formula n=number of people n(n-1)/2

For asymmetric encryption, sender users receiver's public key to encrypt the message. Only the receiver's private key can be used to decrypt the message.

Asymmetric is slower than symmetric but is scalable unlike symmetric.

### Goals of cryptography
5 Goals of cryptography 1. Confidentiality (Protect data from unauthorized use, data in rest/transit/use) 2. Integrity 3. Authentication 4. Obfuscation (Hiding sensitive data) 5. Non-Repudiation (Prove the message is from the alleged sender, through digital signatures, only possible in asymmetric)

### Codes and ciphers
Code - Substituting one meaning for another. (ie. Police and hospital communication). Used for secrecy and efficiency. Cipher encrypt and decrypt messages - Stream Ciphers, work on one character or bit of a message at a time. Block Cipher, Operate on large segments of the message at the same time.

Rotation Cypher - Rotate characters a certain number. ROT used identify how its rotated, if each letter is shifted 13 characters it is called ROT-13.

Transposition Cypher - Rearrange message using algorithm. Substitution Cypher - Replace each letter with algorithm. Transposition and Substitution are used in modern day cyphers.

### Cryptographic math
Math used in cryptography. XOR (Exclusive OR) - Only one of the inputs are true.    Pseudorandom number generators - Computer algorithm used to generate random numbers. Confusion - hide connection between cyphertext and key to make it more difficult to crack, the cyphertext relies on every bit of the encryption key to decrypt the text. Diffusion - Changing a single bit of the original plaintext should change at least 50% of the cyphertext. Obfuscation - Use cryptography to hide source code, so user running code cannot see the source code.

### Choosing encryption algorithms
Security through Obscurity - Major red flag, security that depends on the secrecy of its approach.

Key Length - Longer key length the higher security but worse performance due to computing power required.

### The perfect encryption algorithm
One-Time Pad - Unbreakable encryption algorithm. One-Time shared key for sender and receiver. Using Rotation based on key. Unusable because sending the One-Time Pad is very difficult without both users being in the same room.

### The cryptographic lifecycle
NIST cryptography Lifecycle - 1. Initiation, gather requirements for new system with CIA objectives of company. 2. Acquisition/Development - Figure out software, hardware, and cryptography requirements 3. Implementation and Assessment, configure and test system. 4. Operations and Maintenance, ensure continued secure operation of crypto system. 5. Sunset, stop using system and destroy/archive sensitive keying material.

***********************************************
## Chapter: 8. Symmetric Cryptography
***********************************************
### Data Encryption Standard
DES - Data Encryption Standard, Designed by IBM in the 1970s. Developed a standard encryption algorithm for unclassified communication by the federal government. Before DES, different agencies used different algorithms.

DES test advise - Block cipher operating on 64-bit blocks, 56 bit key. Now insecure.

### 3DES
3DES - Using DES algorithm on the same text 3 times with 1-3 keys. Using 1 key has no benefit is just as insecure as DES. 2DES is insecure to a meet-in-the-middle attack. 3DES is now insecure as well. 

3DES test notes - block cipher on 64 bit blocks. With 3 keys, key length is 112bits. Phased out due to exploits. 

### AES, Blowfish, and Twofish
AES - Invented because of competition by NIST to replace DES. Original name Rijndael Algorithm, now known as AES (Advanced Encryption Standard). Like DES, AES uses a combo of substitution and transposition to achieve encryption.

AES key facts - Block cipher operating on 128-bit blocks. Keylength of 128, 192, or 256 bits. All keys are considered secure today.

Blowfish - Designed as a potential replacement for DES. Like DES uses a Feistel network and combining substitution and transposition.

Blowfish key facts - Block cipher operating on 64-bit blocks. Key length can be chosen anywhere between 32 and 448 bits. No longer secure.

Twofish - recommended instead of Blowfish, was in the competition that lost to Rijndael algorithm. Also uses Feistel network and combines substitution and transposition.

Twofish Key Facts - Block Cipher on 128-bit blocks. Key length of 128, 192, or 256 bits. Considered secure today.

### RC4
RC4 - Symmetric stream cipher widely used to encrypt network communication. Invented by Ron Rivest in 1987. Was a proprietary trade secret until 1994. WIFI encryption for WEP and WPA allowed the use of RC4. Also SSL and TLS allowed RC4. RC4 uses pseudorandom keystream.

RC4 Key Facts - Stream cipher. Variable length key between 40 bits and 2048 bits. No longer secure as of 2015.

### Cipher modes
Cipher Mode - How an algorithm encrypts and decrypts data. ECB (Electronic Codebook Mode), break plaintext into blocks and encrypt each block with the same key. cypher blocks can end up being the same causing a vulnerability.                   

CBC (Cipher Block Chaining) Mode seeks to resolve the disadvantage of ECB. It feeds the previously encrypted block into the encryption of the next block, but the first plaintext is also fed a XOR IV (Initialization Vector) before being encrypted.  Then the ciphertext is XORed with the next plaintext block before being encrypted.                     

CTR( Counter) Mode, generates a random value known as a Nonce and a Counter at 0. The Nonce is encrypted with an encryption key the XORed with the  first plaintext block to create the first cyphertext block. For the next plaintext block the counter is incremented by 1 and the process repeats. Makes the block cypher act more like a stream cipher.                

GCM (Galois/Counter Mode), adds authentication to the previous cipher modes.

### Steganography
Steganography - Hide text/information in image/audio/video by adjusting pixel, sound. Requires stego software to hide and extract data. Allows you to exfiltrate data and hide information in public domains.

***********************************************
## Chapter: 9. Asymmetric Cryptography
***********************************************

### Rivest, Shamir, Adelman (RSA)
RSA (Rivest, Shamir, Adelman) Algorithm - Asymmetric, users create RSA key pair using two large prime numbers. After some mathematical computation, RSA creates a private and public key. RSA is slow for communication, so instead it is used to create an initial secure communication channel over which a symmetric key is exchanged. The system then uses the symmetric key to encrypt communication for the remainder of the session. RSA was patented by MIT where Ron Rivest worked, but the patent expired in 2000.

RSA Key Facts - Asymmetric, uses variable length key between 1024 and 4096 bits. Still considered secure today.

### PGP and GnuPG
PGP - Pretty Good Privacy, invented by Phil Zimmerman in 1991. Widely used in OpenPGP standard. Uses public and private key pairs but combines both symmetric and asymmetric cryptography.

PGP encryption steps - 1. Plaintext is encrypted with random symmetric key, then the symmetric key is encrypted with the recipient's public key. 2. The recipient decrypts the symmetric key with their private key and then decrypts the message with the symmetric key.

PGP has several commercial products but the open source package is GnuPG (Gnu Privacy Guard). GnuPG or GPG is available on all computing platforms. PGP is not an encryption algorithm itself. It is a frame work to use other encryption algorithms (ones  mentioned before).

### Elliptic-curve and quantum cryptography
Elliptic Curve Cryptography (ECC) - Does not depend on prime factorization like RSA. The difficulty of prime factorization problems is what  keeps RSA secure but requires heavier computing. ECC uses the EC discrete logarithm problem.

Quantum Computing will be the next gen  of cryptography, Quantum computing will break ECC and potentially prime factorization cryptography. But will introduce new quantum algorithms for cryptography.

***********************************************
## Chapter: 10. Key Management
***********************************************
### Key exchange
Out-of-Band Key Exchange - exchanging keys through a trusted channel, different than the one that will be used for communication. (ie. meeting face-to-face or telephone call to exchange key, however this is not very practical in most use cases.)

In-Band Key Exchange - Exchanging key securely digitally. (ie. Diffie-Hellman key exchange).

### Diffie-Hellman
Diffie-Hellman - Invented in 1976 by 3 cryptographers, based on work by Ralph Merkle and turned into an algorithm by Diffie and Hellman. For this exchange the users start with two common numbers (one a prime number), each user then has a secret number, they then each compute a new value with their public key and private keys. The new value is shared with each other and computed to create a symmetric key. The symmetric key cannot be cracked without the private keys.

Elliptic Curve Diffie-Hellman (ECDH) - Relies on EC Problem instead of Prime Factorization.

### Key escrow
Encryption Key Escrow - Allows law enforment to receive encryption keys through the implementation of a clipper chip. Received great controversy due to technology having government backdoors. The clipper chip was not adopted widely.

Recovery Agents - Master key used to decrypt lost keys for an org. Product available from Microsoft but risky as it provides global access to all the orgs data.

### Key stretching
Key Stretching - Add strength to an encryption, salting (add value to key to make it more complex). Hashing (Adds time to the verification process by requiring more math.) These methods are often used for passwords. Hashing slows down brute force attacks by slowing down processing. Key Stretching algorithm commonly used PBKDF2 (Password-Based Key Derivation Function v2) and bcrypt (salt and hash with blowfish). Salting Hashing process should be repeated at least 4000 times.

***********************************************
## Chapter: 11. Public Key Infrastructure
***********************************************
### Trust models
Public Key Infrastructure - PKI, builds on web of trust principal. 

### PKI and digital certificates
PKI depends on highly trusted certificate authorities (CAs). CAs are trusted third-party orgs that verify identity before issuing a digital certificate that contains both identity info of the subject and their public key. 

### Hash functions
Hash function - One way function, takes content and converts to a fixed length output. Two different inputs must never have the same output. A hash is no longer secure if it is reversible or has collision.

MD5 (Message Digest 5) by Ron Rivest, 5th iteration of MD. Message Digest means Hash. MD5 uses 128-bit hash. No longer secure found collision.

SHA - created by NIST. SHA-1 procudes 160-bit value. No longer secure. SHA-2, family of 6 hash functions. Produces output of 224, 256, 384, and 512 bits. Mathematically similar to MD5 therefore will have same vulnerabilities but currently not vuln. SHA-3, came out in 2006, produces hash of any bit length selected by user with Keccak algorithm. Still secure.

RIPEMD - Produce hash of 128,160,256, and 320 bits. 128 is no longer secure. 160-bit used in Bitcoin.

Hash functions are used with asymmetric crypto for digital signatures and digital certificates.

HMAC - Hash-based Message Authentication Code, combines symmetric crypto with hashing provides authentication and integrity with secret key.

### Digital signatures
Digital signatures provide - Authentication, owner of the public key is the one that signed the message. Integrity, the message was not altered. Non-Repudiation, the recipient can prove the prior two to a third party.

Digital Signatures are opposite to asymmetric encryption. The public key is used to verify hash of the message since it was encrypted with the senders private key. This proves authenticity that the message was created by the sender. The goal isn't to send secret messages. If the message requires confidentiality, an added step must be taken to encrypt the message and also produce the digital signature.

### Digital signature standard
Digital Signature Standard, DSS - Published by NIST. Supports 3 different algos for digital signatures by government. Digital Signature Algorithm (DSA) similar to ElGamal algorithm, Rivest-Shamir-Adelman (RSA), Elliptic Curve Digital Signature Algorithm (ECDSA).

### Create a digital certificate
Digital certificates follow X.509 standard. So digital certificates can also be called X.509 certs.

To create a digital certificate you must first, create a public/private key pair with your choice of algorithm (RSA, DSA, ECDSA). Then submit a CSR (Certificate Signing Request) with your public key and identifying information (Name, Email, server name) to a trusted third party for public use or private authority for internal use within your org. The CA (AKA Registration Authority (RA)) will then verify your identity, to avoid issuing an invalid certificate. Once the Identity is verified, the Public Key and identity info is removed and puts it in a format of an x.509 certificate. Then the CA uses its private key to place the CA's digital signature on your digital certificate. This x.509 cert is sent back to you to use to confirm your validity in the future.

### Revoke a digital certificate
Certificate Revocation List (CRL) - Serial numbers of revoked certificates. Certificates that no longer have confidential private keys. CRL is not very efficient because it requires you to check if a certificate is valid by downloading the list.

Online Certificate Status Protocol (OCSP) - Provides real-time certificate status verification by CA. Used by most browsers except Google Chrome, they use their own verification tech.

### Certificate stapling
OSCP uses Certificate Stapling to relieve computational burden of checking cert status. Certificate validation is stapled by CA to OSCP server for 24 hours. So the validation doesn't need to occur on every request.

### Certificate authorities
Certificate Chaining - CAs can trust intermediate CAs (a CA from a company that is hosting their own internal CA, commonly for self-signed certs).

Offline CA - Hosts the root key of a CA. This key is used to sign intermediate CAs of the same company which are considered Online CAs. The Online CAs are used to issue certs to customers.

### Certificate subjects
Certificate subject - Owner of a public key.

Certificate Object Identifier - (ie 1.2.840.113549.1.1.11) Used to identify components of a digital certificate and its origins.

Certificate Subjects - Not just for web servers but certificates can also be for SSH servers, file servers, email servers and more. Also can be used for SANs, routers, switches, VPNs, Access Points. ALso individuals emails/names. and developers for Code Signing.

Certificate Pinning - Ties a cert to a subject for a period of time, if any changes occur to the cert in that time it is reported as a security issue.

### Certificate types
Different Types of certs - 1. Root Cert, core cert for a CA (their offline private key) root of trust in chain (intermediate) certs. 2. Wildcard cert, Cover an entire domain instead of one subject (ie. *.linkedin.com) only goes 1 level deep and does not certify multiple levels of a site.

3 levels of verification a CA can do when issuing a cert - 1. Domain Validation (lowest level of trust) - verifies domain ownership. 2. Organizational Validation - Verifies business names. Extended Validation (Highest level of trust) - CA investigates existence of organization. 

### Certificate formats
Certificate Formats - 1. Distinguished Encoding Rules (DER), binary format uses .der .crt and .cer file extension. 2. Privacy Enhanced Mail (PEM), this name comes from an outdated standard but the cert format is still used, ASCII text format equivalent of DER to be human readable. Stored in .pem or .crt format.  3.  Personal Information Exchange (PFX), binary format. Commonly used by Windows systems. Uses .pfx or .p12 file extension. 4. P7B, ASCII text equivalent to PFX. On Windows systems and uses .p7b file extension.

***********************************************
## Chapter: 12. Cryptanalytic Attacks
***********************************************
### Knowledge-based attacks
Frequency Analysis - Detect pattern in cypher text being generated by key. 

Known Plaintext Attack - When an attacker has both the encrypted and plaintext message. Using this to crack the decryption key. Chosen Plaintext Attack - Use the algorithm to encrypt plaintext to learn the key being used. 

Birthday Attack - Find collision in hash function by the use of probability. 

### Eavesdropping attacks
On-Path attacks - Man in the middle/browser attacks because the attacker is on the path to the intended service. 

Replay Attack - when an attacker captures your authentication and uses it to start their own session with your account. Can be prevented with the use of unique tokens for each session or timestamps (both systems having the same time). 

SSL Stripping - Trick browser into unencrypting a user's encrypted communication.

### Implementation attacks
Side-Channel Attack - Use encryption footprint to collect information being encrypted.

Fault Injection Attack - Compromise integrity of cryptographic device through external fault (power failure, temp failure).

Timing Attack - Measure how long encryption takes to gain more info on the cryptographic process.

### Limitations of encryption algorithms
Entropy - The predictability of cryptographic method. 

Downgrade attack - (ie Poodle Attack) lower encryption strength by using weaker standard when the system is normally using stronger encryption.

### Ransomware
Mimikatz - Steal password from RAM.

***********************************************
## Chapter: 13. Physical Security
***********************************************
### Physical security personnel
Two-Person Integrity - Requires two people enter sensitive areas together to lower the chance of illicit activity. Two-Person Control - Requiring two people to carry out an action (ie. missile launch)

***********************************************
## Chapter: 14. Threat Modeling
***********************************************
### Threat intelligence
Threat Intel - Must have Timeliness, Accuracy, and Reliability to be a good source.

### Managing threat indicators
Threat Indicators - Malicious IP, file signatures, communication patterns that are common to an attacker. 

Cyber Observable eXpression (CybOX) (Framework) - common schema to describe intrusion attempts, malicious software, and other observable security events when sharing info (classify threats).

Structured Threat Info eXpression (STIX) (Language)- Takes CybOX framework properties and gives the language used to describe the properties.

Trusted Automated eXchange of Indicator Info (TAXII) (Exchange)- used to share the information between systems and orgs written in STIX. 

OpenIOC - Developed by Mandiant, used to share threat intel.

### Intelligence sharing
Teams that benefit from threat intel - Incident Response, Vulnerability Management, Risk Management, Security Engineering, Detection and Monitoring.

### Threat research
Threat Research - Using threat intel to identify potential malicious actors based on malicious IP, email, domain, etc. (Reputational Threat Research). Or if malicious actor doesn't have identifiable traits, their pattern of behavior can be used to identify past attackers (behavioral Threat Research). 

Sources of Threat Research - Vendor websites, Vuln feeds, cyber conferences, academic journals, Request for Comment documents, Threat feeds, Social Media, and Adversary tactics, techniques, and procedures (TTP).

### Identifying threats
Threat Management - Structured Approach to potential threats, three approaches. 1. Asset Focus, Asset inventory to analyze threats. 2. Threat Focus, identify how specific known threats can affect your information systems. 3. Service Focus, identify the impact of threats to a specific service (internal or service provider).

### Automating threat intelligence
Threat Intel automation - 1. automatically blacklisting malicious IPs from threat feeds in Firewalls, IPS/IDS, and routers. 2. Combining multiple threat feeds 3. SIEM automation to trigger on events. 4. Data Enrichment (ie. perform recon on source IP of attacker, vuln scan of target system, and pull related logs to the event). 

SOAR (Security Orchestration, Automation, and Response) - Enhance SIEM capabilities through automation.

***********************************************
## Chapter: 15. Software Security Architecture
***********************************************
### SOAP and REST
Simple Object Acces Protocol (SOAP) - Was used for API but no longer, used XML format.  Modern APIs use REST (Representational State Transfer) - Use HTTPS protocol to have accessible RESTful APIs. 

API Security - 1. Encrypt all API communication through HTTPS. 2. Secure distribution, storage, and transmission of API keys.

### SOA and microservices
Service-Oriented Architecture (SOA) - OpenGroup, a standards organization defines SOA with 4 characteristics. 1. Logical representations of a repeatable business activitiy with specified outcome. 2. Self-contained. 3. May be composed of other services. 4. Have Black-Box nature (users don't need to know how a service work, just what it does and how to use it). 

SOA allows the integreation of services from different vendors. Microservices are fine-grained services in cloud environment.
