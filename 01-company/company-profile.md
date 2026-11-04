# Company profile: Northbridge Health Ltd
As of 3 Nov 2026 · Author: Junior GRC Analyst · Sources: onboarding pack, open-questions.md

## What we do
Northbridge makes CarePath, a cloud platform for home care and community health providers. Agencies use it to schedule carers' visits, keep care plans and electronic medication records (eMAR), and invoice councils.    Carers' mobile app records their location at check-in, and families follow care through a family portal.

## Who we serve
- 210 home care agencies, 6 local authorities and 2 NHS community trusts (pilot)
- 1 US home-health group (pilot since September 2026)
- About 41,000 service users, 9,800 carers using the app and 5,000 family portal users

## What data we hold, and where
- Care plans, health needs, medication records and safeguarding notes for about 41,000 service users (special category health data): in CarePath, hosted on AWS in London.
- Copies of carers' DBS certificates uploaded by agencies (criminal offence data): location not stated in the pack (open question).
- Carers' names, contact details, GPS location at check-in and visit times (location marked high-risk): in CarePath.
- Family portal accounts and messages: in CarePath.
- Invoices to councils that refer to service users: in CarePath.
- Staff HR records: BreatheHR. Customer contacts and deal notes: HubSpot.

For care data we are mostly a **processor**: the agencies decide how their service users' data is used (they are the controllers). We are the controller for our own staff and customer-contact data.

## Who we answer to
- **UK GDPR (enforced by the ICO):** as a processor, we must keep data secure and tell the agencies about a breach without undue delay.
- **Council contracts:** we must tell a council within 24 hours of any incident affecting its data.
- **NHS Data Security and Protection Toolkit (DSPT):** a yearly self-assessment we must pass to keep the NHS pilots.
- **Cyber Essentials Plus:** required by council contracts; renewal due March 2027.
- **ISO 27001:** the board's target is certification by Q3 2027.
- **DCB0129:** the NHS standard for managing clinical safety risk in health software, owned by Hannah Cole (Clinical Safety Officer).
- **SOC 2:** the US pilot customer has asked for a Type I report in 2027.

## Crown jewels
1. **CarePath database (AWS):** if stolen, 41,000 service users' health records are exposed; if down, care stops across 210 agencies (Severe).
2. **Visit scheduling and eMAR:** if down, carers miss visits and service users could miss medication (Severe).
3. **Carers' GPS check-in records:** if stolen, they show where about 9,800 carers are and when (Major).

## Top five worries
1. We could lose the Eastmere re-tender in March 2027: it needs a maintained risk register, and ours is a 2024 spreadsheet with 9 risks and no owners.
2. Systems added for the US pilot may hold care data that nobody has checked for security.
3. We track carers' locations but may never have assessed the privacy risk.
4. We may be breaking the stricter rules for criminal offence data (carers' DBS copies) without knowing.
5. Our Data Protection Officer is also Head of Legal, so nobody independent checks our privacy decisions. 

Questions I couldn't answer yet: see [open-questions.md](open-questions.md)  