# Week 5 status · w/c Mon 23 Nov 2026

## Done
- Completed Eastmere supplier security questionnaire (`Final v1.0`) across all 15 questions with evidence links and confidence ratings (`2 Confirmed`, `6 Partial`, `7 Gap`), ready for Priya Raman's sign-off before the 4 Dec submission (`02-scope/customer-assurance/eastmere-questionnaire.md`).
- Delivered draft v0.1 to Sofia Brennan with concise commercial framing (`02-scope/customer-assurance/reply-to-sofia.md`), negotiated 5 wording/content requests (`Decision / outcome` table in `GRC-005`), and built the reusable customer assurance answer library (`02-scope/customer-assurance/answer-library.md`).
- Executed AWS lab checks (`L1–L8` in `grc-005-lab-checks.md`) and verified production evidence screenshots from Leo Park (IAM Identity Center MFA, `ci-deploy` 412-day key, S3 SSE-S3 encryption, and RDS unencrypted database), updating `data-flow-care-record.md` (`F3`, `F4`) and `C-12`.
- Added 10 new candidate risks (`C-15` to `C-24`) from questionnaire gaps to `03-risk/candidate-risks.md` and closed `GRC-005`.

## Found
- **Confirmed strengths (2/15):** Cyber Essentials Plus (issued 12 Mar 2026; renews Mar 2027 alongside re-tender) and NHS DSPT 2025–26 Standards Met (published 26 Jun 2026).
- **Verified & newly surfaced gaps:** Production RDS database confirmed unencrypted (`C-12`, target before 31 Dec 2026); `ci-deploy` access key is 412 days old (`C-16`); pen test overdue since 14 Feb 2025 with 3 open mediums (`C-15`); no annual security refresher since 2024 (`C-19`); engineers lack DBS checks (`C-20`); unlogged non-M365 leaver access removal (`C-21`); no BCP/DR plan or tested restore (`C-22`); 4 of 11 critical/high container findings took 21–45 days (`C-23`); and free ChatGPT in use on two Customer Success laptops without an AI policy (`C-24`, under DPO review).
- **Environment difference:** Production runs on AWS Fargate containers (no EC2 servers), making Systems Manager Fleet Manager (`L8`) non-applicable to production.

## Blocked
- None on `GRC-005` (closed). Pending downstream follow-ups carried into next week: Priya Raman's sign-off on `Final v1.0` before 4 Dec, Grace Whitfield's assessment of ChatGPT data exposure and agency sub-processor notices (due 4 Dec), and lab click-through completion for `L5` and `L7` (due 27 Nov).

## Next week
- Open `GRC-006` on Mon 30 Nov 2026 to rebuild the formal ISO 27001 risk register from `C-01` to `C-24` ahead of the 5 Dec target.

## Hours this week
- **GRC-005:** 4.9 h
- **Total:** 4.9 h