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
| 4 | MFA | Partial |
| 5 | Encryption | Gap |
| 6 | Penetration testing | Gap |
| 7 | Risk register | Gap |
| 8 | Incident response | Partial |
| 9 | Sub-processors | Partial |
| 10 | Training and vetting | Gap |
| 11 | Leavers | Gap |
| 12 | BC/DR testing | Gap |
| 13 | DSPT | Confirmed |
| 14 | Patching | Partial |
| 15 | AI tools | Gap |

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
**Answer:** Partly. All staff Microsoft 365 accounts are covered by a Conditional Access policy requiring MFA, except a documented break-glass admin account (stored in the office safe) and a printer scan-to-email account (`scan-sthn`). For production AWS administrative access, engineers authenticate via IAM Identity Center with MFA enforced and root uses a hardware key, though one legacy deployment IAM user (`ci-deploy`) uses long-lived access keys over a year old without console MFA.
**Evidence:** Kwame Boateng, 24 Nov (Entra MFA registration export seen 24 Nov); Leo Park, 23 Nov (production MFA and `ci-deploy` key age owner-confirmed, not verified).
**Confidence:** Partial
**Gap action:** Review and retire/rotate the legacy `ci-deploy` access key, verify production MFA configurations, and document formal sign-off for break-glass/service account exceptions. Owner: Leo Park (AWS) and Kwame Boateng (Microsoft 365). By: date not yet agreed (asked Leo Park and Kwame Boateng, 24 Nov).

### Q5 · Is council data encrypted at rest and in transit?
**Answer:** Partly. In transit: connections from the internet to CarePath use TLS 1.2. Traffic between our load balancer and our application servers, inside our private AWS network, is not yet encrypted. SMS appointment reminders are standard text messages, which are not encrypted. At rest: documents in our file storage are encrypted, but our main database and its backups are not yet encrypted. Leadership has agreed to encrypt the database and backups, with a target before 31 December 2026.
**Evidence:** Leo Park, 23 Nov (owner-confirmed, not verified); Priya Raman, 24 Nov (CTO agreed database and backup encryption target before 31 Dec 2026); data-flow-care-record.md F3, F4, F10, F13; C-12.
**Confidence:** Gap
**Gap action:** Encrypt production database and backups (C-12; ~2 hours downtime) and address unencrypted internal load-balancer-to-app and SMS reminder paths. Owner: David Lin (decision) and Leo Park (delivery). By: before 31 Dec 2026 for database/backup encryption target; load-balancer-to-app date not yet agreed (asked Leo Park, 23 Nov).

### Q6 · Do you commission an independent penetration test at least annually?
**Answer:** No. Our most recent independent penetration test by a CREST-accredited firm took place on 14 February 2025, which is more than 12 months ago. That test identified no critical findings, two high-severity findings (both resolved by April 2025), and six medium-severity findings (three remain open). A follow-up test has not yet been commissioned and is included in our Q1 2027 budget request.
**Evidence:** Priya Raman, 23 Nov (CREST report dated 14 Feb 2025; highs fixed Apr 2025; 3 mediums open; no 2026 test commissioned; Q1 2027 budget request).
**Confidence:** Gap
**Gap action:** Commission an independent penetration test and close remaining medium findings. Owner: Priya Raman. By: date not yet agreed (test in David's Q1 2027 budget request).

### Q7 · Do you maintain a risk register reviewed at least quarterly?
**Answer:** Not yet. We do not currently maintain a risk register reviewed at least quarterly, though we have compiled candidate risks from our discovery and data-flow reviews and are scheduled to establish the formal risk register by 5 December 2026. Our security steering group will review the register quarterly starting in January 2027.
**Evidence:** company-profile.md (2024 spreadsheet baseline); obligations-register.csv (O-14 Partial); candidate-risks.md (C-01 to C-14); Priya Raman, 24 Nov (quarterly steering group review from Jan 2027); GRC-006 due 5 Dec 2026.
**Confidence:** Gap
**Gap action:** Launch the formal risk register and initiate quarterly steering group reviews. Owner: Priya Raman. By: 5 Dec 2026 for register launch; first quarterly review Jan 2027.

### Q8 · Describe your incident response process and your notification timescale to the council.
**Answer:** Partly. We have an incident response plan at draft version 0.3 defining roles (incident lead, technical lead, and DPO/notification decision role), three severity levels, and six stages (detect, contain, assess, notify, recover, review), though the plan has not yet been tested. The current draft states notification "as soon as practicable" with no fixed timescale or council contact list, whereas we can commit to 24-hour notice in the contract once wording is confirmed.
**Evidence:** Priya Raman, 24 Nov (IR plan v0.3 structure, untested, "as soon as practicable" wording, 24-hour contract commitment); obligations-register.csv (O-04 and O-09 Unknown).
**Confidence:** Partial
**Gap action:** Confirm council 24-hour notification clause wording, build the council contact list, and test IR plan v0.3. Owner: Grace Whitfield (notification clause/contacts) and Priya Raman (IR plan testing). By: date not yet agreed (asked Grace Whitfield and Priya Raman, 23–24 Nov).

### Q9 · List every sub-processor that can access council data.
**Answer:** Our sub-processors are:
- AWS (hosting and storage—CarePath application, database, and file storage in London `eu-west-2`).
- Zendesk (customer support ticketing—support tickets and attached care-plan screenshots; account hosted in the EU in Ireland and Germany).
- SignalPost (SMS appointment reminders—service-user first name, mobile number, and visit time; UK company with message log storage location unconfirmed).
We cannot currently show documented agency authorisation for Zendesk and SignalPost as sub-processors, and our DPO will send agencies a sub-processor notice by Friday 4 December 2026.
**Evidence:** data-flow-care-record.md (F2–F10); data-inventory.csv (D-01 to D-09); obligations-register.csv (O-02 Not met); Grace Whitfield, 16 Nov (C-14) and 23 Nov (EU hosting; notice by 4 Dec).
**Confidence:** Partial
**Gap action:** Issue sub-processor notice to agencies and confirm documented sub-processor authorisations (C-14). Owner: Grace Whitfield. By: Fri 4 Dec 2026.

### Q10 · Are all staff trained in security annually, and vetted before access?
**Answer:** No. New starters complete an online security module in week one, but there has been no annual security refresher training since 2024. Pre-employment vetting includes references and right-to-work checks for all staff, while basic DBS checks are carried out only for support agents viewing care records and not for engineers with production access.
**Evidence:** Kwame Boateng, 24 Nov (owner-confirmed: week-one module, no annual refresher since 2024, vetting/DBS scope).
**Confidence:** Gap
**Gap action:** Restore annual security refresher training and review pre-employment vetting/DBS requirements across roles. Owner: Kwame Boateng and HR/leadership. By: date not yet agreed (asked Kwame Boateng, 24 Nov).

### Q11 · How quickly is access removed when staff leave?
**Answer:** Not yet fully evidenced across all systems. When HR logs a leaver in BreatheHR, Microsoft 365 accounts are typically disabled on the last day (usually by 17:00), but revocation in AWS and other applications relies on a Slack message to engineering without a formal checklist or timestamped removal record.
**Evidence:** Kwame Boateng, 24 Nov (owner-confirmed: M365 same-day disablement; Slack handoff to Leo for other systems with no checklist or removal log).
**Confidence:** Gap
**Gap action:** Implement a formal leaver access revocation checklist and audit log covering Microsoft 365, AWS, and third-party tools. Owner: Kwame Boateng and Leo Park. By: date not yet agreed (asked Kwame Boateng, 24 Nov).

### Q12 · Is your business continuity and disaster recovery plan tested at least annually?
**Answer:** No. We do not have a business continuity plan (planned on the ISO roadmap for Q2 2027) or a written disaster recovery plan, and we have never run a planned disaster recovery restore test (the only real restore was an unscheduled March 2025 staging debug restore taking about 3 hours, with single-region London hosting and no failover).
**Evidence:** Leo Park, 24 Nov (no written DR plan, no planned restore test, Mar 2025 staging restore ~3 hours, single-region London); Priya Raman, 24 Nov (no BCP; Q2 2027 roadmap).
**Confidence:** Gap
**Gap action:** Deliver business continuity plan by Q2 2027 (Priya Raman) and establish/test a formal disaster recovery plan. Owner: Priya Raman (BCP) and Leo Park (DR plan/testing). By: Q2 2027 for BCP; DR test date not yet agreed (asked Leo Park, 24 Nov).

### Q13 · Do you hold a current DSPT assessment at Standards Met?
**Answer:** Yes. Our published DSPT status for 2025–26 is Standards Met, published on 26 June 2026.
**Evidence:** Priya Raman, 23 Nov (public DSPT status 2025–26, Standards Met, published 26 Jun 2026).
**Confidence:** Confirmed

### Q14 · Are critical and high-risk security patches applied within 14 days?
**Answer:** No, not consistently. Weekly container image scanning over the last 90 days recorded 11 critical or high findings: 7 were resolved within 14 days, while 4 took 21–45 days due to base-image rebuild requirements (and no formal written patch timescale exists yet).
**Evidence:** Tom Adeyemi, 24 Nov (90-day container scan export seen 24 Nov: 7 of 11 fixed within 14 days, 4 took 21–45 days); Leo Park, 23 Nov (no written patch timescale).
**Confidence:** Partial
**Gap action:** Establish formal patch SLAs and streamline base-image updates so critical and high findings are resolved within 14 days. Owner: Tom Adeyemi and Leo Park. By: date not yet agreed (asked Tom Adeyemi and Leo Park, 24 Nov).

### Q15 · Do you use AI tools to process council data?
**Answer:** Not intentionally via approved company tooling, as CarePath has no AI features, no AI tools are licensed, and Microsoft Copilot is not enabled; however, free ChatGPT has been observed open on two Customer Success laptops for rewriting emails to agencies, and we have no AI policy restricting it.
**Evidence:** Kwame Boateng, 24 Nov (owner-confirmed: no licensed AI/Copilot, free ChatGPT seen on two Customer Success laptops, no AI policy); Grace Whitfield, 23 Nov (no AI in CarePath known).
**Confidence:** Gap
**Gap action:** Establish an AI acceptable-use policy and controls (including GRC-008 AI note-taker policy exception review) and verify whether any council data was entered into external AI tools. Owner: Kwame Boateng and Priya Raman. By: date not yet agreed (asked Kwame Boateng, 24 Nov; GRC-008 scheduled in Dec).