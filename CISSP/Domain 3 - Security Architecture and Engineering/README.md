# CISSP Cert Prep : 3. Security Architecture and Engineering

***********************************************
Chapter: 1. Secure Design
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
Chapter: 2. Virtualization and Cloud Computing
***********************************************
