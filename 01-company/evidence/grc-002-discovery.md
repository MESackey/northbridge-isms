# GRC-002 discovery log: AWS and GitHub
Checked by: Junior GRC Analyst · Date: Tue 10 Nov 2026 · Signed in as: grc-admin (MFA)

| # | Check | Where I looked | What I found | Matches the pack? |
| --- | --- | --- | --- | --- |
| D1 | Resources in every region | EC2 → AWS Global View | 1 EC2 instance (`reports-legacy`) in eu-west-2 (London); default VPCs in all active AWS regions | No, Kwame's systems list does not mention `reports-legacy` |
| D2 | S3 buckets | S3 → General purpose buckets (All AWS Regions) | 1 bucket: `cp-exports-temp-mes` (eu-west-2, created 9 Nov) | No, Kwame's systems list does not mention this bucket |
| D3 | IAM users and access keys | IAM → Users → Security credentials | 2 users (`grc-admin`, `CLIusage1`); `CLIusage1` has no active access keys (key deleted per Day 8 notes) | No, `CLIusage1` is not listed on IT's inventory |
| D4 | IAM groups and roles | IAM → User groups; Roles | No User groups found; standard AWSServiceRole entries present | Not stated in pack |
| D5 | CloudTrail trails | CloudTrail → Trails | No active trails found (CloudTrail is currently disabled/absent) | Pack says CloudTrail exists: No (missing/disabled) |
| D6 | GuardDuty | GuardDuty | Shows a "Get started" page (GuardDuty is not enabled) | Pack says GuardDuty exists: No (disabled/absent) |
| D7 | GitHub repositories | github.com/MESackey?tab=repositories | Repositories found: `northbridge-isms`, `northbridge-grc` | Pack says "GitHub + Actions": Yes |
| D8 | Earlier asset register | northbridge-grc/05-asset-cmdb/asset-register.csv | File exists in repository containing baseline asset records. Describes a different product (clinic scheduling); its business-level rows are not used (decision 9 Nov, option A). | Yes, provides earlier inventory baseline |
| D9 | Documented AWS assets not found | EC2, S3, RDS (database) | No containers, PostgreSQL database or S3 document store | No: the lab account does not simulate CarePath's production workloads. The inventory records them from the pack, marked "not verified". Security controls (CloudTrail, GuardDuty) are treated as real findings, because the lab did run CloudTrail (Day 12) and it is now gone. |

## Not on IT's list
1. **S3 bucket `cp-exports-temp-mes`** (eu-west-2): found via S3 → All AWS Regions. Not on Kwame's systems list. Created 9 Nov by `grc-admin` (CloudTrail event history). The name suggests CarePath data exports; it is currently empty. No owner tag and not managed in Terraform. Owner unknown: ask the CTO, who owns AWS.
2. **EC2 instance `reports-legacy`** (eu-west-2): found via EC2 → AWS Global View / Instances. Not on Kwame's systems list. Created 9 Nov by `grc-admin` (CloudTrail event history). The name suggests legacy reporting functions; it is currently stopped without an owner tag or Terraform management. Owner unknown: ask the CTO, who owns AWS.
3. **IAM user `CLIusage1`**: found via IAM → Users. Not on Kwame's systems list or IT records. Inactive user with no active access keys remaining. Owner unknown: ask the IT Manager or CTO.