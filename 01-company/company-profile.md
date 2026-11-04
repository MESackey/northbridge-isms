# Company profile: Northbridge Health Ltd
As of 3 Nov 2026 · Author: Junior GRC Analyst · Sources: onboarding pack, open-questions.md

## What we do
Northbridge makes CarePath, a cloud platform for home care and community health providers. Agencies use it to schedule carers' visits, keep care plans and electronic medication records (eMAR), and invoice councils. Carers use a mobile app that records their location when they check in, and families follow care through a family portal.

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
1. CarePath primary cloud database (AWS): if it were down or stolen, 41,000 service users' health and medication records would be exposed or inaccessible, halting care delivery across providers.
2. Visit scheduling and eMAR system: if this service experienced an outage, carers could not track medication schedules or visit assignments, directly risking patient safety.
3. Carer GPS location and check-in records: if compromised or lost, sensitive location patterns of vulnerable care workers and clients would breach privacy obligations and regulatory trust. (about 9,800 carers: Major on our impact scale) 

## Top five worries
1. We need an accurate risk register to answer the Eastmere security questionnaire and secure our re-tender, but our current risk register is out of date.
2. Systems added for the US pilot may hold care data that nobody has checked for security.
3. Carers' GPS check-in location data is marked high-risk, but we may never have assessed its privacy risks.
4. We hold copies of carers' criminal offence data, but our obligations register has no rules covering it.
5. Our Data Protection Officer is also Head of Legal, so nobody independent checks our privacy decisions. 

Questions I couldn't answer yet: see [open-questions.md](open-questions.md)  