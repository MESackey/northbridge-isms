# GRC-002 discovery log: AWS and GitHub
Checked by: Junior GRC Analyst · Date: Mon 9 Nov 2026 · Signed in as: grc-admin (MFA)

| # | Check | Where I looked | What I found | Matches the pack? |
| --- | --- | --- | --- | --- |
| D1 | Resources in every region | EC2 → AWS Global View | 1 EC2 instance in eu-west-2 (London); default VPCs in all active AWS regions | Yes, pack states hosting is in the London region |
| D2 | S3 buckets | S3 → General purpose buckets (All AWS Regions) | 1 bucket: cp-exports-temp-mes (eu-west-2, created 9 Nov) | No, Kwame's systems list does not mention this bucket |
| D3 | IAM users and access keys | IAM → Users → Security credentials | 2 users (grc-admin, CLIusage1); CLIusage1 has no active access keys (key deleted per Day 8 notes) | Not stated in pack |
| D4 | IAM groups and roles | IAM → User groups; Roles | No user group found; standard AWSServiceRole entries present | Not stated in pack |
| D5 | CloudTrail trails | CloudTrail → Trails | No event trail | Pack says CloudTrail exists: No |
| D6 | GuardDuty | GuardDuty | Shows the 'Get Started' page | Pack says GuardDuty exists: No |
| D7 | GitHub repositories | github.com/MESackey?tab=repositories | Repositories found: `northbridge-isms`, `northbridge-grc` | Pack says "GitHub + Actions": Yes |
| D8 | Earlier asset register | northbridge-grc/05-asset-cmdb/asset-register.csv | File exists in repository containing baseline asset records | Yes, provides earlier inventory baseline |

## Not on IT's list
The S3 bucket `cp-exports-temp-mes` in eu-west-2 was found in AWS S3 (All Regions) during the S3 bucket check but is completely missing from Kwame's systems list. Because it was created on 9 Nov as a temporary export location for CarePath data, it represents an uninventoried data store holding sensitive information outside formal configuration management and risk assessment.