# Candidate risks (for the GRC-006 register)

Listed during GRC-002 (12 Nov 2026). Each becomes a full, scored risk entry in GRC-006.

| # | Candidate risk | Found in | Asset IDs |
| --- | --- | --- | --- |
| C-01 | No CloudTrail trail, so activity in AWS can't be investigated after an incident | GRC-002 discovery D5 | A-015 |
| C-02 | GuardDuty is off, so attacks on the AWS account may go unnoticed | GRC-002 discovery D6 | A-016 |
| C-03 | Resources created outside Terraform with no owner, so nobody secures or removes them | GRC-002 discovery D1, D2 | A-017, A-018 |
| C-04 | An unused IAM user remains in the AWS account | GRC-002 discovery D3 | A-020 |
| C-05 | Production assets in the systems list can't be verified, so the inventory may be incomplete | GRC-002 discovery D9 | A-012, A-013, A-014 |
| C-06 | Nobody knows where carers' DBS copies are stored | GRC-001 Q2; GRC-002 inventory | A-002 | 
Leo says S3 (13 Nov); not verified.
