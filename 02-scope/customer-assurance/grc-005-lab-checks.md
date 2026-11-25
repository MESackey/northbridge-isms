# GRC-005 · Lab checks (questions 4, 5 and 14)
Checked by: Junior GRC Analyst · Date: Mon 23 Nov 2026 (screenshots reviewed Wed 25 Nov 2026) · Signed in as: grc-admin (MFA) · Region: eu-west-2 (IAM is global)
Scope: the lab AWS account only. Leo confirmed (23 Nov) that the lab doesn't match production, so these results prove the lab, not CarePath production. They show the method we will use on production evidence.

| # | Q | Check | Where in the console | What I saw | Result (lab) |
| --- | --- | --- | --- | --- | --- |
| L1 | 4 | Root user has MFA | IAM → Dashboard → Security recommendations | Green tick: "Root user has MFA"[cite: 4] | Pass |
| L2 | 4 | MFA for each IAM user | IAM → Users (MFA column) | `grc-admin`: Virtual MFA (1) enabled; `grc-auditor`: Virtual MFA (1) enabled; `CLIusage1`: Console access Disabled, Console password Not enabled, MFA (0) (no console access)[cite: 5, 6, 8, 13, 14, 15, 16] | Pass (console users MFA enabled; `CLIusage1` N/A for console MFA) |
| L3 | 4 | Access key age for each IAM user | IAM → Users (Active key age column) | `grc-admin`: 1 active access key (`grc-terraform-key`), 44 days old (within 90 days); `CLIusage1`: Access keys (0); `grc-auditor`: Access keys (0)[cite: 6, 9, 14, 16] | Pass |
| L4 | 5 | S3 default encryption | S3 → cp-exports-temp-mes → Properties → Default encryption | Encryption type: "Server-side encryption with Amazon S3 managed keys (SSE-S3)"; Bucket Key: Enabled; SSE-C blocked[cite: 17] | Pass |
| L5 | 5 | EC2 disk (EBS volume) encrypted | EC2 → Instances → reports-legacy → Storage tab | Instance `reports-legacy` (`i-072f74c86e11d5051`, Stopped) shows attached volume `vol-0648a24cfc703e8c3` (`/dev/xvda`, 8 GiB, In-use), but the `Encrypted` column is scrolled off to the right and not visible[cite: 18] | Not visible (column scrolled) |
| L6 | 5 | New disks encrypted by default | EC2 → Dashboard → Account attributes → Data protection and security | Under EBS encryption: "Always encrypt new EBS volumes: Disabled" (red X)[cite: 21] | Fail |
| L7 | 14 | Age of the server image (AMI) | EC2 → reports-legacy → Details → AMI ID → Creation date | AMI name starts with `al2023-ami-...-kernel-6.1...-x86_64`, but the AMI `Creation date` is not visible in the screenshot[cite: 20] | Not visible (creation date not shown) |
| L8 | 14 | Server managed for patching | Systems Manager → Fleet Manager | Systems Manager Fleet Manager shows landing screen "Get started with Fleet Manager" / "Get started" (not an active managed-nodes list showing `reports-legacy`)[cite: 22] | Fail |

*(Additional observation from shared screenshots: GuardDuty shows "Try GuardDuty for free" / "Get started" in `Europe (London)`, indicating GuardDuty is not enabled in the lab account[cite: 1, 2, 3].)*

## What this means for production
- L1 to L3 → ask Leo for the IAM Identity Center MFA settings page and the IAM Users list for production (user names, MFA and key age only; no IDs). Leo has already mentioned one key over a year old (ci-deploy).
- L4 to L6 → ask Leo for S3 default encryption settings, RDS and snapshot encryption settings (C-12), and EC2/EBS default encryption/load-balancer-to-app transport encryption details for production.
- L7 and L8 → ask Leo for production container image/AMI build and patching details plus Systems Manager Fleet Manager or patch compliance status for production workloads.