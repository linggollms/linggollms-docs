# History: activity log

What was built, shipped and decided, with dates. Dates come from the git history of the repos and from the repos' own `docs/` folders; nothing here is reconstructed from memory. Current as of November 2, 2026.

## Before September 2026

Linggo was founded by a Board Certified Behavior Analyst with years of AAC practice. The original Linggo platform, built from 2020 by a contracted engineering team, served families and clinicians from its first beta in 2021, with about 2,900 registered learners and professionals. In September 2026 its graph database cluster ran into trouble: reads slowed and writes stopped. The lessons were documented, and the platform was rebuilt from new code, in a new company (Linggo USA Inc, doing business as Linggo LLMs), on an environment built for health information from the first day.

## Where the code lives

The new code base began on September 4, 2026 in the founder's `mylinggo` GitHub account and moved into the `linggollms` organization with its full history. Until mid-October, commits reached GitHub through a hosting tool's sync, so many carry its bot label; the code was written by the founder with Claude Code.

## September to November 2026

| When | Area | What was built or shipped |
| --- | --- | --- |
| Sept 4–18 | App, Database | New code base started (every change on a branch and pull request). The board: Language Tree, My Words, Keyboard with predictions, Quick Chat, caregiver Builder behind a PIN, a 3,593-word library with photos and emoji, Symbol Lab, five languages, switch-access focus. First database migrations; numbered product decision log |
| Sept 22–30 | App, Security | Aphasia product specified and started. Hashed PINs, admin-only clinician links, email-only sign-in |
| Oct 4–15 | App, Database | Offline use (board, pictures and chosen voice), opt-in character voices, Symbol Lab composition, My Topics builder, Scene Chat with AI suggestions, Lily's demo board, an accessibility QA pass, limits on codes and PIN tries, numbered database updates |
| **Oct 16** | **Architecture** | **Move to AWS:** Cognito sign-in, PostgREST on RDS Postgres, S3, Polly voices, Bedrock AI helpers (Nova; Claude when unlocked) |
| Oct 17–22 | Architecture, App | Aphasia app on AWS in its own member account under an organization-wide BAA, built from CloudFormation: CloudTrail, GuardDuty, AWS Config HIPAA pack (130 checks), Security Hub, KMS, private encrypted RDS, Neptune. Adult starter topics, wallet card, What's new. OpenAI removed. Architecture target and care-team design |
| **Oct 23** | **App** | **Aphasia beta live** at `webapp-pwa.linggollms.com`. Phone and iPad layouts. PRD and TRD |
| Oct 28–31 | Architecture, Docs | Both apps on ECS Fargate in private networks behind HTTPS-only load balancers, with alarms. Two-apps design and AWS account kit. Privacy Policy and Terms of Use published. ASD/IDD sign-up with optional text messages |
| **Nov 1–2** | **App, Docs** | **Both products in beta, including the ASD/IDD web app on AWS** (`webapp-dd.linggollms.com`). Public demo boards (Lily, Justin). Architecture page for each app; Accessibility Statement and Privacy Policy list both apps at their AWS addresses |

## By the numbers

As of November 2, 2026. About 2,000 unique commits across all branches of the organization. Commits on `main`: 1,534 in `linggollms-asd-idd-webapp` (since September 4, including the `mylinggo` period) and 269 in `linggollms-aphasia-webapp` (since September 22). Two AWS accounts in one Organization. CloudFormation templates for both apps' environments, including the Fargate move. A custom API layer: 26 server endpoints across the two apps, 90+ database endpoints generated through PostgREST from 47 tables and 49 functions (Aphasia app), Lambda sign-in hooks. 15 architecture decision records. A container security scan with seven findings, all in the Debian base image, none in Linggo's own code. Five languages. Two products.

## The decisions that shaped it

| Decision | When |
| --- | --- |
| One code base for children and adults; different content, voices and tone | Oct 17 |
| Only HIPAA-eligible AWS services touch what a person says; any outside voice or AI service needs a BAA or stays off | Oct 20–22 |
| The Aphasia app in its own AWS member account; the ASD/IDD app in the organization's main account | Oct 21, revised Oct 28 |
| Postgres is the record; Neptune sits beside it; the personal graph first, an anonymous shared graph (opt-in) later | Oct 20–22 |
| The person owns their account for life; organizations get time-limited access; a bedside tablet is only borrowed | Oct 20 |
| Data collection off by default; beta only, by number not name | Oct 19 |
| Amazon Nova as the default AI; Claude on Bedrock when unlocked | Oct 21 |
| App servers move from App Runner to ECS Fargate before real patients | Oct 22, built Oct 30–31 |
| No editing on the learner's screens; no auto-lock; email-only sign-in for now | Sept 16–17 |
