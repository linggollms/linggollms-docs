# ADR-016: FHIR layer, one per product account

**Status:** Proposed
**Date:** November 3, 2026
**Decider:** Ling Ly Tan, Founder and CEO
**Related:** ADR-001 to ADR-015, `platform/architecture.md`, Notion: *Reimbursement, Prior Auth & FHIR Hub* (Nov 3, 2026)

## Context

Hospitals, clinics and payers exchange clinical data through HL7 FHIR R4. To work with them, Linggo LLMs needs:

1. A SMART on FHIR app that clinicians can launch from inside an EHR (Epic, Oracle Health, Smile CDR), and a listing in the Smile CDR appSphere gallery.
2. A way to send standard clinical records (goals, progress, AAC usage, evaluation reports) to the care team's EHR.
3. Documentation that supports billing and prior authorization. Under CMS-0057-F, impacted payers must offer FHIR prior-authorization APIs (CRD, DTR, PAS) by January 2027.
4. Three new apps for both products: Companion (families), Coach (clinicians) and Admin (organizations).

Current rules that still apply: each product lives in its own AWS account and the two never share data; only HIPAA-eligible services touch PHI; Postgres is the record of everything; the Neptune graph stays inside the account.

## Decision

1. **One FHIR layer per product account.** The ASD/IDD (main) account and the Aphasia member account each get their own FHIR store and gateway. Nothing FHIR-related is shared across accounts.
2. **FHIR store: Smile CDR (FHIR R4), proposed; AWS HealthLake as fallback.** Smile CDR is preferred because the Coach app will be listed in Smile's appSphere and its DTR and PAS modules cover the CMS-0057-F prior-authorization flow. It runs in a private subnet with its own encrypted Postgres, reachable only by the app server, created from a new CloudFormation template. Whether it is installed in-account or Smile-managed on AWS, and the BAA with Smile Digital Health, are open; if licensing or hosting does not fit a startup, HealthLake takes its place with the same boundary.
3. **Postgres stays the record of everything.** Boards, every tap, voice and images stay in Linggo's Postgres and S3. The FHIR store holds only consented, minimum-necessary clinical data, written through the app.
4. **FHIR connector inside the app server on ECS Fargate.** It checks the Learner's Consent before any FHIR write, maps Linggo records to FHIR resources, and writes an append-only access log entry for every read and write, kept one year. Clinician sign-in uses a staff Cognito pool federated to hospital identity; Learners and Companions use their own pool.
5. **Neptune never leaves the account.** Only summaries derived from the graph (for example, an Observation of vocabulary growth) become FHIR resources. The graph itself and the patented word-tree logic stay internal.
6. **The new apps are routes in the shared code base,** deployed in each account the same way the Learner board is. Coach and Admin use the FHIR connector. The Learner board and Companion talk to Postgres as today. The SLP evaluation template is built into the Coach app (decided Nov 3, 2026) and supplies the DTR answers.
7. **First version is read-only SMART launch.** Write scopes (ServiceRequest, QuestionnaireResponse, Claim) come later, agreed per hospital and payer. Whether the Coach app or the clinic EHR submits the PAS request is open. Speech-generating devices (E2510/E2511) are billed by a DME supplier partner, not by Linggo LLMs.

## First resource mapping

| Linggo record | FHIR resource | Written by |
|---|---|---|
| Learner's time-limited grant to a Coach or organization | Consent | Learner / Companion |
| Learner's plan and member number | Coverage | Admin |
| Orders for AAC evaluation (92605/92607/92608/92618), therapy, Companion training (97550–97552, 97156) | ServiceRequest | Coach |
| Answers from the Coach SLP evaluation template | QuestionnaireResponse (DTR) | Coach |
| Signed evaluation report and attachments | DocumentReference | Coach |
| Order for E2511 / E2510 / E2599 / E2512 | DeviceRequest, routed to the DME partner | Coach |
| Prior-auth request and payer decision | Claim (preauthorization) / ClaimResponse (PAS) | Coach app or clinic EHR (open) |
| Missing documents, appeals, renewals | Task | Admin |
| Clinician, clinic, care team | Practitioner, PractitionerRole, Organization, CareTeam | Admin |

Not in FHIR: boards, taps, the Neptune graph, voice and images. Remote-monitoring (RTM) codes do not fit AAC today, so no RTM Observations are planned.

## Options considered

| Option | For | Against |
|---|---|---|
| **Smile CDR in-account** (proposed) | Same vendor as appSphere; DTR and PAS modules; full control of the boundary | Licence cost; Linggo runs and patches it; BAA with Smile needed |
| Smile CDR managed on AWS | Less to run; Smile operates it | Data leaves Linggo's account; needs a BAA and a clear boundary; cost |
| AWS HealthLake (fallback) | Managed, HIPAA-eligible, in-account, little to run | No DTR/PAS modules; appSphere listing must be done separately |
| Self-run HAPI FHIR | Free software, full control | Linggo builds the prior-auth flow itself |
| One FHIR store for both products | Less to run | Breaks the rule that the products never share data; the hub notes ASD/IDD sits in the management account and needs its own instance or a move |

## Consequences

- Adds a FHIR-server CloudFormation template (private subnet, own encrypted Postgres) to the kit, deployed Aphasia first, then ASD/IDD.
- Adds the FHIR server and connector to the HIPAA conformance pack and Security Hub scope in both accounts.
- Requires the Phase 0 hardening first: Fargate DNS switch, private PostgREST, second availability zone, 35-day backups, WAF.
- Revisit if Smile licensing or hosting does not fit, or if the first hospital partner requires a different server.

## Open questions

1. Smile CDR hosting: in-account install or Smile-managed on AWS, and on what licensing terms; standard BAA terms.
2. CRD: a Smile module, or part of the payer package? PAS early-access timeline for a provider-side vendor.
3. Who submits the PAS request: the Coach app directly, or the clinic EHR with Linggo supplying the evaluation?
4. First payer target: Medicare, Medicaid or commercial.
5. One Smile CDR instance per product (this ADR), confirmed with Smile for multi-product licensing.
6. DME partner candidates and PDAC coding guidance for a locked Linggo device.
