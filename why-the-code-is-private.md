# Why the code is private

The product repositories of Linggo LLMs are private. This page says why, and what a reader can see instead.

## The reasons

**The apps handle health information.** Linggo LLMs Aphasia and Linggo LLMs ASD/IDD store what a person says, their personal vocabulary and meanings, and their progress. In the United States that is protected health information when a hospital, clinic or health plan is involved, and we build as if it always is. The repos contain the schema, the access rules, the audit logging and the deployment templates for the environment that holds that data. Publishing them would hand anyone a map of the systems we are obliged to protect.

**The environment is HIPAA-covered and audited.** Both products run inside a Linggo LLMs AWS Organization under an organization-wide Business Associate Addendum, with CloudTrail, GuardDuty, AWS Config (HIPAA conformance pack) and Security Hub enabled. Security findings, remediation notes and infrastructure details live in the repos' `docs/` folders alongside the code. We are happy to walk an investor or partner through them under NDA; we do not publish them.

**The products are in beta.** Beta research runs on opt-in, with participants identified by number, not name. The repos hold survey logic, consent copy and the beta runbooks. Those are not secret, but they change weekly and are easy to misread out of context.

**Licensed content.** The library includes third-party symbol sets under licence. The code paths that handle them are not for redistribution.

## What is public instead

- This documentation repo: what each product is, how it is built, the architecture, the history, and how the company runs.
- The [organization README](https://github.com/linggollms): the ten-week story, the numbers, and the architecture map.
- Every repo's README, reproduced here under [apps/](apps/) at the level of purpose, stack and status.

## What we will show on request

Under NDA, to investors, clinical partners and auditors: the repositories themselves, the AWS Config conformance results, the CloudTrail and Neptune audit log configuration, the architecture decision records (ADR-001 to ADR-015), the security scan results, and the beta research protocol. Write to ling@linggollms.com.

## What is never written anywhere public

Secrets, AWS account or resource IDs, IP addresses, instance IDs, and anything that identifies a learner, a family member or a clinician who uses the app. This rule is written into every repo's README and into `CLAUDE.md`, the working instructions the coding agent reads at the start of every session.
