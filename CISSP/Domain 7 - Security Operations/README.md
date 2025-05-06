# CISSP Cert Prep : 7. Security Operations
***********************************************
## Chapter: 1. Investigations and Forensics
***********************************************
### Network forensics
Netflow - there is also sFlow and IPFIX formats for similarly formatted data.

### Software forensics
Software Forensics - Often used for Intellectual Property disputes and Malware origins (identity author). 

### Reporting and documenting incidents
US-CERT - Computer Emergency Response Team. Any federal government orgs calls them when an incident occurs.

### Electronic discovery (ediscovery)
Legal Holds - Require the preservation of relevant electronic and paper records. 

E-discovery process during dispute: Preservation -> Collection -> Production

***********************************************
## Chapter: 5. Incident Management
***********************************************
### Build an incident response program
IR Plan Elements - Statement of purpose, strategies and goals for IR, Approach to IR, communication with other groups, senior leadership approval.    
CONSULT NIST SP80061 to develop plan.
### Mitigation
Containment Strategy Evaluation - 1. Damage potential 2. Evidence Preservation 3. Service Availability 4. Resource Requirements 5. Expected Effectiveness 6. Solution Time Frame 
### Containment techniques
Containment Strategies - Segmentation, Isolation, Removal.
### Incident eradication and recovery
Eradication - Remove all traces of the incident. Recovery - Restore business process. 

Recovery Practices - Strengthen Access Controls, Application White/Blacklisting, Quarantining, Modify Firewall Rules, redeploying MDM, DLP, URL and content filtering, updating Digital certs. Sanitization and disposal of sensitive media. 

Sanitization Techniques - NIST 8088 - 3 recommended techniques 1. Clearing overwrites info to frustrate casual analysis. 2. Purging - Takes longer than clearing uses cryptographic techniques or degaussing to clear data. 3. Destroying - shredding, pulverization, melting, burning.

### Validation
Validation Process - Verify the secure config of every system. Run vulnerability scans. Perform account and permission reviews. Verify that all apps and systems are logging to SIEM. Validate restoration of all capabilities and services.

### Post-incident activities
Post-Incident activities - 3 activities - 1. Lessons Learned 2. Incident Summary Report (describes response efforts) 3. Incorporate new indicators of compromise in your security monitoring.

***********************************************
## Chapter: 6. Personnel Safety
***********************************************
### Personnel safety
Personnel Safety - Panic Button (silently alerts security personnel of dangerous situation) and Duress Code. (Using code words to trigger an emergency security response.) 
