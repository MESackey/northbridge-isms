# Job description market check

Each duty in `job-description.md` was checked against the four entry-level ads in `ads/` (ads 3, 4, 6, 9).
Marks: ✓ the ad lists it as a duty · ~ mentioned only as a skill, learning area or narrower version · — not mentioned.
A duty is market-backed if at least 2 of the 4 ads give it a ✓. Checked 29 Oct 2026.

| # | JD duty | Ad 3 Pay.UK | Ad 4 Smart Comms | Ad 6 Picture More | Ad 9 KPMG | ✓ count | Market-backed? |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Asset and data inventories, data flows | — | — | — | — | 0 | No |
| 2 | ISMS scope and obligations | — | — | ✓ | — | 1 | No |
| 3 | Customer security questionnaires | — | ✓ | ✓ | — | 2 | Yes |
| 4 | Risk register | ✓ | ✓ | ~ | ~ | 2 | Yes |
| 5 | Supplier assurance | ✓ | ✓ | ~ | — | 2 | Yes |
| 6 | Policy exceptions, contract clauses | — | ✓ | ~ | — | 1 | No |
| 7 | Control tests and audit evidence | ✓ | ✓ | ✓ | ✓ | 4 | Yes |
| 8 | Awareness and phishing | — | — | ✓ | — | 1 | No |
| 9 | Incident paperwork | — | — | — | — | 0 | No |
| 10 | Reports to management | ✓ | ✓ | ✓ | — | 3 | Yes |

## Evidence quotes

### Ad 6 · Picture More
- Duty 2: "Assisting with the ongoing maintenance of the Information Security Management System (ISMS)"
- Duty 3: "Completing client security questionnaires and due diligence requests"
- Duty 4 (~): "Some exposure to ... risk assessments ... would be advantageous"
- Duty 5 (~): "developing your knowledge across ... supplier assurance"
- Duty 6 (~): "maintenance of information security policies, standards and documentation"
- Duty 7: "Supporting ISO 27001 certification, surveillance and internal audit activities"
- Duty 8: "Supporting security awareness and training initiatives across the business"
- Duty 10: "Helping prepare security metrics, dashboards and management information"

### Ad 3 · Pay.UK
- Duty 4: “Maintain accurate supplier and risk data ... provide first line support to suppliers.”
- Duty 5: "Issue, manage and assess Third Party Assurance Questionnaires ... and business continuity."
- Duty 7: “Evaluate supplier responses and evidence to assess control design and effectiveness.”
- Duty 10: “Prepare regular functional risk reports ... to support informed decisions.” 

### Ad 4 · Smart Communications
- Duty 3: “Completing security questionnaires and requests for proposals (RFPs)”
- Duty 4: "Supporting risk assessments and security audits under guidance from senior team members"
- Duty 5: “Supporting the 3rd party security risk mgt process by reviewing vendor security measures.”
- Duty 6: “... ensuring security requirements are considered in contracts.”
- Duty 7: “Assisting internal audits to check compliance ... tracking corrective actions”
- Duty 10: “Preparing reports on operations, security and compliance status across the business”

### Ad 9 · KPMG
  - Duty 4 (~): "... review business applications ... and cyber security risks"
  - Duty 7: "You could assess controls ..."

## Duties the ads ask for that the JD doesn't have
- “Monitor the supplier threat landscape using external intelligence and data sources.”
- “Assisting in projects and supplier/customer onboarding.”
- “You will work alongside colleagues in Financial audit ... organisation’s key financial processes.” (specific to audit firms; not relevant to an in-house role)

## Conclusion
Five of the ten duties are market-backed (3, 4, 5, 7, 10): questionnaires, risk register, supplier assurance, audit evidence and reporting. The other five stay because Northbridge needs them:

- **Duty 1 (inventories):** ISO 27001 control A.5.9 requires an asset inventory, and Northbridge has none.
- **Duty 2 (scope):** ISO 27001 clause 4.3 requires a defined scope before certification, and Northbridge is aiming for certification in 2027.
- **Duty 6 (exceptions and contracts):** ISO 27001 control A.5.20 requires security terms in supplier contracts, and Northbridge relies on suppliers that handle care data (AWS, SignalPost, Zendesk). Policy exceptions must be recorded and approved so leadership knows which risks it has accepted. 
- **Duty 8 (awareness):** Cyber Essentials Plus and the NHS DSPT both expect staff security training.
- **Duty 9 (incidents):** council contracts require incident notice within 24 hours, UK GDPR requires a processor to tell its customers about breaches without delay, and ISO 27001 controls A.5.24 to A.5.28 require incidents to be managed and recorded.