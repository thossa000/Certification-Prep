# ISO/IEC 27001:2022 Lead Auditor
Notes for review for the ISO 27001:2022 Lead Auditor certification exam.

# The Basics
## History and Background
ISO stands for International Organization for Standardization

Established in 1947 by a group of engineers to develop standards for quality, safety, and efficiency. Now recognized globally across private and public sectors for all industries.

The ISO 27001 standard is tailored to each organization to best fit the requirements of the standard.

ISO comprises National Standardization Bodies (NSBs) from over 160 countries. NSBs contribute via consensus, ensuring global representation for comprehensive standards development. Notable NSBs include:

1. USA: American National Accreditation Board (ANAB)
2. UK: British Standard Institution (BSI)

Standards are developed by Technical Committees (TCs) of SMEs from industry, government, and academia. Joint TCs are groups of TCs and Subcommittees (SCs)

- JTC 1 covers Information Technology (IT)
- JTC1/SC 27 develop ISO 27000 series (ISMS)

### Benefits of ISO:
1. Standards build trust and credibility
2. Cost savings
3. Operational efficiency
4. enhanced marketability
5. Basis for legal/regulatory requirements and procurement processes

## Accreditation vs. Certification

Accreditation: Validates that a Certification Body is competent to perform a certification body.

Certification: Validates that an organization meets the requirements of a specific ISO standard. Performed by a Accredited Certification Body.

CBs assess whether an organization's management system confirms to the ISO standard. Accreditation is voluntary for CBs, however when they certify an organization it will miss stamps showing the governing body that accredits the CBs.

ISO 17021-1 defines the requirements for CBs to achieve accreditation. This defines the processes and audit evidence management requirements, the competencies required for and auditor, and consistencies in audit conduct/practices and time allocation. CBs are audited annually by the accreditation bodies for ongoing compliance.

ABs undergo peer evaluations through the International Accreditation Forum (IAF). ABs oversee CBs to ensure checks and balances. 

IAF CertSearch is a public Certification Database to view all certifications issued by an accredited CB. This allows people to validate an organization certificate received from a accredited CB.

Unaccredited certificates lack market trust and recognition since they are not validated by an AB recognized globally through the IAF MLA (Multilateral Recognition Arrangement).

## Multi-year Audit Cycles
ISO certification is typically a 3-year audit cycle

- Year 1: Initial Certification Audit (2 Stages)
- Year 2: First Surveillance Audit
- Year 3: Second Surveillance Audit
- Year 4: Recertification Audit (1 Stage)

### Initial Certification Audit's 2 Stages
- Stage 1: Reviews the design of the management system and governance documentation
- Stage 2: Assesses the implementation and effectiveness of the management system

After each stage is passed, a recommendation is made by the auditor to a decision commitee (in the same CB) impartial to the audit to proceed to the next stage, once the decision commitee passes stage 2, the ISO27001 certification is granted for 3 years (subject to success annual surveillance audits).

### Surveillance Audits
Conducted to verify continued conformity to ISO standards:
- Review prior nonconformities and corrective actions
- Changes to the organization or certification scope
- High-risk areas identified by the auditor or organization.

Non-compliance with surveillance audits can result in certification suspension and withdrawal.

### Recertification Audit
Performed at the end of the 3-year cycle to reassess the entirety of the management system. Similar to Initial Certification Audit but conducted in a single stage workstream. Successful recertification generated a renewed cert with a new 3-year expiration. Failing recertification causes suspension/withdrawal.

Multi-year audit cycles promotes:
- Continual Improvement
- Alignment with system goals and organizational priorities
- Risk prioritization and identification
- Corrective actions for security gaps

Nonconformities (NC):

- Minor NC: does not affect the capability of the management system to achieve intended result
- Major NC: affects the capability of the management system to achieve intended result

NCs are typically not raised in Stage 1 certification audits, they are instead called Areas of Concern (AOC). AOCs do not explicitly require correction but can turn to NCs in future audits.

NCs are addresses via short-term corrections and long-term corrective actions.
- Corrections: Resolve the detected issue
- Corrective Action: Identify and resolve the root cause to prevent reoccurrence

Auditors review Corrective Actions for existing NCs before recertifying. Unresolved NCs or ineffective corrective actions can lead to certification suspension/withdrawal.

### Common Challenges
- Resource constraints: Budget cuts and staff changes
- Process changes: New tools or processes might cause failures with ISO requirements
- Scope changes: Adding products, services, or acquisitions to certification scope with implementing proper controls

### Lead Auditor Priorities
- Tailoring Audits: Each audit requires different focus, initial certification is comprehensive, while surveillance audits target high-risk areas or new elements
- Tracking Corrective Actions: Maintain corrective actions tracker for visibility and remediations of NCs
- Risk Management: Ensure risks are reviewed, updated and mitigated at least once annually to promote continuous improvement.

## Normative & Informative Criteria 
ISO standards have 2 types of criterias

- Normative: Mandatory requirements and organization must meet.
- Informative: Recommendations and best practice to support implemention, not required but recommended.

Auditors only evaluate confirmity with normative criteria.

If an ISO standard clauses has the word "shall" it is a normative criteria and a hard requirement.

If an ISO standard control has the word "should" it is a infromative criteria and is a recommendation or best practice. ISO27002 is a document for implementation guidence for ISO 27001 Annex A. ISO27003 has implementation guidance for ISO27001 clauses.

Optional controls - Using custom controls to meet ISO 27001 clauses, these become normative criterias and are still audited. Often used when you bring controls from other frameworks that you've implemented to meet ISO 27001 requirements.

## Revisions vs. Amendments vs. Corrigenda

ISO standards are updated to reflect advancements in tech, industry, best practices, and regulatory standards. Auditors are required to familiarize themselves with updates to standards.

- Revision: major update, occurs every 5-10 years, add new requirements and remove outdated ones. ISO 27001 was revised in 2022 making changes to risk assessment procedures and Annex A controls.
    Organizations have a 1-3 year transition period to update processes, procedures, controls, documentation, and policies to meet revisions. Also to conduct gap assesment to address new requirements.
- Amendment: Minor change to a standard, addressing specific requirements. Amendments are implemented immediately and audited in the next planned audit. February 2024 had an amendment to ISO 27001 to require assessments of climate change relevance of ISMSs.
- Corrigendum: correction to an ISO standard. Typically grammar/formatting changes and dependencies/reference updates. No significant impact to organizations. Auditors are required to use latest corrected versions of these documents.

# Understanding the ISMS
## What is ISO 27001:2022?
Published in 2005, revised in 2013, and revised again in 2022. 

Framework takes a risk-based approach to managing information security risks, follows the CIA triad.

It provides a systematic, repeatable approach for managing sensitive data. Focusing on threat and vulnerability management to identify and mitigate risks. Also to compy with regulatory or contractual requirements. Enhancing information security practices.

2022 revision updated ANnex A controls to address evolving cyber threats. Added 11 new controls for threat intel and DLP.

Aligned structure with ISO Harmonized Structure (Annex SL) for better integration with other ISO standards.

ISO 27001 follows the Plan-Do-Check-Act (PFCA) lifecycle:

- Plan: Establish ISMS policies, resources, and objectives
- Do: Implement risk assesments, treatments, and controls
- Check: Monitor key metrics to ensure effectiveness
- Act: Improve by addressing nonconformities

## Structure of ISO 27001

- Clause 1: Scope
- Clause 2: Normative References
- Clause 3: Terms and Definitions
- Clause 4-10: Core management system elements. Reference ISO 27003 for guidance on Clauses 4-10.
- Clause 4: Context of the Organization - Define drivers, stakeholders, and scope of ISMS
- Clause 5: Leadership - Top leadership demonstrates commitment, assign responsibility, and provides strategic direction
- Clause 6: Planning - Define security objectives and establish a risks management proccess for consistent assessments
- Clause 7: Support - Allocate resources, maintain competency, establish communication plans
- Clause 8: Operation - Plan, implement, and control ISMS processes, including risk assessments and treatments
- Clause 9: Performance Evaluation - Monitor and measure ISMS effectiveness through audits and management reviews
- Clause 10: Improvement - Identify oppurtunities for improvement and correct nonconformities
- Annex A: Provides a detailed list of control for use to mitigiate identified, "in-scope" risks. Reference ISO 27002 for guidance on Annex A.

## Requirements

ISO 27001 has 26 required activities (Clauses 4-10) and 17 required documentation artifacts.

### Required Activities
|Sub-Clause|Description|
|:-:|:-:|
|4.1|
|4.2|
|4.3|
|4.4|
|5.1|
|5.2|
|5.3|
|6.1.1|
|6.1.2|
|6.1.3|
|6.2|
|7.1|
|7.2|
|7.3|
|7.4|
|7.5|
|8.1|
|8.2|
|8.3|
|9.1|
|9.2|
|9.3|
|10.1|
|10.2|

### Required Documentation
|Sub-Clause|Description|
|:-:|:-:|
|4.3|
|5.2|
|6.1.2|
|6.1.3|
|6.2|
|7.2|
|7.5|
|8.1|
|8.2|
|8.3|
|9.1|
|9.2|
|9.3|
|10.2|

## ISO 27001 Revisions

Clauses 4-10 remained largely unchanged, with minor word changes and clarifications.

Annex A reduced from 114 controls down to 93. Also changed from 14 domains to 4 themes. 11 new controls were added to include threat intelligence, cloud information security, configuration management, and data masking. 

# Implementing the Management System
## Determining the Scope
Defining the ISMS scope is required under Clause 4.3

- Organization Context: Identify deparments requiring ISMS inclusion, exclude business unites irrelevant to ISMS goals, review critical outsourced services.
- Legal, Regulatory, and Contractual Obligations: Asses data types, meet customer expections for security assurance, include offices involved in regulatory compliance.

### Internal and External Stakeholders
Define internal stakeholders that are responsible for ISMS support and ownership (board of directors).

Identify external stakeholders, customers, regulators, 3rd party partners.

Determine critical data, physical, and service assets.

Enterprise-wide scopes are common for small/medium business but must be tailored for large organizations.

### Product Scope
Targets management system and how it supports specific products.

Requires explicit deprtments (IT, HR, Finance, Security) that support the ISMS operations.

Limits audit to specific offices, may include ciritical operations like headquarters and data processing facilities.

### Common Pitfalls

- Overly-General Scope: Wastes resources and confuses readers of the report.
- Overly-Narrow Scope: Leaves critical systems unaudited, risking dissatisfied stakeholders and unmitigated risks.
- Confusing Scope: Leads to internal confusion when reviewing scope, misdirected resources, and missed risks during audits.

## Executing the Risk Assessment


