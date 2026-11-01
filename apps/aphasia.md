> Public overview of the private repo `linggollms/linggollms-aphasia-webapp`. Why private: [why-the-code-is-private.md](../why-the-code-is-private.md). Mirrors that repo's README without the developer setup section.

# Linggo LLMs Aphasia

An AAC (picture and text communication) board for adults who have lost some or all of their speech: aphasia after a stroke, dementia, or a brain injury. The person taps pictures, words or whole sentences and the device says them aloud. Built for the person first, and for the families, carers and speech-language pathologists around them.

Part of [Linggo LLMs](https://github.com/linggollms). Started October 17, 2026 as a copy of the children's app, [Linggo LLMs ASD/IDD](https://github.com/linggollms/linggollms-asd-idd-webapp); the two share one code base and never share data.

**Status:** beta since October 23, 2026, web app and home-screen PWA at webapp-pwa.linggollms.com. This repo's `docs/` folder is the platform's documentation of record (PRD, TRD, architecture target, care-team architecture, Neptune, ADRs).

## What makes it the adult app

- **Whole adult sentences.** Every starter tile says a complete message ("I need the bathroom.", "Please give me time to answer."), in English, Spanish, Arabic, Chinese and French.
- **Adult starter topics:** Talking With Me (speaking accommodations for aphasia, all on the page), Speaking Up, Small Talk, Daily Needs, Health and Care, Feelings, About Me, My Day, Home, Things I Enjoy, Out and About. Each topic shows its most important tiles first, then small folders with the rest.
- **Adult voices by default** (Amazon Polly, device fallback), and setup written for the families, carers and therapists of adults.
- **Stop / Undo / "I'm not finished"**, phone layouts, "Keep me signed in", printable communication and wallet cards, and "Delete my account" (the person owns their account for life; care settings only borrow access).
- **Opt-in beta research** with de-identified figures; data collection off by default.

Everything else (the board, Quick Chat, "+ More", typing, the Dashboard and Builder, pictures, offline use, switch access) works as in the children's app.

## Where it runs

AWS, in its **own member account** ("Linggo LLMs Aphasia") inside the Linggo LLMs AWS Organization, so health information is fenced off and a HIPAA audit looks at one account. Built from CloudFormation (`deploy/aws/`, `scripts/aws-new-account.sh`): ECS Fargate (the app server, inside a private network), Cognito (sign-in), PostgREST on RDS Postgres 16 (the database, encrypted with the app's own key), S3 (pictures, signed links), Polly (voices), Bedrock (AI helpers: Amazon Nova by default, Claude when unlocked), and an **Amazon Neptune** graph (IAM-only, audited, HIPAA-eligible) for each person's own language. Organization-wide BAA, CloudTrail, GuardDuty, AWS Config with the HIPAA conformance pack, Security Hub.

Postgres is the record of everything. The graph sits beside it and links a person to what they said, to the words and pictures they used, and to what each word means for them (for example "cold" meaning pain), with standard medical meanings (SNOMED CT) to follow. Details: `docs/neptune.md`, `docs/own-aws-account.md`, `docs/architecture-target.md`.

## Stack

TypeScript · React 19 · TanStack Start · Vite · Bun · Drizzle ORM · PWA

## Rules for this repo

No secrets, account IDs, resource IDs, IP addresses, or anything that identifies a person who uses the app or their family. Documentation is written in plain words for clinicians, families and partners.
