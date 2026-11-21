# Month-1 report · Junior GRC Analyst
To: Priya Raman · From: Junior GRC Analyst · 21 Nov 2026 · Period: 26 Oct – 21 Nov (Weeks 1–4)

## Biggest concern
None of Northbridge's 17 obligations has verified evidence yet (0 Met; 4 Not met; 8 Unknown), while core care records in the PostgreSQL database and backups are unencrypted at rest (C-12; O-03). Ahead of Eastmere and March 2027 deadlines, leaving unencrypted Restricted data and unverified controls unresolved threatens commercial bids and customer assurance.

## Delivered
| Ticket | Deliverable | Closed | On time? |
| --- | --- | --- | --- |
| GRC-001 | Company profile, stakeholder map, 30-60-90 plan, open questions | Wed 4 Nov | No (due Sat 31 Oct) |
| GRC-002 | Asset inventory v1 (37 assets), AWS and GitHub discovery log | Thu 12 Nov | No (due Sat 7 Nov) |
| GRC-003 | Data inventory (13 types), data-flow map (13 flows), 5 data-flow worries | Fri 13 Nov | Yes |
| GRC-004 | ISMS scope v0.1, obligations register (17), this report | Sat 21 Nov | Yes |

## Found: top five concerns
1. CarePath's PostgreSQL database and backups are unencrypted at rest, and app-to-database TLS is unenforced (C-12; O-03).
2. No DPIA exists for carers' GPS check-in tracking, active since 2023 (C-13; O-06; Q3).
3. Written agency authorisation for sub-processors Zendesk and SignalPost cannot be shown (C-14; O-02).
4. CloudTrail and GuardDuty were off in AWS during discovery, and service-user names appear in logs (C-01; C-02; C-07).
5. 90-day post-exit deletion is unverified against contractual promises (C-11; O-08).

## Blocked / at risk
Independent verification depends on owners: Kwame's Intune report, Leo's AWS evidence, and Grace's council clause wording (O-09) and US health-privacy view (O-17). Scope v0.1 awaits your approval.

## Next month (Weeks 5–8)
Across GRC-005 to GRC-008, I will complete the Eastmere security questionnaire (GRC-005), build the formal risk register (GRC-006), assess the Rotamind supplier (GRC-007), and handle the AI note-taker policy exception (GRC-008). Decisions needed from you: confirm remediation priorities for C-12 and C-14, and back evidence collection.

## Numbers
- Tickets closed on time: 2 of 4
- Hours: GRC-001 22.0 · GRC-002 10.6 · GRC-003 5.6 · GRC-004 5.0 (time box 7 each)
- Assets inventoried: 37 · Data types: 13 · Data flows: 13 (encryption confirmed by owner on 6; verified on 0)
- Obligations: 17 (Met 0 · Partial 5 · Not met 4 · Unknown 8)
- Candidate risks for the GRC-006 register: 14 (C-01 to C-14)