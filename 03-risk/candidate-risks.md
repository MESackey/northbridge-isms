# Candidate risks (for the GRC-006 register)

Listed during GRC-002 (12 Nov 2026). Each becomes a full, scored risk entry in GRC-006.

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