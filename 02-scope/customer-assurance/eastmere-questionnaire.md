# Eastmere supplier security questionnaire · Draft v0.1
Prepared by: Junior GRC Analyst · Review: Sofia Brennan (wording), Grace Whitfield (Q3, Q9) · Sign-off: Priya Raman
Council data means: service users' care records, visit logs and GPS, agency staff details including DBS scans (criminal offence data), and council invoices. All Restricted. (Grace, 23 Nov)
The Evidence and Gap action lines are internal. They are removed before this goes to Eastmere.

## Summary
| Q | Topic | Confidence |
| --- | --- | --- |
| 1 | ISO 27001 | Gap |
| 2 | Cyber Essentials Plus | Confirmed |
| 3 | UK data location | Partial |
| 4 | MFA | |
| 5 | Encryption | Partial |
| 6 | Penetration testing | Gap |
| 7 | Risk register | Gap |
| 8 | Incident response | Partial |
| 9 | Sub-processors | Partial |
| 10 | Training and vetting | |
| 11 | Leavers | |
| 12 | BC/DR testing | |
| 13 | DSPT | Confirmed |
| 14 | Patching | |
| 15 | AI tools | |

## Answers

### Q1 · Do you hold ISO 27001 certification?
**Answer:** No, not yet. We are building an information security management system aligned to ISO 27001. Its scope was approved on 21 November 2026, and our board's target is certification by Q3 2027. In the meantime we hold Cyber Essentials Plus and DSPT Standards Met (see Q2 and Q13).
**Evidence:** company-profile.md (board target Q3 2027); isms-scope.md v1.0 (approved 21 Nov 2026); Priya, 23 Nov (no certificate).
**Confidence:** Gap
**Gap action:** Now: ISMS scope approved. Next: risk register rebuilt (GRC-006, Dec 2026). Owner: Priya Raman. Target: certification Q3 2027 (board target, no audit booked yet).

### Q2 · Do you hold Cyber Essentials Plus?
**Answer:** Yes. We have been certified to Cyber Essentials Plus since March 2026. A copy of the certificate is available on request.
**Evidence:** CE+ certificate issued 12 Mar 2026, seen 23 Nov 2026 (Priya, shared drive).
**Confidence:** Confirmed
**Note (internal):** it expires around 12 Mar 2027, the same month as the Eastmere re-tender. Renewal needs to be booked early.

### Q3 · Where is council data stored and processed geographically?
**Answer:** Our CarePath core platform—including the US pilot environment—is hosted in AWS London (`eu-west-2`), with backups kept in London. Some support and messaging workflows involve third-party suppliers (Zendesk and SignalPost) whose exact storage regions have not yet been verified, and council invoice exports may be generated on UK staff laptops.
**Evidence:** data-flow-care-record.md; open-questions.md Q1 (Priya, 23 Nov: US pilot on London platform); Zendesk and SignalPost storage locations not yet confirmed.
**Confidence:** Partial
**Gap action:** Grace Whitfield to review Q3 before Sofia sees the draft; verify Zendesk and SignalPost storage locations during supplier reviews.

### Q4 · Do you enforce multi-factor authentication (MFA)?
**Answer:**
**Evidence:**
**Confidence:**
**Gap action:**

### Q5 · How is council data encrypted at rest and in transit?
**Answer:** In transit, public connections to CarePath use TLS 1.2 or higher at the load balancer, while SMS reminder texts are sent unencrypted over cellular networks and internal application-to-database TLS is not currently enforced. At rest, S3 object storage uses default encryption, whereas our legacy production PostgreSQL database and its backups/snapshots are not encrypted at rest, and we are planning remediation.
**Evidence:** data-flow-care-record.md (flows F1–F13); Leo Park, 23 Nov (owner-confirmed, not yet verified).
**Confidence:** Partial
**Gap action:** Priority remediation for unencrypted database and backups (C-12, owned by Priya/Leo); verify production configurations and enforce internal TLS.

### Q6 · Do you carry out independent penetration testing at least annually?
**Answer:** Our most recent independent penetration test by a CREST-accredited firm took place on 14 February 2025, which is more than 12 months ago. That test identified no critical findings, two high-severity findings (both resolved by April 2025), and six medium-severity findings (three remain open). A follow-up test has not yet been commissioned and is included in our Q1 2027 budget request.
**Evidence:** Priya Raman, 23 Nov (CREST report dated 14 Feb 2025; highs fixed Apr 2025; 3 mediums open; no 2026 test commissioned; Q1 2027 budget request).
**Confidence:** Gap
**Gap action:** Commission an independent penetration test and close remaining medium findings; owner: Priya Raman / leadership budget approval (Q1 2027 target).

### Q7 · Do you maintain a formal information security risk register?
**Answer:** We do not yet have a formally maintained risk register in place, though we have compiled candidate risks from our discovery and data-flow reviews and are scheduled to establish the formal risk register in early December 2026.
**Evidence:** company-profile.md (2024 spreadsheet baseline); obligations-register.csv (O-14 Partial); candidate-risks.md (C-01 to C-14); GRC-006 due 5 Dec 2026.
**Confidence:** Gap
**Gap action:** Establish and populate the formal risk register in GRC-006 (due 5 Dec 2026); owner: Priya Raman / Junior GRC Analyst.

### Q8 · How do you manage security incidents and breach notifications?
**Answer:** We have an incident response plan at draft version 0.3, which has not yet been formally tested. Where customer contracts require notification within 24 hours of an incident affecting council data, we do not yet have a verified procedure and contact list in place to confirm that timeline.
**Evidence:** Priya Raman facts (IR plan v0.3, untested); obligations-register.csv (O-04 and O-09 Unknown).
**Confidence:** Partial
**Gap action:** Finalize and test the incident response plan and establish a verified 24-hour council notification procedure; owner: Head of Legal and DPO / Head of Security and Compliance.

### Q9 · Which third-party sub-processors handle council data, and how are they controlled?
**Answer:** Third-party suppliers supporting CarePath workflows include AWS (hosting), Zendesk (support tickets, where care-plan screenshots may be attached), and SignalPost (SMS reminder delivery). Formal supplier security assessments have not yet been completed for Zendesk and SignalPost, and we cannot currently demonstrate documented agency authorisation for their use as sub-processors.
**Evidence:** data-flow-care-record.md (F8–F10); data-inventory.csv (D-06, D-07); obligations-register.csv (O-02 Not met); Grace Whitfield, 16 Nov & 23 Nov (C-14).
**Confidence:** Partial
**Gap action:** Grace Whitfield to review Q9 before Sofia sees the draft; obtain documented agency sub-processor authorisations (C-14) and complete supplier security assessments (GRC-007+).

### Q10 · What staff security training and pre-employment vetting do you carry out?
**Answer:**
**Evidence:**
**Confidence:**
**Gap action:**

### Q11 · How quickly is access revoked when staff or users leave?
**Answer:**
**Evidence:**
**Confidence:**
**Gap action:**

### Q12 · Do you test business continuity and disaster recovery plans?
**Answer:**
**Evidence:**
**Confidence:**
**Gap action:**

### Q13 · Do you hold NHS Data Security and Protection Toolkit (DSPT) compliance?
**Answer:** Yes. Our published DSPT status for 2025–26 is Standards Met, published on 26 June 2026.
**Evidence:** Priya Raman, 23 Nov (public DSPT status 2025–26, Standards Met, published 26 Jun 2026).
**Confidence:** Confirmed

### Q14 · What are your patch timescales for systems and vulnerabilities?
**Answer:**
**Evidence:**
**Confidence:**
**Gap action:**

### Q15 · How do you govern the use of AI tools?
**Answer:**
**Evidence:**
**Confidence:**
**Gap action:**