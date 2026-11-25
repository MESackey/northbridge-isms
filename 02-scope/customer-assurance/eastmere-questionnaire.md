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
| 5 | Encryption | Gap |
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

### Q3 · Is all council data stored and processed in the UK?
**Answer:** No, not all. Our CarePath core platform and backups are hosted in AWS London (`eu-west-2`) in the UK, and council invoice exports may be generated on UK staff laptops. However, our Zendesk account is hosted in the EU (Ireland and Germany—lawful under UK adequacy for the EU, but outside the UK), and SignalPost is a UK company whose message log storage location has not yet been confirmed.
**Evidence:** data-flow-care-record.md; Grace Whitfield, 23 Nov (Zendesk EU hosting in Ireland and Germany; SignalPost message log location asked/unconfirmed).
**Confidence:** Partial
**Gap action:** Confirm SignalPost message log storage location and document UK/EU data residency details. Owner: Grace Whitfield. By: date not yet agreed (asked Grace Whitfield, 23 Nov).

### Q4 · Is MFA enforced for all staff and all administrative access?
**Answer:**
**Evidence:**
**Confidence:**
**Gap action:**

### Q5 · Is council data encrypted at rest and in transit?
**Answer:** Partly. In transit: connections from the internet to CarePath use TLS 1.2. Traffic between our load balancer and our application servers, inside our private AWS network, is not yet encrypted. SMS appointment reminders are standard text messages, which are not encrypted. At rest: documents in our file storage are encrypted, but our main database and its backups are not yet encrypted. This has been escalated to our leadership, and a remediation date is being agreed.
**Evidence:** Leo Park, 23 Nov (owner-confirmed, not verified); data-flow-care-record.md F3, F4, F10, F13; C-12.
**Confidence:** Gap
**Gap action:** Now: S3 encrypted; internet traffic on TLS 1.2. Next: encrypt the database and backups (C-12; about 2 hours of downtime, Leo 17 Nov); encrypt load balancer to app traffic. Owner: David Lin (decision), Leo Park (delivery). By: date not yet agreed (Priya raising C-12 with David, 23 Nov).

### Q6 · Do you commission an independent penetration test at least annually?
**Answer:** No. Our most recent independent penetration test by a CREST-accredited firm took place on 14 February 2025, which is more than 12 months ago. That test identified no critical findings, two high-severity findings (both resolved by April 2025), and six medium-severity findings (three remain open). A follow-up test has not yet been commissioned and is included in our Q1 2027 budget request.
**Evidence:** Priya Raman, 23 Nov (CREST report dated 14 Feb 2025; highs fixed Apr 2025; 3 mediums open; no 2026 test commissioned; Q1 2027 budget request).
**Confidence:** Gap
**Gap action:** Commission an independent penetration test and close remaining medium findings; Owner: Priya Raman. By: date not yet agreed (test in David's Q1 2027 budget request).

### Q7 · Do you maintain a risk register reviewed at least quarterly?
**Answer:** Not yet. We do not currently maintain a risk register reviewed at least quarterly, and no quarterly review cadence has been agreed yet. We have compiled candidate risks from our discovery and data-flow reviews and are scheduled to rebuild the formal risk register by 5 December 2026.
**Evidence:** company-profile.md (2024 spreadsheet baseline); obligations-register.csv (O-14 Partial); candidate-risks.md (C-01 to C-14); GRC-006 due 5 Dec 2026.
**Confidence:** Gap
**Gap action:** Establish the formal risk register in GRC-006 (by 5 Dec 2026) and agree a formal review cadence. Owner: Priya Raman. By: 5 Dec 2026 for register launch; quarterly review date not yet agreed (asked Priya Raman, 23 Nov).

### Q8 · Describe your incident response process and your notification timescale to the council.
**Answer:** Partly. We have an incident response plan at draft version 0.3, which has not yet been reviewed in full or formally tested, and we do not yet have a verified procedure and contact list in place to confirm a 24-hour notification timeline to the council.
**Evidence:** Priya Raman facts (IR plan v0.3, untested); obligations-register.csv (O-04 and O-09 Unknown).
**Confidence:** Partial
**Gap action:** Review IR plan v0.3 and establish/verify the incident response and 24-hour council notification procedure. Owner: Priya Raman (IR plan) and Grace Whitfield (24-hour council notice, O-09). By: date not yet agreed (requested IR plan v0.3 from Priya Raman, 23 Nov; council clause/procedure with Grace Whitfield).

### Q9 · List every sub-processor that can access council data.
**Answer:** Our sub-processors are: AWS (hosting and storage—CarePath application, database, and file storage in London eu-west-2); Zendesk (customer support ticketing—support tickets and attached care-plan screenshots; account hosted in the EU in Ireland and Germany); and SignalPost (SMS appointment reminders—service-user first name, mobile number, and visit time; UK company with message log storage location unconfirmed). We cannot currently show documented agency authorisation for Zendesk and SignalPost as sub-processors, and our DPO will send agencies a sub-processor notice by Friday 4 December 2026.

### Q10 · Are all staff trained in security annually, and vetted before access?
**Answer:**
**Evidence:**
**Confidence:**
**Gap action:**

### Q11 · How quickly is access removed when staff leave?
**Answer:**
**Evidence:**
**Confidence:**
**Gap action:**

### Q12 · Is your business continuity and disaster recovery plan tested at least annually?
**Answer:**
**Evidence:**
**Confidence:**
**Gap action:**

### Q13 · Do you hold a current DSPT assessment at Standards Met?
**Answer:** Yes. Our published DSPT status for 2025–26 is Standards Met, published on 26 June 2026.
**Evidence:** Priya Raman, 23 Nov (public DSPT status 2025–26, Standards Met, published 26 Jun 2026).
**Confidence:** Confirmed

### Q14 · Are critical and high-risk security patches applied within 14 days?
**Answer:**
**Evidence:**
**Confidence:**
**Gap action:**

### Q15 · Do you use AI tools to process council data?
**Answer:**
**Evidence:**
**Confidence:**
**Gap action:**