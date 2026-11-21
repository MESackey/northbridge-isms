# ISMS scope · Northbridge Health Ltd
Version 0.1 (draft) · 20 Nov 2026 · Author: Junior GRC Analyst · Approver: Priya Raman (Head of Security and Compliance)
Sources: onboarding pack; [asset inventory](../01-company/asset-inventory.csv); [data-flow map](../01-company/data-flow-care-record.md); scope guidance from Priya (19 Nov)

## Scope statement
The ISMS covers the CarePath service—including the CarePath platform, carer mobile app, family portal, and supporting infrastructure in AWS London (eu-west-2)—together with the people, processes, locations (London HQ and Southampton support centre), and suppliers that support it. Care agency user accounts and authentication within CarePath are included, while agencies' own local devices and networks remain outside Northbridge's control.

## In scope
| Area | What's included | Asset IDs |
| --- | --- | --- |
| Service | CarePath scheduling, eMAR, carer mobile app, family portal, invoicing, and support operations (including the US pilot running on the London platform) | A-008, A-009, A-010, A-028, A-029 |
| Customers covered | 210 care agencies, 6 local authorities, 2 NHS community trusts (pilot), and 1 US home-health group (pilot) | — |
| Locations | London HQ (Old Street) and Southampton support centre (supporting AWS London eu-west-2 hosting) | A-034, A-035 |
| People | Platform engineering team and operational/support staff supporting CarePath and its security/compliance governance | A-037 |
| Technology | CarePath application, mobile/web front-ends, AWS London hosting/storage/logging/IAM/unlisted resources, GitHub and CI tooling, Microsoft 365/Entra/Intune, Slack, Jira, Zendesk, SignalPost, and staff laptops | A-008 to A-029, A-033 |
| Information | Service user care records, DBS certificate scans, GPS check-in and visit records, family portal data, council invoices, and credentials/keys (excluding HR records and sales CRM data) | A-001 to A-005, A-036 |

## Out of scope
| Excluded | Reason | What this leaves uncovered |
| --- | --- | --- |
| Corporate tools not used for care data: HubSpot (A-030), Xero (A-031), BreatheHR (A-032) | Confirmed by Priya (19 Nov): these systems do not hold care data for this certification round; they remain in the asset inventory and are subject to company policies | Security or availability incidents in HubSpot, Xero, or BreatheHR (including special-category HR data in A-006/A-032 or sales contacts in A-007/A-030) are outside this ISMS scope boundary |
| Care agencies' own devices and networks | Confirmed by Grace (16 Nov): agencies are data controllers responsible for their own local IT and networks, though their CarePath accounts and logins remain in scope | Compromise or malware on an agency's local workstation or network could expose care data viewed or entered by agency staff |
| Staff personal devices, apart from work email in the Outlook app | Confirmed by Kwame (16 Nov): Outlook uses Intune app protection (PIN, no copy-paste to other apps), and personal devices cannot access AWS production | Personal devices used outside managed controls could still face general consumer device threats, though no direct AWS production access is permitted |

## Interfaces and dependencies
| Dependency | Type | What crosses the boundary | How it's controlled today |
| --- | --- | --- | --- |
| AWS | Supplier (hosting) | CarePath application runtime, PostgreSQL database (unencrypted at rest), S3 document store (default encryption), unencrypted backups/snapshots, CloudWatch logs with service-user names, and IAM/unlisted resources (A-017, A-018, A-020) | Hosted in `eu-west-2`; TLS 1.2+ at load balancer; CloudTrail and GuardDuty not active during discovery; app-to-DB TLS not enforced; DB/backups unencrypted (C-12) |
| Zendesk | Sub-processor | Support tickets and care-plan screenshots attached by agencies (D-06) | Assumed HTTPS in transit; no supplier security assessment completed yet; agency sub-processor authorisation not confirmed on file (C-14) |
| SignalPost | Sub-processor | Reminder details (first name, mobile number, visit time; D-07) and outbound SMS reminder texts | Assumed HTTPS to SignalPost; SMS texts sent unencrypted over cellular networks (C-09); no supplier security assessment yet; agency authorisation not confirmed (C-14) |
| GitHub | Supplier (code and pipelines) | Source code, CI/CD workflows, Terraform/Trivy/Checkov configurations, and deployment pipelines (A-021, A-022) | Managed by Platform Engineering Lead and engineering team; formal pipeline security audit/verification status to be confirmed |
| Microsoft 365 | Supplier (email, identity, devices) | Staff emails/files (may include personal data), Entra ID identities/MFA, and Intune device management (A-023 to A-025) | Managed by IT Manager; Intune enforces BitLocker on laptops (confirmed by owner, report requested) and Outlook app protection on personal phones | 
| Slack; Atlassian (Jira) | Suppliers (chat and ticketing) | Staff messages and IT and security tickets, which may include personal data (A-026, A-027) | Managed by IT Manager; no supplier assessment yet |
| Care agencies (210) | Customers and controllers | Care plans, health/medication records, safeguarding notes, DBS scans, and support screenshots entered/uploaded into CarePath or Zendesk | Agencies act as controllers; CarePath access/login controls apply, while agency sub-processor authorisation for Zendesk/SignalPost lacks documented proof (C-14) |
| Local authorities (6) | Customers | Council invoices referencing service users and care hours (D-11) | Invoices generated in CarePath; export to Excel on staff laptops carries endpoint/retention risk (C-10) |
| NHS community trusts (2) | Customers (pilot) | Care service data processed on CarePath in London | Governed under CarePath service scope; pilot-specific compliance/DSPT alignment tracked alongside obligations |
| US home-health group (1) | Customer (pilot) | Home-health operational/care data running on the same CarePath platform in AWS London (`eu-west-2`) | Included in scope on Priya's instruction (runs on the London platform); cross-border/US data governance details to be verified |

## Why this scope
This scope is defined to support Northbridge's board target of ISO 27001 certification, meet customer and NHS pilot expectations (including Data Security and Protection Toolkit alignment at Standards Met), and satisfy the Eastmere tender requirements (ISO 27001 certification or credible plan, Cyber Essentials Plus, DSPT Standards Met, maintained risk register, named DPO, and 24-hour incident notice).