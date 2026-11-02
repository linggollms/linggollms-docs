# History: activity log

What was built, shipped and decided, with dates. Dates come from the git history of the repos and from the repos' own `docs/` folders; nothing here is reconstructed from memory. Current as of November 2, 2026.

## Before

Linggo was founded by a Board Certified Behavior Analyst with years of AAC practice. Development began at the end of 2019, and the first beta was released in 2021, during COVID. The original product was a live AAC app used by families and clinicians: a Python Serverless Framework backend on AWS Lambda, API Gateway, Cognito, DynamoDB and S3, a self-managed Neo4j graph database on EC2, and a Flutter front end, built by a contracted development team. The last meaningful commits to that codebase are from September 2024.

In early September 2026 the Neo4j cluster behind it failed: reads degraded and writes stopped. The incident review listed what the new platform must not repeat: public access and exposed ports, credentials in repository history, no monitoring, untested backups. The original system was replaced rather than patched, in a new company (Linggo USA Inc, doing business as Linggo LLMs), on an environment built for health information.

## Where the code lives

The new code base began on September 4, 2026 in the founder's `mylinggo` GitHub account and moved into the `linggollms` organization in late October, with its full history. Until mid-October, commits reached GitHub through a hosting tool's sync, so many carry its bot label; the code was written by the founder with Claude Code. That hosting tool is no longer used for the apps; only the marketing website remains on it until it moves to AWS.

## September 2026

| When | Built, shipped or decided |
| --- | --- |
| Sept 4 | First commit of the new code base, from a TanStack Start template. Every change on a branch and a pull request from the start. |
| Sept 10–18 | About 940 commits. The Language Tree rebuilt to match how learners moved through the original app, My Words, Keyboard with predictions, Quick Chat, the caregiver Builder behind a PIN, a 3,593-word library (licensed symbol sets deliberately not shipped), photos and emoji with skin tones, Symbol Lab, five languages (English, Spanish, Arabic, Mandarin, French), cloud voices with device fallback, switch-control-friendly focus. |
| Sept 16–17 | First product decisions recorded as a numbered log with dates and reasons: no editing on the learner's screens, no auto-lock, no donations in the app until it is secured. |
| Late Sept | Security fixes (hashed PIN functions, admin-only clinician links); consumer-beta sign-up with an active consent checkbox and a stored consent record. |
| Sept 30 | The adult (aphasia) product specified. |

## October 2026

| When | Built, shipped or decided |
| --- | --- |
| Early Oct | Plan to leave the first host: its sign-in and data treated as an MVP layer, synced to a Linggo-owned GitHub repo from day one. |
| Oct 13–15 | ASD/IDD app: a demo board with a recorded voice, Scene Chat with AI suggestions, child starter topics, safety limits on codes, PINs and paid voices. The product and AI roadmap and the HIPAA-controlled AWS plan written. Database rehearsed on plain Postgres: every migration applies. |
| Oct 15–16 | **Move to AWS.** The first host's managed database could not meet HIPAA requirements. Cognito sign-in with a pre-token Lambda, PostgREST on RDS Postgres, S3 with signed links, Polly voices, Bedrock AI helpers, first on App Runner. |
| Oct 17 | **Aphasia app started on AWS** as a copy of the ASD/IDD app's AWS branch: adult starter topics in whole sentences, adult voices, adult library and Quick Chat. Database built from scratch and rehearsed the same day. |
| Oct 17–22 | About 140 commits on the Aphasia app: opt-in beta research, the beta feedback survey, "Delete my account", the care-partner questionnaire with printable communication and wallet cards, Stop/Undo/"I'm not finished", phone layouts, "Keep me signed in". |
| Oct 20 | Architecture target written: the person owns their account for life, care settings borrow access, a bedside tablet is only borrowed; store apps via Capacitor; Neptune; FHIR and the Smile CDR appSphere gallery. |
| Oct 21–22 | **Aphasia member account** inside a Linggo LLMs AWS Organization: organization-wide BAA accepted (the "Healthcare and Life Sciences" add-on declined, because it would let AWS de-identify our data for its own use); organization-wide CloudTrail; GuardDuty; AWS Config with the HIPAA conformance pack (130 checks); Security Hub. Four CloudFormation templates and one build script. Amazon Neptune built, IAM-only, encrypted with the app's own key, every query audited. |
| Oct 22 | Care-team architecture written: companions, coaches, admins, consent, access log, FHIR mapping. Evidence review of the v1 beta against the AAC research base produces the build list for the next release. |
| Oct 23 | **Aphasia beta live** at webapp-pwa.linggollms.com. PRD, technical requirements, UI/UX, app flow, backend schema and implementation plan written. |
| Oct 24–29 | Phones and iPads: landscape layout, one tile size, phone keyboard. Speech on iPhones in any browser and in silent mode; the chosen voice saved for use offline; a tap speaks at once. Calm Lagoon (teal) as the adult default theme. Care-team design with one account for every role and organization IDs. Decisions: a Companion app for parents and caregivers, a Coach app for clinicians, one consent at first invitation; the ASD/IDD app stays in the organization's main account (Oct 28). Neptune stopped until the app writes to it (Oct 28). Old Linggo error analysis, September 1 to October 30. A read-only look at the original company's AWS account finds about 2,900 registered users; they are to move into the new app after the beta. |
| Oct 30 | Privacy Policy and Terms of Use published at policies.linggollms.com. OpenAI removed from every service. Aphasia app: ElevenLabs only with a person's own account. ASD/IDD app: sign-up stands on its own. |
| Oct 30–31 | **Both apps on ECS Fargate** in private networks, beside App Runner as the way back: HTTPS-only load balancers, request and traffic logs kept a year, alarms that also fire when data stops arriving. ASD/IDD app: optional text messages at sign-up; the board fits phones, iPads and computers. |

## November 2026

| When | Built, shipped or decided |
| --- | --- |
| Nov 1 | **Both products in beta, including the ASD/IDD web app on AWS.** Both apps: make a new word from a category, and say when a category isn't on the board. |
| Nov 1–2 | Public demo: Lily's and Justin's communication boards with child voices, no sign-in, at demo-lily.linggollms.com and demo-justin.linggollms.com; only linggollms.com may embed them. |
| Nov 2 | An architecture page in each app repo (`docs/architecture.md`): AWS, BAA boundary, security controls, accessibility, gaps before real patients. The leftover `.env` from the first host removed from the ASD/IDD repo and blocked by `.gitignore`. |

## By the numbers

As of November 2, 2026. Commits on `main`: 1,534 in `linggollms-asd-idd-webapp` (since September 4, including the `mylinggo` period) and 269 in `linggollms-aphasia-webapp` (since September 22). Two AWS accounts in one Organization. CloudFormation templates for both apps' environments, including the Fargate move. A custom API layer: 26 server endpoints across the two apps, 90+ database endpoints generated through PostgREST from 47 tables and 49 functions (Aphasia app), Lambda sign-in hooks. 15 architecture decision records. A container security scan with seven findings, all in the Debian base image, none in Linggo's own code. Five languages. Two products.

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
