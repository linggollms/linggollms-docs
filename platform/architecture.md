# Architecture: Linggo LLMs ASD/IDD and Linggo LLMs Aphasia

One document for both products. It says what the two apps share, what they keep separate, how the AWS environment is laid out, what is live, what is in progress, and what comes after the beta. Account and resource identifiers, network addresses and keys are never written down here or anywhere else public. Current as of November 3, 2026 (documented November 2; both accounts checked read-only in the AWS console on November 3).

## The whole thing, in three pictures

**1. Two products, one code base, two accounts.** The apps never share data.

```mermaid
flowchart LR
  P["People<br/>web app + PWA<br/>phone · tablet · bedside"]
  APP["One code base<br/>same app, two products"]
  subgraph ORG["Linggo LLMs AWS Organization · one BAA · one audit trail"]
    direction LR
    A["Linggo LLMs account<br/>the ASD/IDD app"]
    B["Aphasia member account<br/>the Aphasia app + language graph"]
  end
  P --> APP
  APP --> A
  APP --> B
  A -. no shared data .- B
```

**2. Inside each account.** The same pattern in both; the graph is built in the Aphasia account today (stopped until its write path ships) and is planned for ASD/IDD.

```mermaid
flowchart LR
  LB["Load balancer<br/>HTTPS only"] --> F["ECS Fargate<br/>app server, private network"]
  F --> C["Cognito<br/>sign-in"]
  F --> API["PostgREST<br/>database API"]
  API --> D["RDS Postgres<br/>the record"]
  F --> S["S3<br/>pictures"]
  F --> V["Polly<br/>voices"]
  F --> AI["Bedrock<br/>AI helpers"]
  D -. Aphasia only .-> N["Neptune<br/>language graph"]
```

**3. In progress, and after the beta.**

```mermaid
flowchart LR
  subgraph NOW["In progress"]
    H["AI assistant in the app<br/>both products"]
    M["PHI intake: email + secure upload<br/>Aphasia"]
    G["Graph write path + meanings<br/>Aphasia"]
  end
  subgraph NEXT["After the beta"]
    ST["iOS · Google Play · Amazon Appstore"]
    CC["Companion app · Coach app · Admin panel"]
    FH["Hospitals via FHIR / appSphere"]
  end
  NOW --> NEXT
```

## The two apps, side by side

| | **Linggo LLMs ASD/IDD** | **Linggo LLMs Aphasia** |
| --- | --- | --- |
| Who | Children and youth with autism or IDD and little or no speech; parents, caregivers, teachers, therapists | Adults with aphasia (often after stroke), dementia or brain injury; families, carers, speech-language pathologists |
| Repo | `linggollms-asd-idd-webapp` (private) | `linggollms-aphasia-webapp` (private; its `docs/` is the platform's documentation of record) |
| Status | Beta, Nov 1, 2026, web app + PWA at webapp-dd.linggollms.com; public demo boards (Lily, Justin) | Beta since Oct 23, 2026, web app + PWA at webapp-pwa.linggollms.com |
| Code | **Shared.** The Aphasia app began Oct 17 as a copy of the ASD/IDD app's AWS branch; the ASD/IDD repo is a git remote of the Aphasia repo, so fixes flow both ways | Same |
| What differs in code | Starter topics, voices, tone, default theme (purple Day Orchid), setup copy for parents and teachers, Scene Chat with AI suggestions, demo board with a recorded voice | Whole-sentence adult starter topics, adult voices, default theme (teal Calm Lagoon), setup copy for families and carers of adults, Stop/Undo/"I'm not finished", printable communication and wallet cards |
| Languages | English, Spanish, Arabic, Mandarin, French | Same |
| Board modes | Language Tree, My Words, Keyboard with predictions, Quick Chat, Scene Chat | Same five, adult content |
| Accessibility | Switch-access focus handling, accessible keyboards, full offline use, device-voice fallback | Same |
| AWS account | The Linggo LLMs account (also runs the Organization and the bill) | Its own member account, so health information is fenced off and an audit looks at one account |
| Compute | ECS Fargate in a private network, built Oct 30–31; App Runner serves until the DNS switch | ECS Fargate in the account's private network, built Oct 31; App Runner serves until the DNS switch |
| Sign-in | Own Cognito user pool | Own Cognito user pool |
| Database | Own RDS Postgres via PostgREST; first built by hand on Oct 16, to be rebuilt inside a private network with the app's own key from the same CloudFormation kit as the Aphasia app | Own RDS Postgres 16 via PostgREST, private, encrypted with the app's own key |
| Files | Own S3, signed links only | Own S3, signed links only |
| Graph | Amazon Neptune planned, from the same template as Aphasia; linking soon | Amazon Neptune: each person's own language graph. IAM-only, audited, encrypted. Built, kept stopped until the write path ships |
| Voices | Amazon Polly, device fallback | Amazon Polly, device fallback; own-voice work in progress |
| AI | In-app AI assistant for questions and support, on Bedrock inside the account (in progress); Scene Chat suggestions | In-app AI assistant (in progress); meanings from the personal graph via Bedrock (in progress); Comprehend Medical for symptoms and medicines with standard codes (planned) |
| PHI intake | Not planned | By email (with a confidentiality addendum on every message) or by secure upload in the app; files land encrypted in the account, logged, and are processed inside the boundary (in progress) |
| Data they share | **None.** Separate sign-in, database and storage | None |
| Beta research | Opt-in, participants by number not name, off by default | Same, with de-identified team figures |
| Next | Store apps after beta; Companion app, Coach app, Admin panel; FHIR layer (see below) | Store apps after beta; Companion app, Coach app, Admin panel; FHIR and Smile CDR appSphere for hospitals (see below) |
| GitHub | CodeConnections connection to the `linggollms` org, available | Same connection, created November 3 from the same GitHub App install |

## What is shared

**One code base.** Both products are the same application with different content, voices, tone and theme. A fix to the keyboard, the offline cache or the switch-access focus order lands in one repo and is pulled into the other. It is why two clinical products can move at the pace of one.

**One design system.** Logo, palette, type and icons live in `linggollms-design-system` and guide the apps, the website and the Notion workspace.

**One AWS Organization.** One Business Associate Addendum covers every account, now and later. One CloudTrail trail records every account into one private, encrypted bucket. GuardDuty, AWS Config with the HIPAA conformance pack (130 checks) and Security Hub run in the account that holds health data. The Aphasia account's environment is created from four CloudFormation templates (base network, services, app, graph) and one build script, plus two for Fargate; the ASD/IDD repo carries the same kit, so its hand-made first pieces can be rebuilt the same way, and a third product would get its own account the same way.

**One rule.** Only HIPAA-eligible AWS services touch what a person says. Any outside voice or AI service needs its own BAA or stays off by default. The one opt-in exception is the ElevenLabs character voices: off by default, not offered in accounts from healthcare organizations, library words voiced ahead of time and cached, a new word sent once and then cached, and disclosed in the [Privacy Policy](../policies.md). Every outside look at a person's information is recorded.

## What is kept apart

**Data.** The two products never share a database, a sign-in pool or a bucket. A child's words and an adult's words live in different accounts.

**Accounts.** The Aphasia product has its own AWS member account because it is the one heading into hospitals, where a HIPAA audit will want to see one boundary. The ASD/IDD product runs in the organization's main account (decided October 28, 2026), with its own sign-in pool, database, buckets and keys.

## Compute: ECS Fargate

Both app servers now have an ECS Fargate copy inside a private network, behind an HTTPS-only load balancer, with request and traffic logs kept a year and alarms (built October 30–31, 2026). App Runner, which the first AWS copies ran on in October, keeps serving until each app's web address is switched to the load balancer, then is paused and kept for a month as the way back: it is not on AWS's HIPAA-eligible list and runs outside the private network. Fargate is eligible, private, and lets the app server, the database and the graph talk without touching the internet.

## Where it stands, and what comes before real patients

Checked in the AWS console on November 3, 2026 (read-only): both accounts run one Fargate cluster with two tasks; both still serve through App Runner; both databases are single-zone; the Aphasia account has GuardDuty on with no findings, the HIPAA conformance pack deployed at 76% compliance and Security Hub on; the Aphasia Neptune cluster is built and stopped. The main account still holds an empty leftover Aphasia database and two paused Aphasia App Runner services from before the member account existed; they hold no user data and will be deleted. Nothing FHIR-related is built in either account.

As of November 3, 2026, no real patients use either app. Before they do: the web addresses switch to Fargate; the database API (PostgREST) moves off App Runner into the private network; the ASD/IDD database is rebuilt inside a private network from the CloudFormation kit; the databases get a standby in a second zone (Multi-AZ); a second internet exit (NAT) and AWS WAF go in front of the apps; and the open items in the HIPAA checks (secret rotation, storage access logs) are closed. Each app repo's `docs/architecture.md` holds the full list.

## The data layer

**Postgres is the record of everything.** Each product has its own RDS Postgres 16, reached through PostgREST with Cognito-issued tokens. Schema changes are versioned migrations rehearsed on a local Postgres before every deploy (139 in the Aphasia app, 114 in the ASD/IDD app, as of Nov 1, 2026).

**Neptune sits beside it** (Aphasia today) and links things so the app can understand one person better over time: a person → what they said → the words and pictures they used; each word → what it means for that person ("cold" meaning pain) → later a standard medical meaning (SNOMED CT); what they said → where they were (hospital, rehab, home); a person → the training they did → the words it practises. The person's own graph first; a shared, anonymous graph across people who opt in later. Reachable only inside the private network, IAM-only, every query audited and kept a year.

## AI, inside the boundary

Everything AI runs on Amazon Bedrock inside the AWS account that holds the data: Amazon Nova by default, Claude when unlocked. Nothing a person says leaves the account to reach a model.

**In progress, both apps: an AI assistant inside the app.** A small helper for questions and support: how do I add a word, why is the voice not playing, what does this setting do. It runs on Bedrock in the same account as the app, so a question that mentions a person's words stays inside the boundary.

**In progress, Aphasia: PHI intake by email and secure upload.** A person, family member or care team will be able to send files (a discharge summary, a therapy report, a word list) in two ways: by email to an address that lands them, encrypted, in the Aphasia account's storage with the receipt logged, or through a secure upload in the app, which is being added so that documents never have to travel through a mail provider at all. Every email Linggo LLMs sends carries a confidentiality addendum. From storage the files are processed inside the boundary: Comprehend Medical (planned) to find symptoms, medicines and standard codes; Bedrock with the person's own graph to work out what matters for their board. Nothing is processed outside AWS, and both paths are built on HIPAA-eligible services with the organization BAA covering them.

**In progress, Aphasia: meanings from the graph.** Bedrock reads a person's own graph to work out what they most likely mean, and proposes words and sentences accordingly.

## After the beta: store apps

Both products are web apps and home-screen PWAs today, on purpose: one build, every device, no store review between a fix and the people who need it. Native apps for the Apple App Store, Google Play and the Amazon Appstore (Fire tablets) come after the beta, built with Capacitor from the same code base. They will be offered first to the people who have had good experiences with Linggo over the years and want to explore the new AI features, so the first store reviews come from people who know what the app is for. Store apps also unlock what a bedside tablet needs: Guided Access on iPad, device management locks, a staff "End session" that clears the tablet without deleting the account.

## The lifelong account

The principle that drives all of this: the person owns their Linggo LLMs account for life. Someone with aphasia may first meet the app on a hospital tablet; their words, their meanings and their progress follow them to rehab, to outpatient therapy and home. A hospital, clinic or therapist is a care setting given access for a time; it never owns the account. A bedside tablet is only borrowed and is cleared for the next patient without deleting anything. Only the person, or a family member acting for them, can delete the account.

## Hospitals and payers: the FHIR layer (proposed, November 3, 2026)

Hospitals, clinics and payers exchange clinical data through HL7 FHIR R4. To work with them, each product account gets its own FHIR layer; the two never share one. Proposed, not built; the decision record is ADR-016.

```mermaid
flowchart TB
EXT["Hospital and clinic EHRs · Smile CDR appSphere · payer prior-auth APIs (CRD · DTR · PAS)"]
DME["DME supplier partner (future) · bills the device codes"]
subgraph ORG["AWS Organization · one BAA"]
direction LR
subgraph A["Main account · ASD/IDD"]
A1["Learner board · Companion · Coach · Admin<br/>ECS Fargate"] --> A2["FHIR connector in the app server<br/>consent check · mapping · audit"]
A2 --> A3["Smile CDR (proposed) · FHIR R4<br/>private subnet, own Postgres"]
A1 --> A4["RDS Postgres · S3 · Bedrock"]
A4 -. soon .-> A5["Neptune"]
end
subgraph P["Aphasia member account"]
P1["Learner board · Companion · Coach · Admin<br/>ECS Fargate"] --> P2["FHIR connector in the app server<br/>consent check · mapping · audit"]
P2 --> P3["Smile CDR (proposed) · FHIR R4<br/>private subnet, own Postgres"]
P1 --> P4["RDS Postgres · S3 · Bedrock · Neptune"]
end
end
A3 <--> EXT
P3 <--> EXT
A3 -- DeviceRequest + evaluation --> DME
P3 -- DeviceRequest + evaluation --> DME
```

**Where FHIR sits.** Beside Postgres, inside each account's private network, behind the same load balancer and WAF. A FHIR server (Smile CDR proposed, because the Coach app will be listed in Smile's appSphere and Smile's DTR and PAS modules cover the CMS-0057-F prior-authorization flow; AWS HealthLake is the fallback) runs in a private subnet with its own encrypted Postgres, reachable only by that account's app server. It is the single door to hospitals, payers and the future DME partner. Boards, every tap, voice, images and the Neptune graph stay in Linggo LLMs' own Postgres, Neptune and S3; only consented, minimum-necessary clinical data goes into FHIR, and the first version is a read-only SMART on FHIR launch.

**The new apps.** Companion (families and carers; consent on the person's behalf), Coach (SLPs, BCBAs, RBTs; a SMART on FHIR app launched from the hospital EHR, with the SLP evaluation template built in) and Admin (clinics, schools, hospitals; organizations, care teams, payer and coverage records) are routes in the shared code base, deployed in each account the same way the board is. The reimbursement rule that shapes them: insurance pays for equipment through a DME supplier, or a licensed clinician's live time under a plan of care; it does not pay for an app subscription. Codes live in `billing-codes.md`.

**Phases.**

1. **Harden and clean up.** Delete the leftovers in the main account; switch both web addresses to Fargate and retire App Runner; PostgREST into the private network; rebuild the ASD/IDD database from the CloudFormation kit; Multi-AZ, second NAT, WAF; close the open HIPAA checks.
2. **FHIR foundation.** Approve ADR-016; add a FHIR-server template to the kit, deploy Aphasia first; add the FHIR connector to the app server; map Consent, Coverage, ServiceRequest, QuestionnaireResponse and DocumentReference.
3. **Coach app and appSphere.** Coach with the SLP evaluation template and a read-only SMART launch; test on the Smile sandbox; apply to appSphere.
4. **Admin panel and the ASD/IDD graph.** Organizations, care teams, NPI and taxonomy, payer and coverage records; Neptune in the ASD/IDD account from the same template.
5. **Billing and prior authorization.** Settle who submits the request (Coach app or clinic EHR), the first payer target and the DME partner; CRD → DTR → PAS; re-check 2027 codes when the CY2027 fee schedule is final.
6. **Companion and store apps.** Companion with Consent and the lifelong account; iOS, Google Play and Amazon Appstore builds.

## Designed, not yet built

Companion app (parents and caregivers), Coach app (clinicians; the live version after the beta), Admin panel (clinics, schools, hospitals), store apps, hospital connections through FHIR and the Smile CDR appSphere gallery, the Neptune write path, the email PHI intake, the in-app assistants, and the rebuild of the ASD/IDD environment from the CloudFormation kit. All are specified in the Aphasia repo's `docs/` and in architecture decision records ADR-001 to ADR-015; the FHIR layer in the draft ADR-016 (`adr-016-fhir-layer.md`).
