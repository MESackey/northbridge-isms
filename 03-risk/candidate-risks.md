# Candidate risks (for the GRC-006 register)

Listed during GRC-002 (12 Nov 2026); C-15 onwards added during GRC-005 (Eastmere questionnaire).

| # | Candidate risk | Found in | Asset IDs |
| --- | --- | --- | --- |
| C-01 | No CloudTrail trail, so activity in AWS can't be investigated after an incident | GRC-002 discovery D5 | A-015 |
| C-02 | GuardDuty is off, so attacks on the AWS account may go unnoticed | GRC-002 discovery D6 | A-016 |
| C-03 | Resources created outside Terraform with no owner, so nobody secures or removes them | GRC-002 discovery D1, D2 | A-017, A-018 |
| C-04 | An unused IAM user remains in the AWS account | GRC-002 discovery D3 | A-020 |
| C-05 | Production assets in the systems list can't be verified, so the inventory may be incomplete | GRC-002 discovery D9 | A-012, A-013, A-014 |
| C-06 | Nobody knows where carers' DBS copies are stored (Leo says S3, 13 Nov; not verified) | GRC-001 Q2; GRC-002 inventory | A-002 |
| C-07 | Service-user names in application logs, readable by anyone with log access | GRC-003 W1 (flow F5) | Data D-05 |
| C-08 | Care-plan screenshots stored in Zendesk outside core AWS boundaries | GRC-003 W2 (flow F8) | Data D-06 |
| C-09 | Unencrypted reminder texts sending visit details and names by SMS | GRC-003 W3 (flows F9/F10) | Data D-07 |
| C-10 | Restricted invoice reports exported and stored on staff laptops | GRC-003 W4 (flow F11) | Data D-08 |
| C-11 | 90-day deletion after a customer leaves is promised but never checked | GRC-003 W5 (flow F12) | Data D-01 |
| C-12 | Production PostgreSQL database and its backups/snapshots are not encrypted at rest (created in 2021; ~2 hours downtime to restore from an encrypted copy) | GRC-004 Inbox (Leo, 17 Nov) ; database "Encryption: Not enabled" verified 25 Nov (Leo RDS screenshot; backups/snapshots remain owner-confirmed unencrypted) | Data D-01, D-04 |
| C-13 | No Data Protection Impact Assessment (DPIA) exists for carers' GPS check-in tracking (live since 2023; required under ICO guidance for location tracking) | GRC-004 Inbox (Grace, 16 Nov; answers Q3) | Data D-09 |
| C-14 | Cannot demonstrate that care agencies (controllers) authorised Zendesk and SignalPost as sub-processors under UK GDPR Article 28 | GRC-004 Inbox (Grace, 16 Nov) | Data D-06, D-07 |
| C-15 | No independent penetration test since 14 Feb 2025, and 3 medium findings from it are still open, so new weaknesses in CarePath may be unknown | GRC-005 Q6 (Priya, 23 Nov) | A-008, A-012 |
| C-16 | Legacy IAM deployment user `ci-deploy` relies on long-lived access keys over a year old without key rotation or MFA, so compromised credentials could expose production AWS resources | GRC-005 Q4 (Leo, 23 Nov) | A-011, A-036 |
| C-17 | Internal HTTP traffic between the AWS load balancer and CarePath application containers is unencrypted inside the VPC, so sensitive care data in transit could be intercepted if internal network boundaries are breached | GRC-005 Q5 (Leo, 23 Nov) | A-008, A-012 |
| C-18 | Incident response plan v0.3 has never been tested and lacks a defined 24-hour council notification procedure or contact list, so breach reporting deadlines could be missed during a live incident | GRC-005 Q8 (Priya, 24 Nov) | A-008 |
| C-19 | No annual staff security refresher training has been delivered since 2024, so staff awareness of phishing and data-handling obligations may degrade over time | GRC-005 Q10 (Kwame, 24 Nov) | A-008, A-023 |
| C-20 | Engineers with production access do not undergo pre-employment DBS checks, so unvetted personnel could access systems holding criminal offence and health data | GRC-005 Q10 (Kwame, 24 Nov) | A-001, A-002, A-037 |
| C-21 | Leaver access revocation outside Microsoft 365 relies on informal Slack messages without a checklist or timestamped audit log, so former staff could retain access to AWS or third-party systems | GRC-005 Q11 (Kwame, 24 Nov) | A-011, A-023, A-024 |
| C-22 | No business continuity plan or written disaster recovery plan exists, no planned restore test has been run, and production runs in a single AWS region without failover, so an outage could cause prolonged CarePath unavailability | GRC-005 Q12 (Leo & Priya, 24 Nov) | A-008, A-011, A-013 |
| C-23 | 4 of 11 critical/high container vulnerabilities over the last 90 days took 21–45 days to remediate and no formal patch SLA exists, so exploitable vulnerabilities may remain exposed beyond 14 days | GRC-005 Q14 (Tom, 24 Nov; Leo, 23 Nov) | A-012, A-022 |
| C-24 | Staff use free ChatGPT on Customer Success laptops to rewrite agency emails without an AI policy or technical controls, so Restricted council or care data could be disclosed to an unapproved external AI service | GRC-005 Q15 (Kwame, 24 Nov) | A-025, A-033 |