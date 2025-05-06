# CISSP Cert Prep : 6. Security Assessment and Testing
***********************************************
## Chapter: 4. Code Testing
***********************************************
### Code review
Fagan Inspection - The most formal code review (reading code) technique, has 6 steps - Planning, Overview, Preparation, Meeting, Rework, Follow up.

### Code tests
Code Tests - Using software to perform Static Tests and Dynamic Tests 

Synthetic Transactions - Scripted sets of input with known expected outputs to confirm proper function.

### Fuzz testing
Types of Fuzzing - Developer-Supplied Input, Developer-Supplied script, Generation fuzzing, Mutation fuzzing. 

Fuzzing - Providing auto generated input values to find errors in code. Commonly done with OWASP ZAP.

### Misuse case testing
Misuse Case Testing - How can an attacker break the software. Should have a mix of the software's developers and outside analysts. Misuse cases try unexpected inputs, missing input, injection attacks, and more.

### Test coverage analysis
Test Coverage - Percentage of software tested. Cases can be Functions, Lines of code, Conditional Branching, and known use cases.

Test Coverage = Cases Tested/Total Cases. 

***********************************************
## Chapter: 5. Business Continuity Planning
***********************************************
### Business continuity planning
Business Impact Assessment - Assessing risks with ALE to establish priorities.  Used to create Business Continuity Planning.

***********************************************
## Chapter: 6. Disaster Recovery Planning
***********************************************
### Disaster recovery
When a BCP fails Disaster Recovery is initiated. Disaster Recovery Plan is created to bring operations back ASAP. 

RTO - Maximum time that it should take to recover from disaster. 

Recovery Service Level - Percentage of service that must be available during a disaster. 

RPO - Maximum time period from which data may be lost in a disaster.

### Backups
Differential backup - Backs up changes from last full backup. 

Incremental Backup - Backs up change from last incremental backup.

### Restoring backups
Incremental - Takes less space to store but more time to restore. 

Differential - Takes more storage space but less time to restore. 

Non-Persistence - Allows you to back up only unique data.

### Testing BC/DR plans
DR Testing - 1. Read-Through - DR team members review their roles and provide feedback. 

2. Walk-Through (AKA Table-Top Exercise)- Everyone on DR team gathers together for a formal review of DR plan.

3. Simulation Test - Team gathers for practice DR scenarios.

4. Parallel tests - Active DR environment to simulate disaster.

5. Full-Interruption test - Cause planned disaster to test plan.

### After action reports
After Action Report - Create formal record of BC or DR event and to review for improvements and successes. Contains with Executive Summary, Detailed summary, Lessons Learned, and Conclusion (next steps from Lessons Learned).

***********************************************
## Chapter: 7. Assessing Security Processes
***********************************************
### Management review and approval
Management reviews - Verify accuracy and completeness of work and create culture of oversight for fraud.

### Security Metrics
Key Risk Indicator - Criteria's are Business Impact, Effort to implement/measure/support, reliability, and sensitivity.

### Audits and assessments
Audits - External review. 

Assessments - Internal reviews.
