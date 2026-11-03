# Company profile: Northbridge Health Ltd
As of 3 Nov 2026 · Author: Junior GRC Analyst · Sources: onboarding pack, open-questions.md

## What we do
Northbridge Health Ltd provides CarePath, a cloud-based software platform that lets home-care agencies schedule visits for carers and run Electronic Medication Administration Records (eMAR). The platform supports around 41,000 people receiving home care across the UK. 

## Who we serve
We serve home-care agencies and local authorities, supporting approximately 41,000 individuals receiving home care, plus a US home-health group participating in a pilot since September 2026.

## What data we hold, and where
Patient care records and medical notes (special category health data): stored in the primary cloud database hosted on Amazon Web Services (AWS).
Medication administration records (eMAR): stored in the AWS cloud environment.
Carers' GPD check-in location data: stored in the AWS database upon visit check-in.
Carers' Disclosure and Barring Service (DBS) certificate copies (criminal offence data): stored for partner agencies. 
Staff records and internal administration files: managed via Microsoft 365 and local office systems. 
Northbridge acts mostly as a data processor, handling personal and health data on behalf of home-care agencies (who act as data controllers).

## Who we answer to
Information Commissioner's Office (ICO): enforces UK data protection law (UK GDPR), requiring data breach notifications within 72 hours.
Care Quality Commission (CQC): inspects care providers and evaluates the safety and governance of care records.
NHS England: requires passing the annual Data Security and Protection Toolkit (DSPT) assessment to maintain our NHS contracts.
National Cyber Security Centre (NCSC): provides security guidance and frameworks such as Cyber Essentials Plus.

## Crown jewels
1. CarePath primary cloud databse (AWS): if it were down or stolen, 41,000 vulnerable patients' health and medication records would be exposed or inaccessible, halting care delivery across providers.
2. Visit scheduling and eMAR system: if this service experienced an outage, carers could not track medication schedules or visit assignments, directly risking patient safety.
3. Carer GPS location and check-in records: if compromised or lost, sensitive location patterns of vulnerable care workers and clients would breach privacy obligations and regulatory trust.

## Top five worries
1. The system inventory was last updated in June 2026, meaning new infrastructure or data flows added for the September US pilot are completely uninventoried and unassessed.
2. The Data held table identifies carers' GPS location data as high-risk, but our Obligation list contains no corresponding legal safeguards or rules covering it.
3. We hold copies of carers' DBS cerificates (criminal offence data), but our Obligations list lacks any reference to the required UK GDPR Article 10 conditions.
4. The Data held table provides no defined retention periods for sensitive data such as DBS copies and GPS check-in history.
5. Key security leadership roles and responsibilities lack independent separation of duties, risking unmanaged conflicts between legal advisory and compliance oversight.

Questions I couldn't answer yet: see open-questions.md 