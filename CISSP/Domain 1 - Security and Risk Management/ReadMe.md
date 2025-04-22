# CISSP Cert Prep : 1. Security and Risk Management

***********************************************
Chapter: 2. Security Governance
***********************************************
### Organizational processes
Security Governance - Oversight of security, risk management, most senior level of governance is the Board of Directors. 

### Security roles and responsibilities
CISO - reports to CIO or Risk Management Leader 

Due Care - Fulfiling legal responsibilities and professional best Practices. 

Due Diligence - Taking reasonable measures to investigate security risks. 

### Control frameworks
Security Controls are set to protect CIA. Security Control Frameworks are used to guide security program design.

COBIT - Used by auditors, used to link business goals with security. Has 6 goals:
1. Provide Stakeholder Value
2. Holistic Approach
3. Dynamic Governance System
4. Governance Distinct From Management
5. Tailored to Enterprise Needs
6. End-to-End Governance System

ISO 27001 - Covers security control objectives. Very popular 

ISO27702 - Cover security control implementation 

ISO 27701 - Covers privacy controls. 

ISO 31000 - Cover Risk Management Programs 

NIST 800-53 - Mandatory for federal agencies, however many organizations use it aswell. Covers building a security program. 

NIST Cybersecurity Framework (CSF) - Provides a common language for cyber risk. Helps identify and prioritize actions to mitigate and reduce risk. Aligns security actions across control types. Identify, Protect, Detect, Respond, Recover.

***********************************************
Chapter: 3. Compliance and Ethics
***********************************************
### Data privacy
GAPP - Data Privacy, has 10 components to help with data privacy. Developed by 4 institutions. 
1. American Institute of Certified Public Accountants (AICPA).
2. Canadian Institute of Chartered Accounts (CICA).
3. ISACA.
4. Institute of Internal Auditors (IIA).

ISO 27018 - Covers Practice for protection of PII 

ITADA - Identity Therft and Assumption Deterrence Act 


Side Note: Study all 10 GAP principals.

### Computer crimes
CFAA - Law that makings hacking a criminal offence. 

ITADA - Identity Therft and Assumption Deterrence Act 

### Import and export controls
Intellection Property - Copyrights - Projects Creative Work. Automatically granted to the creator. Copyrights last 70 years beyond creator's death. 

Trademarks - Protect words and symbols. Must be registered and renewed every 10 years. Abandoned if not used after 5 years. 

Patents - Protect inventions, an inventor must demonstrate their invention is Useful, Novel, and Non-Obvious. Patents last 20 years, requires public disclosure of invention on what it is and how it works. 

Trade Secrets - patents within a company, not public. 

Import/Export controls - ITAR - International Traffic in Arms Regulations - Covers Defense articles. 

EAR - Export Admin Regulations - Cover dual user tech 

OFAC - Office of Foreign Asset Controls, covers sanctioned country rules. 

### Ethics
ISC2 Ethics Code - CANON1, Protect society, infrastructure, and common good. 

CANON2, Act honourable, with justifise, and responsibility. 

CANON3, Duties must be diligent and compatent. 

CANON4, Your actions should help the profession and protect ISC2 (snitch on others that are ISC2 and harming you or your profession).  

CANON1 and 2, protect the public CANON3 , Protect clients. CANON4, protect the profession.

***********************************************
Chapter: 4. Security Policy
***********************************************
### Security policy framework
Policy - The foundation for a security program, states security expections, requirest compliance from all employees.

Standards - Provide specific details of security controls, derive their authority from policies. Requires employee compliance. Good standards can be used from CIS Benchmark.

Guidelines - Providing security advise, best practices (IE. Use encrypted network when available, use VPN when not available. 

### Security policies
Procedures - Step-By-Step process for an activity like incident response. Compliance may or may not be necessary.

Data Storage Policy - Explain appropirate storage location and access controls. Encryption requirements (ie. data can be unencrypted in storage in local DC but encrypted at rest in the cloud). 

***********************************************
Chapter: 5. Business Continuity
***********************************************
### Business continuity planning
Defining BCP Scope - What Business activities does the plan cover? What systems are covered? What controls will it consider? 

BIA - Business Impact Assessment - Identifies and prioritizes IT risks. 

### High availability and fault tolerance
BCP should also contain personel succession planning. For departing employees. 

Most common hardware failures - Power supply, storage media, networking. Diversify technology, vendors, and cryptography to remove single points of failure.

RAID1 - Mirrored across 2 disks. RAID 5 - Disk striping with parity, If one disk fails the system can regenerate a single disk. RAID is for fault tolarence, does not provide backups. 

NIC Teaming - using multiple NICs to prevent hardware failure. Also add multipath networks to provide route redundancy. 

***********************************************
Chapter: 6. Personnel Security
***********************************************
### Employee privacy
Minimization - Orgs should only collect and store employee information that is needed for the time needed then removed. 

### Conducting investigations
Interview - can be conducted by cyber because voluntary. Interrogation - involuntary, does not involve cyber.

Types of Investigations - Operational/administrative, Criminal, Civil, Regulatory. Operational - Look into technology issues to restore normal operations involves root cause analysis, no legal actions involved. Criminal - Investigate violation of criminal law, very high stakes. Use beyond a reasonable doubt standard of evidence. Civil - Also an investigation, but not criminal law. No one is going to jail. Uses preponderance (most likely) of evidence standard. Regulatory - conducted by government or industry regulator, can become civil or criminal. 

***********************************************
Chapter: 7. Risk Management
***********************************************
### Risk assessment

Threat - External Force (Hurricane, or terrorist). Threat Vector - Method used by hacker. Vulnerability - Security control weakness used to exploit. You control vulnerabilities in your org. Risk - A threat that can exploit a vuln. 

Risk Assessment - Rank risks by likelyhood and impact (amount of damage). Review Qualitative Risk Assessment chart.

### Quantitative risk assessment

AV = Asset Value (Determined with Original cost, Depreciated cost (Accountant), Replacement cost (Risk Manager))  EF = Exposure Factor | SLE = Single Loss Expectancy | SLE = AV * EF (This gives us impact of risk || ARO = Annualized Rate of Occurrence, ALE = Annualized Loss Expectancy | ALE = SLE * ARO. 

Mean Time to Failure (MTTF) for non-repairable assets. Mean Time Between Failures (MTBF) Mean Time to Repair (MTTR) for repairable assets. 

### Risk management
Risk Management - Avoidance, Transference, Mitigation, Acceptance. 

### Security control selection and implementation
Risk after a control is applied is called the residual risk. Control risk is the risk of a control failing. The risk appetite of a company is taking their control risk + residual risk. 

### Risk management frameworks
Risk Management Frameworks - NIST SP 800-37 (most widely used, mandatory for government). 6 Steps involved - Categorize Info System (Tech Architecture, Organization specific info), Select Security Controls, Implement Security Controls, Assess Security Controls, Authorize Info System (Accept remaining risk), Monitor Security Controls. 

### Risk visibility and reporting
Risk Register - Centralized document of nature and status of known risks. Includes risk description, category, probability/impact, risk rating which is probability * impact, Risk Management actions taken or in progress.     Risks are identified from Risk Assessment results, Audit findings, team member output, and threat intel. 

Threat Intel - Sharing threat intel between orgs or from a vendor. Threat intel used to share nature and characteristics of attacks experienced, blacklist known malicious IPs, or to monitor risk trends in a general way.

Risk Matrix/Heat Map - Used to display risks to senior management. 

***********************************************
Chapter: 8. Threat Modeling
***********************************************
### Intelligence sharing

TAXII, STIX, and CyBOX - Threat intel sharing.

ISACs - Information Sharing and Analysis Centers, every industry has an ISAC, they are non-profit orgs. 

### Threat hunting
Structured approach to threat management - Asset Focused approach, use asset inventory as the basis for analysis. Threat focused approach - Identify possible threat actors that affect each info systems. Service focused approach - Identify the impact of threats on specific services. 

Threat Hunting - Assume compromise. Seek out IOC on your network through analytics and expertise. Threat hunters think like attackers. They establish hypothesis based on threat actor profiles, threat feeds, and advisory boards. IOC can include Unusual binary files, unexpected proccesses/resource consumption/accounts, deviations in network traffic, unexplained log entries or config changes. Use threat hunting products and focus and pair with critical infrastructure. Once threat is identified begin incident response process. 

***********************************************
Chapter: 9. Supply Chain Risk Management
***********************************************
### Managing vendor relationships
ISO 27036 - Infosec for Vendor/Supplier relationships 

### Vendor agreements
Busines Partnership Agreement (BPA) - Between two businesses working together in a partnership. MOU - Document aspects of a relationship when legal dispute is unlikely. Often used internally. Interconnection security agreement (ISA) - How two companies will connect their infra and data. Master Services Agreement (MSA) - When two companies have multiple agreements together for different project. Is an overview agreement. SOW - Specific terms of a project governed by the MSA. 

### Vendor audits and assessments
Assessments - Performed at the request of IT, Audit - Performed at the request of management or regulators 

### Cloud audits
SSAE 18 (Attestation) applies in the US. ISAE 3402 is international. These are standards to guide SOC audits. They are similar in scope and purpose. 

SOC - Service Organization Control Reports | SOC1 - Most common, provide customers assurance of service providers when conducting financial audits. | SOC2 - More detailed testing of Conf, Integr, Avail for service provider assurance. Contains detailed sensitive info | SOC3 - Same as SOC2 but for public reporting at a high level. 

Type1 report - Describe controls service provider has in place and opinion on the suitability of those controls. No opinion if the controls are effective | Type 2 - Same as Type 1 but controls are also tested and verified. 

### Security service providers
Cloud Access Security Broker - Security service to monitor for security issues. 

***********************************************
Chapter: 10. Awareness and Training
***********************************************
### Security awareness training
Security Training - Active learning | Security Awareness - Reminding security best practice passively. 

### Compliance training
Compliance Training - should include relevant laws, regulations, and standards.
