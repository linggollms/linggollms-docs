# The ten weeks: how Linggo LLMs got here

September 4 to November 1, 2026. Dates come from the git history of the repos and from the repos' own `docs/` folders; nothing here is reconstructed from memory.

## Before

Linggo was founded in 2021 by a Board Certified Behavior Analyst with years of AAC practice, and shipped its first working beta during COVID. The original product was a live AAC app used by families and clinicians: a Python Serverless Framework backend on AWS Lambda, API Gateway, Cognito, DynamoDB and S3, a self-managed Neo4j graph database on EC2, and a Flutter front end, built by a contracted development team. By late 2024 active development had stopped. The last meaningful commits to the original codebase are from September 2024; for the next twelve months the app ran, and nobody was building it.

## September 2026: the outage

In early September the Neo4j cluster behind the live app failed. Reads degraded, writes stopped, and the people who depended on Linggo to speak could not. The incident review that followed found what the new platform must never repeat: public access and exposed ports, credentials in repository history, no monitoring, untested backups. The developer was unreachable. The founder, who had never used a terminal, found and fixed the fault herself.

That was the turning point. The decision was not to patch the old system but to replace it: every line, in a new company (Linggo USA Inc, doing business as Linggo LLMs), in an environment built for health information from the first day.

## The rebuild

| When | What happened |
| --- | --- |
| **Sept 4** | First commit of the new codebase, from a TanStack Start template. The founder in the terminal with Claude Code as the coding agent; every change on a branch and a pull request from the start. |
| **Sept 10–18** | The heavy build: about 940 commits in two weeks. The Language Tree rebuilt to match how learners moved through the original app, My Words, Keyboard with predictions, Quick Chat, the caregiver Builder behind a PIN, a 3,593-word library (licensed symbol sets deliberately not shipped), photos and emoji with skin tones, Symbol Lab, five languages (English, Spanish, Arabic, Mandarin, French), cloud voices with device fallback, switch-control-friendly focus. |
| **Sept 16–17** | The first product decisions recorded as a numbered log with dates and reasons: no editing on the learner's screens, no auto-lock, no donations in the app until it is secured. |
| **Late Sept** | Security hotfixes (hashed PIN functions, admin-only clinician links); consumer-beta sign-up with an active consent checkbox and a stored consent record. |
| **Sept 30** | The adult (aphasia) product is specified. |
| **Early Oct** | The approach to the first version's hosting is set: treat its auth and data as an MVP layer, sync to a Linggo-owned GitHub repo from day one, plan the replacement before leaving. |
| **Oct 13–15** | Children's app: a demo board with a recorded voice, Scene Chat with AI suggestions, child starter topics, safety limits on codes, PINs and paid voices. The product and AI roadmap, the plan to move off the first host, and the HIPAA-controlled AWS environment plan are written. The database is rehearsed on plain Postgres: every migration applies. |
| **Oct 15–16** | **The move to AWS.** The managed database the first version ran on could not meet HIPAA requirements, and migrating users' language graphs later would only get harder. Cognito sign-in with a pre-token Lambda, PostgREST on RDS Postgres, S3 with signed links, Polly voices, Bedrock AI helpers; App Runner at first, replaced by ECS Fargate. The hosting and sync layer is removed. |
| **Oct 17** | **The adult app restarts on AWS** as a copy of the children's AWS branch. Adult starter topics in whole sentences, adult voices, adult library and Quick Chat. Database built from scratch and rehearsed locally the same day. |
| **Oct 17–22** | About 140 commits on the adult app: opt-in beta research, the beta feedback survey, "Delete my account", the care-partner questionnaire with printable communication and wallet cards, Stop/Undo/"I'm not finished", phone layouts, "Keep me signed in". |
| **Oct 20** | The architecture target is written: the person owns their account for life, care settings borrow access, a bedside tablet is only borrowed; store apps via Capacitor; Neptune; FHIR and the Smile CDR appSphere gallery. |
| **Oct 21–22** | **The aphasia product gets its own AWS member account** inside a Linggo LLMs AWS Organization: organization-wide BAA accepted (the "Healthcare and Life Sciences" add-on deliberately declined, because it would let AWS de-identify our data for its own use); organization-wide CloudTrail; GuardDuty; AWS Config with the HIPAA conformance pack (130 checks); Security Hub. Four CloudFormation templates and one build script. Amazon Neptune built, IAM-only, encrypted with the app's own key, every query audited. Switched over October 22. |
| **Oct 22** | The care-team architecture is written: companions, coaches, admins, consent, access log, FHIR mapping. The research agent's evidence review of the v1 beta produces the build list for the next release. |
| **Oct 23** | **Aphasia beta live** at webapp-pwa.linggollms.com. PRD, technical requirements, UI/UX, app flow, backend schema and implementation plan written as a handover set. |
| **Oct 24–29** | PRD and TRD merged. The founder's decisions on the care side: a Companion app for parents and caregivers, a Coach app for clinicians, one consent at first invitation, the old coach app kept for data collection until the new one exists. A read-only look at the original company's AWS account finds about 2,900 registered users in its sign-in pools; they are to move into the new app after the beta. |
| **Nov 1** | **Both products in beta.** |

## By the numbers

2,049 unique commits and 179 merged pull requests across the organization in 58 days, by the founder working with Claude Code. Two AWS accounts built from CloudFormation. 253 database migrations rehearsed locally before deploy. 15 architecture decision records. A container security scan with seven findings, all in the Debian base image, none in Linggo's own code. Five languages. Two products.

## The decisions that shaped it

| Decision | When |
| --- | --- |
| One code base for children and adults; different content, voices and tone | Oct 17 |
| Only HIPAA-eligible AWS services touch what a person says; any outside voice or AI service needs a BAA or stays off | Oct 20–22 |
| The adult app in its own AWS member account; the children's app in the organization's main account | Oct 21, revised Oct 28 |
| Postgres is the record; Neptune sits beside it; the personal graph first, an anonymous shared graph (opt-in) later | Oct 20–22 |
| The person owns their account for life; organizations get time-limited access; a bedside tablet is only borrowed | Oct 20 |
| Data collection off by default; beta only, by number not name | Oct 19 |
| Amazon Nova as the default AI; Claude on Bedrock when unlocked | Oct 21 |
| No editing on the learner's screens; no auto-lock; email-only sign-in for now | Sept 16–17 |
