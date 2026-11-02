> Public overview of the private repo `linggollms/linggollms-asd-idd-webapp`. Why private: [why-the-code-is-private.md](../why-the-code-is-private.md). Mirrors that repo's README without the developer setup section.

# Linggo LLMs ASD/IDD

An AAC (picture and text communication) board for children and youth with autism or intellectual and developmental disabilities who have little or no speech, and for the parents, caregivers, teachers and therapists around them. The child taps pictures, words or whole sentences and the device says them aloud.

Part of [Linggo LLMs](https://github.com/linggollms). The Aphasia product, [Linggo LLMs Aphasia](https://github.com/linggollms/linggollms-aphasia-webapp), shares this code base with different content, voices and tone; fixes flow both ways. The two apps never share data.

**Status:** beta (November 1, 2026), web app and home-screen PWA at webapp-dd.linggollms.com. Replaces the original Linggo app (2021–2024, Flutter).

## What it does

- **Language Tree, My Words, Keyboard with predictions, Quick Chat, Scene Chat.** Five board modes, built to match how learners moved through the original Linggo so no one has to relearn.
- **Five languages:** English, Spanish, Arabic, Mandarin, French, including right-to-left and CJK layouts.
- **A 3,500+ word library** with photos and emoji (skin tones included), a Symbol Lab, and a caregiver Builder behind a PIN. No editing on the learner's screens.
- **Natural voices** (Amazon Polly) with child voices by default and device-voice fallback.
- **Public demo:** Lily's and Justin's communication boards, no sign-in, at demo-lily.linggollms.com and demo-justin.linggollms.com.
- **Accessibility:** switch-access-friendly focus handling, accessible keyboards, full offline use.
- **AI helpers** on Amazon Bedrock for suggestions (Scene Chat suggest-from-photo), behind safety limits on codes, PINs and paid voices.
- **Beta research, opt-in only.** Data collection is off by default; beta participants are identified by a number, not a name.

## Where it runs

AWS, in the Linggo LLMs account (the organization's main account): ECS Fargate in a private network behind an HTTPS-only load balancer (built October 30–31, 2026; App Runner serves until the web address is switched), Cognito (sign-in), PostgREST on Amazon RDS Postgres (the database), S3 (pictures), Polly (voices), Bedrock (AI helpers). Organization-wide BAA, CloudTrail, GuardDuty, AWS Config with the HIPAA conformance pack, Security Hub. The database and database API were first built by hand on October 16 and are to be rebuilt inside a private network from the same CloudFormation kit as the Aphasia app. Setup and settings: `docs/architecture.md`, `docs/fargate.md`, `docs/aws-account-kit.md`, `docs/aws-app-settings.md`.

Development is on AWS only. The first version of this app ran on a hosted prototype platform from September 4 to mid-October 2026 (code kept in GitHub from day one, first in the `mylinggo` account); it moved to AWS because that platform's managed database could not meet HIPAA requirements. People are moving onto the AWS app.

## Stack

TypeScript · React 19 · TanStack Start · Vite · Bun · Drizzle ORM · PWA

## Rules for this repo

No secrets, account IDs, resource IDs, IP addresses, or anything that identifies a learner or their family. Documentation is written in plain words for clinicians, families and partners.
