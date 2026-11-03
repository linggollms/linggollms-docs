# Billing codes: AAC, therapy and training

Mirror of the Notion database *CMS Codes | AAC, Therapy and Online Courses / Training* as of November 3, 2026. Notion is the source of truth; this file is a readable copy for the platform docs.

> Research, not legal or billing advice. A certified coder or reimbursement consultant must review before any claim. No PHI. Rows marked **Needs check** have not been re-verified against CMS or ASHA; **High risk** rows have a known fit problem described in the notes.

## The rule that shapes everything

Insurance pays for (a) equipment through an enrolled DME supplier, or (b) a licensed clinician's live time under a plan of care. It does not pay for an app subscription or self-paced courses on their own. Each Linggo LLMs feature has to attach to one of those two paths. Speech-generating devices (E2510/E2511) are billed by a DME supplier partner, not by Linggo LLMs.

## Key findings (Nov 3, 2026)

- CPT 92507 is deleted on January 1, 2027. The timed replacements 92654–92663 have proposed Medicare values; the CY2027 PFS final rule is pending.
- Online courses on their own are not billable. Only live clinician time is.
- No remote-monitoring (RTM) code fits AAC use today. E2511 pays for software only; the tablet is A9270 and not covered.
- Payers covered by CMS-0057-F must offer prior-authorization APIs by January 1, 2027.

## Summary table

| Code | Type | Category | Description | Products | Roles | Who bills | Prior auth | Telehealth | Timed | Status | Verified |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 92605 | CPT | AAC evaluation | Evaluation for prescription of a non-speech-generating AAC device (e.g. picture board), face-to-face, first hour | Aphasia, ASD/IDD | Learner, Coach, Admin | SLP | Varies by payer | Payer-dependent | Yes | Needs check |  |
| 92607 | CPT | AAC evaluation | AAC (speech generating device) evaluation, first hour | Aphasia, ASD/IDD | Learner, Coach, Admin | Speech-language pathologist (SLP) | Varies by payer | Payer-dependent | Yes | Needs check |  |
| 92608 | CPT | AAC evaluation | AAC evaluation, each extra 30 minutes | Aphasia, ASD/IDD | Learner, Coach, Admin | SLP | Varies by payer | Payer-dependent | Yes | Needs check |  |
| 92618 | CPT | AAC evaluation | Non-speech-generating AAC device evaluation, each additional 30 minutes | Aphasia, ASD/IDD | Learner, Coach, Admin | SLP | Varies by payer | Payer-dependent | Yes | Needs check |  |
| 92606 | CPT | AAC therapy | Therapy for a non-speech AAC device, including programming | Aphasia, ASD/IDD | Learner, Companion, Coach, Admin | SLP | Varies by payer | Payer-dependent |  | Needs check |  |
| 92609 | CPT | AAC therapy | Therapy for using a speech generating device, including programming and changes | Aphasia, ASD/IDD | Learner, Companion, Coach, Admin | SLP | Varies by payer | Payer-dependent |  | Needs check |  |
| E2512 | HCPCS | Accessory | Mounting system for a speech generating device | Aphasia, ASD/IDD | Learner, Admin | Equipment supplier (DME) | Usually required | Not a visit (remote/async) |  | Verified | 2026-11-03 |
| E2599 | HCPCS | Accessory | Accessories for a speech generating device, such as switches and switch interfaces | Aphasia, ASD/IDD | Learner, Admin | Equipment supplier (DME) | Usually required | Not a visit (remote/async) |  | Verified | 2026-11-03 |
| 97151 | CPT | Behavioral therapy (ABA) | Behavior identification assessment | ASD/IDD | Learner, Coach, Admin | BCBA or qualified professional | Usually required | Payer-dependent | Yes | Needs check |  |
| 97152 | CPT | Behavioral therapy (ABA) | Supporting behavior assessment by a technician | ASD/IDD | Learner, Coach, Admin | Technician under a BCBA | Usually required | In person only | Yes | Needs check |  |
| 97153 | CPT | Behavioral therapy (ABA) | Adaptive behavior treatment by protocol, by a technician | ASD/IDD | Learner, Coach, Admin | Technician under a BCBA | Usually required | In person only | Yes | Needs check |  |
| 97154 | CPT | Behavioral therapy (ABA) | Group adaptive behavior treatment by protocol, by a technician | ASD/IDD | Learner, Coach, Admin | Technician under a BCBA | Usually required | In person only | Yes | Needs check |  |
| 97155 | CPT | Behavioral therapy (ABA) | Adaptive behavior treatment with protocol changes, by a qualified professional | ASD/IDD | Learner, Coach, Admin | BCBA | Usually required | Payer-dependent | Yes | Needs check |  |
| 97156 | CPT | Behavioral therapy (ABA) | Family adaptive behavior treatment guidance (caregiver training in ABA) | ASD/IDD | Companion, Coach, Admin | BCBA | Usually required | Payer-dependent | Yes | Needs check |  |
| 97157 | CPT | Behavioral therapy (ABA) | Group family adaptive behavior guidance (several families) | ASD/IDD | Companion, Coach, Admin | BCBA | Usually required | Payer-dependent | Yes | Needs check |  |
| 97158 | CPT | Behavioral therapy (ABA) | Group adaptive behavior treatment with protocol changes, by a qualified professional | ASD/IDD | Learner, Coach, Admin | BCBA | Usually required | In person only | Yes | Needs check |  |
| 96202 / 96203 | CPT | Caregiver training | Group caregiver behavior management/modification training, without the patient present: first 60 minutes (96202), each additional 30 minutes (96203) | ASD/IDD | Companion, Coach, Admin | Physician/NPP or qualified clinician (check scope; ABA payers may prefer 97156/97157) | Varies by payer | Payer-dependent | Yes | Needs check |  |
| 97535 | CPT | Caregiver training | Self-care/home management training, direct one-on-one, each 15 minutes (patient present) | Aphasia, ASD/IDD | Learner, Companion, Coach | OT/PT mainly; SLP use varies by payer | Varies by payer | Payer-dependent | Yes | Needs check |  |
| 97550 | CPT | Caregiver training | Caregiver training in strategies and techniques to facilitate the patient's functional performance (incl. communication), without the patient present, face-to-face, first 30 minutes | Aphasia, ASD/IDD | Companion, Coach, Admin | Physician/NPP, or PT/OT/SLP under their plan of care | Varies by payer | Medicare telehealth list | Yes | Needs check |  |
| 97551 | CPT | Caregiver training | Caregiver training, each extra 15 minutes | Aphasia, ASD/IDD | Companion, Coach, Admin | Physician/NPP, or PT/OT/SLP under their plan of care | Varies by payer | Medicare telehealth list | Yes | Needs check |  |
| 97552 | CPT | Caregiver training | Group caregiver training (several caregivers) | Aphasia, ASD/IDD | Companion, Coach, Admin | Physician/NPP, or PT/OT/SLP under their plan of care | Varies by payer | Medicare telehealth list |  | Needs check |  |
| G0539 / G0540 | HCPCS | Caregiver training | Individual caregiver behavior management/modification training, without the patient present: first 30 minutes (G0539), each additional 15 minutes (G0540) | ASD/IDD, Aphasia | Companion, Coach, Admin | Physician/NPP or qualified clinician under plan of care | Not usually | Payer-dependent | Yes | Needs check |  |
| G0541 | HCPCS | Caregiver training | Caregiver training in direct care strategies and techniques to support care for patients with an ongoing condition or illness and to reduce complications (including, but not limited to, techniques to prevent decubitus ulcer formation, wound care, and infection control) (without the patient present), face-to-face; initial 30 minutes. | Aphasia, ASD/IDD | Companion, Coach, Admin | Physician/NPP, or PT/OT/SLP under plan of care | Not usually | Payer-dependent | Yes | Verified | 2026-11-03 |
| G0542 | HCPCS | Caregiver training | Caregiver training in direct care strategies and techniques to support care for patients with an ongoing condition or illness and to reduce complications (…) (without the patient present), face-to-face; each additional 15 minutes (list separately in addition to code for primary service) (use G0542 in conjunction with G0541). | Aphasia, ASD/IDD | Companion, Coach, Admin | Physician/NPP, or PT/OT/SLP under plan of care | Not usually | Payer-dependent | Yes | Verified | 2026-11-03 |
| G0543 | HCPCS | Caregiver training | Group caregiver training in direct care strategies and techniques to support care for patients with an ongoing condition or illness and to reduce complications (…) (without the patient present), face-to-face with multiple sets of caregivers. Untimed; billed per patient represented. | Aphasia, ASD/IDD | Companion, Coach, Admin | Physician/NPP, or PT/OT/SLP under plan of care | Not usually | Payer-dependent |  | Verified | 2026-11-03 |
| 96125 | CPT | Cognitive | Standardized cognitive performance testing, per hour | Aphasia | Learner, Coach, Admin | SLP or psychologist | Not usually | Payer-dependent | Yes | Needs check |  |
| 97129 | CPT | Cognitive | Cognitive function intervention, first 15 minutes | Aphasia | Learner, Coach, Admin | SLP, OT or psychologist | Varies by payer | Payer-dependent | Yes | Needs check |  |
| 97130 | CPT | Cognitive | Cognitive function intervention, each extra 15 minutes | Aphasia | Learner, Coach, Admin | SLP, OT or psychologist | Varies by payer | Payer-dependent | Yes | Needs check |  |
| A9270 | HCPCS | Device | Non-covered item or service. Per DME policy article A52469, a general computing device (tablet, smartphone, laptop) running E2511 software must be coded A9270 — Medicare does not pay for the hardware. | Aphasia, ASD/IDD | Learner, Admin | DME supplier | Not usually | Not a visit (remote/async) |  | Verified | 2026-11-03 |
| E2500 to E2506 | HCPCS | Device | Speech generating devices, digitized speech (recorded words), by recording time | Aphasia, ASD/IDD | Learner, Coach, Admin | Equipment supplier (DME) | Usually required | Not a visit (remote/async) |  | Verified | 2026-11-03 |
| E2508 | HCPCS | Device | Speech generating device, synthesized speech, one way to build messages and one way to access | Aphasia, ASD/IDD | Learner, Coach, Admin | Equipment supplier (DME) | Usually required | Not a visit (remote/async) |  | Verified | 2026-11-03 |
| E2510 | HCPCS | Device | Speech generating device, synthesized speech, several ways to build messages and several ways to access (touch, switch, eye gaze) | Aphasia, ASD/IDD | Learner, Coach, Admin | Equipment supplier (DME) | Usually required | Not a visit (remote/async) |  | Verified | 2026-11-03 |
| E2511 | HCPCS | Device | Speech generating software program, for personal computer or personal digital assistant. Medicare pays the software only when installed on a general computing device; the device itself is coded A9270 (non-covered). Installation/tech support not separately billable. Requires KX (or GA/GZ) modifier. | Aphasia, ASD/IDD | Learner, Coach, Admin | Equipment supplier (DME) | Usually required | Not a visit (remote/async) |  | High risk | 2026-11-03 |
| Modifiers GN, KX, 95; POS 02 / 10 | HCPCS | Modifier / place of service | GN = services delivered under an outpatient SLP plan of care (Medicare). KX = attestation that therapy above the annual threshold is medically necessary: CY2026 $2,480 PT+SLP combined; CY2027 proposed $2,540; targeted medical review at $3,000 through CY2027. On DME (E2500–E2599) KX = LCD criteria met (GA/GZ otherwise). 95 = synchronous telehealth (payer-specific). POS 10 = telehealth in patient home; POS 02 = telehealth elsewhere. CY2027 NPRM also proposes new telehealth modifiers BB/BC — pending. | Aphasia, ASD/IDD | Coach, Admin | Any billing clinician | Not usually | Payer-dependent |  | Needs check | 2026-11-03 |
| 98975, 98980, 98981 | CPT | Remote monitoring | RTM: 98975 initial setup and patient education; 98980 treatment management first 20 minutes per calendar month; 98981 each additional 20 minutes | Aphasia, ASD/IDD | Learner, Companion, Coach | Physician/NPP; PT/OT/SLP only under a therapy plan of care | Not usually | Not a visit (remote/async) | Yes | High risk | 2026-11-03 |
| 98979, 98984, 98985 | CPT | Remote monitoring | 98979: RTM treatment management services, physician or other QHP time in a calendar month requiring at least 1 real-time interactive communication with the patient or caregiver; first 10 minutes. 98984: RTM device(s) supply … respiratory system, 2–15 days in a 30-day period. 98985: RTM device(s) supply … musculoskeletal system, 2–15 days in a 30-day period. (98986 = cognitive behavioral therapy, 2–15 days, also new 2026.) 98979 not combinable with 98980 same month; 2–15 and 16–30 day supply codes mutually exclusive. | Aphasia, ASD/IDD | Learner, Companion, Coach | Physician/NPP; PT/OT/SLP only under a therapy plan of care | Not usually | Not a visit (remote/async) | Yes | High risk | 2026-11-03 |
| G0552 / G0553 / G0554 (DMHT) | HCPCS | Remote monitoring | G0552 supply of digital mental health treatment device and initial education/onboarding, per course of treatment (contractor-priced); G0553 first 20 min/month treatment management incl. ≥1 interactive communication; G0554 each additional 20 min. Limited to FDA-cleared devices under 21 CFR 882.5801 (psychiatric) and, from 2026, 882.5803 (ADHD), furnished incident to a behavioral health plan of care. | ASD/IDD, Aphasia | Learner, Coach | Behavioral health practitioner with prescribing authority | Varies by payer | Not a visit (remote/async) |  | High risk | 2026-11-03 |
| 92507 | CPT | Speech therapy | Treatment of speech, language, voice, communication, and/or auditory processing disorder; individual. DELETED from CPT effective 1 Jan 2027 — valid for dates of service through 31 Dec 2026 only. | Aphasia, ASD/IDD | Learner, Coach, Admin | SLP | Varies by payer | Payer-dependent |  | Ending 2026 | 2026-11-03 |
| 92508 | CPT | Speech therapy | Speech, language, voice and communication treatment, group | Aphasia, ASD/IDD | Learner, Coach, Admin | SLP | Varies by payer | Payer-dependent |  | Needs check |  |
| 92521 | CPT | Speech therapy | Evaluation of speech fluency (stuttering) | Aphasia, ASD/IDD | Coach, Admin | SLP | Not usually | Payer-dependent |  | Needs check |  |
| 92522 | CPT | Speech therapy | Evaluation of speech sound production | Aphasia, ASD/IDD | Coach, Admin | SLP | Not usually | Payer-dependent |  | Needs check |  |
| 92523 | CPT | Speech therapy | Evaluation of speech sound production plus language comprehension and expression | Aphasia, ASD/IDD | Coach, Admin | SLP | Not usually | Payer-dependent |  | Needs check |  |
| 92524 | CPT | Speech therapy | Voice and resonance evaluation | Aphasia | Coach, Admin | SLP | Not usually | Payer-dependent |  | Needs check |  |
| 92526 | CPT | Speech therapy | Treatment of swallowing and oral function for feeding | Aphasia, ASD/IDD | Coach, Admin | SLP | Varies by payer | Payer-dependent |  | Needs check |  |
| 92654 to 92663 (2027) | CPT | Speech therapy | CPT 2027 individual SLP treatment, timed, direct one-on-one: 92654/92655 fluency; 92656/92657 speech sound production; 92658/92659 language comprehension and expression; 92660/92661 combined speech sound + language; 92662/92663 voice, upper airway dysfunction and/or resonance. Base = initial 30 min, add-on = each additional 15 min. 92508 (group) stays untimed. Medicare values PROPOSED (CY2027 PFS NPRM, CF $32.8409); final rule expected early Nov 2026 — not yet confirmed. CMS also proposed Medicare-only pediatric code GSLPP (see row). | Aphasia, ASD/IDD | Learner, Coach, Admin | SLP | Varies by payer | Payer-dependent | Yes | Effective 2027 | 2026-11-03 |
| 96105 | CPT | Speech therapy | Assessment of aphasia, per hour | Aphasia | Learner, Coach, Admin | SLP or psychologist | Not usually | Payer-dependent | Yes | Needs check |  |
| GSLPP (proposed 2027) | HCPCS | Speech therapy | PROPOSED Medicare-only HCPCS G-code for individual pediatric SLP treatment (CY2027 PFS NPRM). Untimed, valued on 92507 inputs, work RVU 1.30 (~60 min), once per patient per day, always therapy, MPPR applies; proposed for Medicare telehealth list. ASHA opposes. Final status pending CY2027 final rule. | ASD/IDD | Learner, Coach, Admin | SLP (Medicare) | Varies by payer | Payer-dependent |  | High risk | 2026-11-03 |

## Details by category

### AAC evaluation

#### 92605 (CPT)

Evaluation for prescription of a non-speech-generating AAC device (e.g. picture board), face-to-face, first hour

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Timed, first hour; add-on 92618 for each extra 30 minutes. SLP, face-to-face; written report with device recommendation. GN modifier (Medicare).
- **How Linggo LLMs uses it:** Low-tech backup boards (printed from the Learner's board) for ER/ICU, power loss or eye-gaze fatigue. Aphasia and ASD/IDD; inpatient bundled, outpatient billable.
- **Online / async training coverage:** Live SLP eval; low-tech boards (printable from Linggo LLMs boards) fit here.
- **FHIR record:** ServiceRequest; QuestionnaireResponse
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/)
- **Sources:** ASHA Medicare coding rules; ASHA Leader 'Billing for AAC'.

#### 92607 (CPT)

AAC (speech generating device) evaluation, first hour

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Example ICD-10:** R47.01/I69.320; S06.- sequela; F84.0; F70–F79; F03.9-
- **Requirements:** Face-to-face. Written report covering impairment, language and thinking, why natural speech can't meet needs, devices tried, chosen device, training plan. Required before any device claim.
- **How Linggo LLMs uses it:** Generated by the Coach app SLP evaluation template (decided 2026-11-03); output = LCD L33739 evaluation for the DME partner.
- **Online / async training coverage:** Live SLP face-to-face evaluation; telehealth payer-dependent. Output must contain the 7 LCD elements (impairment, natural-mode assessment, goals, device rationale, training schedule, etc.).
- **FHIR record:** ServiceRequest; QuestionnaireResponse (evaluation); DocumentReference (signed report)
- **Change log:** 2026-11-03: Added fields. 2026-11-03 (later): Linked to Coach eval template spec.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/) · [Policy document](https://www.cms.gov/medicare-coverage-database/view/lcd.aspx?LCDId=33739)
- **Sources:** Medicare LCD L33739; policy article A52469; ASHA Medicare coding rules.

#### 92608 (CPT)

AAC evaluation, each extra 30 minutes

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Add-on to 92607 only, each additional 30 minutes, same session; time documented. Never billed alone.
- **How Linggo LLMs uses it:** Long evaluations, e.g. eye-gaze calibration and switch trials. Coach app timer should capture start/stop.
- **Online / async training coverage:** Add-on to 92607; live only.
- **FHIR record:** ServiceRequest
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/) · [Policy document](https://www.cms.gov/medicare-coverage-database/view/lcd.aspx?LCDId=33739)
- **Sources:** ASHA Medicare coding rules; LCD L33739.

#### 92618 (CPT)

Non-speech-generating AAC device evaluation, each additional 30 minutes

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Add-on to 92605 only; time documented; same session.
- **How Linggo LLMs uses it:** Long low-tech board evaluations.
- **Online / async training coverage:** Add-on to 92605; live only.
- **FHIR record:** ServiceRequest
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/)
- **Sources:** ASHA Medicare coding rules.

### AAC therapy

#### 92606 (CPT)

Therapy for a non-speech AAC device, including programming

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Untimed therapy for use of a non-speech-generating AAC device, including programming; SLP; plan of care; GN modifier. Check NCCI edits with 92507 on the same day.
- **How Linggo LLMs uses it:** Training on printed/low-tech boards generated from the app; outpatient.
- **Online / async training coverage:** Live SLP therapy with patient; Companion may attend. Not a course.
- **FHIR record:** ServiceRequest; CarePlan
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/)
- **Sources:** ASHA Medicare coding rules.

#### 92609 (CPT)

Therapy for using a speech generating device, including programming and changes

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Example ICD-10:** R47.01/I69.320; S06.- sequela; F84.0; F70–F79; F03.9-
- **Requirements:** Part of a plan of care; only when working on the device itself. Check bundling edits with 92507.
- **How Linggo LLMs uses it:** Outpatient core code after the device is in place: Coach programs boards, tunes dwell/scan settings, trains access. Inpatient: bundled. Usage data from the board supports progress notes.
- **Online / async training coverage:** Live SLP therapy for SGD use incl. programming/modification. Board programming done async by Coach without patient is generally not billable time — verify per payer.
- **FHIR record:** ServiceRequest; CarePlan; Observation (progress)
- **Change log:** 2026-11-03: Added fields. Core AAC treatment code for Learner app sessions; NOT replaced in 2027 (only 92507 is).
- **Links:** [Reference](https://leader.pubs.asha.org/doi/10.1044/leader.BML.22022017.36) · [Policy document](https://www.cms.gov/medicare-coverage-database/view/lcd.aspx?LCDId=33739)
- **Sources:** ASHA Leader 'Billing for AAC'; ASHA Medicare coding rules; LCD L33739.

### Accessory

#### E2512 (HCPCS)

Mounting system for a speech generating device

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Home/community
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Need documented in the SLP evaluation.
- **How Linggo LLMs uses it:** Wheelchair/bed mounts for tablets running Linggo LLMs, important for ICU and limited-mobility users.
- **Online / async training coverage:** N/A (DME).
- **FHIR record:** DeviceRequest
- **Change log:** 2026-11-03: Accessory must meet base-SGD criteria 1–7; KX/GA/GZ required.
- **Links:** [Policy document](https://www.cms.gov/medicare-coverage-database/view/article.aspx?articleId=52469)
- **Sources:** LCD L33739; A52469; Colorado DMEPOS manual.

#### E2599 (HCPCS)

Accessories for a speech generating device, such as switches and switch interfaces

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Home/community
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Need written in the SLP evaluation (for example, can't use touch, needs a switch or eye gaze).
- **How Linggo LLMs uses it:** Switches, switch interfaces and eye-gaze accessories used with the Linggo LLMs app when touch isn't possible. Need documented in 92607 report.
- **Online / async training coverage:** N/A (DME). Switch/eye-gaze access in Learner app should be WCAG 2.2 AA (2.5.7 dragging, 2.5.8 target size).
- **FHIR record:** DeviceRequest
- **Change log:** 2026-11-03: Alternative input devices covered when beneficiary cannot use standard input (LCD). Software bundled with access device not separately billable as E2511.
- **Links:** [Policy document](https://www.cms.gov/medicare-coverage-database/view/lcd.aspx?LCDId=33739)
- **Sources:** LCD L33739; A52469; Colorado DMEPOS manual.

### Behavioral therapy (ABA)

#### 97151 (CPT)

Behavior identification assessment

- **Populations:** Autism, IDD
- **Settings:** Outpatient, Telehealth, Home/community
- **Coverage:** Medicaid, Commercial
- **Example ICD-10:** F84.0; F70–F79
- **Requirements:** Timed, 15-minute units; BCBA or qualified health care professional; diagnosis (often autism); assessment report and treatment plan; prior auth usually required (Medicaid EPSDT under 21, commercial under state autism mandates). Traditional Medicare rarely pays.
- **How Linggo LLMs uses it:** ASD/IDD line: BCBA assessment that sets communication (manding) goals using the Learner's board; data from taps.
- **Online / async training coverage:** Assessment by BCBA; telehealth allowed by some payers. AAC/mand assessment can be part of plan.
- **FHIR record:** ServiceRequest; CarePlan
- **Change log:** 2026-11-03: Added fields.
- **Sources:** AMA CPT adaptive behavior code set; state Medicaid ABA manuals (state-specific, not yet linked).

#### 97152 (CPT)

Supporting behavior assessment by a technician

- **Populations:** Autism, IDD
- **Settings:** Outpatient, Home/community
- **Coverage:** Medicaid, Commercial
- **Example ICD-10:** F84.0 autism; F70–F79 IDD (many state Medicaid ABA benefits are autism-only via EPSDT — IDD-only coverage varies)
- **Requirements:** Timed, 15-minute units; technician under BCBA direction; face-to-face with the Learner; prior auth usually required.
- **How Linggo LLMs uses it:** ASD/IDD line: technician-collected assessment data captured in the app.
- **Online / async training coverage:** Technician-delivered with patient; not a course.
- **FHIR record:** ServiceRequest
- **Change log:** 2026-11-03: Added fields.
- **Sources:** AMA CPT adaptive behavior code set.

#### 97153 (CPT)

Adaptive behavior treatment by protocol, by a technician

- **Populations:** Autism, IDD
- **Settings:** Outpatient, Home/community, School (research)
- **Coverage:** Medicaid, Commercial
- **Example ICD-10:** F84.0; F70–F79
- **Requirements:** Timed, 15-minute units; technician by protocol under BCBA; authorized hours; session notes. From 2027 the new SLP treatment codes cannot be billed with 97153/97155 (coordinate same-day schedules).
- **How Linggo LLMs uses it:** ASD/IDD line: technician runs communication programs on the board; taps become trial data.
- **Online / async training coverage:** In-person technician session; Learner app usage can be data source, not billable itself.
- **FHIR record:** ServiceRequest; Observation
- **Change log:** 2026-11-03: Added fields.
- **Sources:** AMA CPT adaptive behavior code set; secondary reports on CPT 2027 edits (verify in codebook).

#### 97154 (CPT)

Group adaptive behavior treatment by protocol, by a technician

- **Populations:** Autism, IDD
- **Settings:** Outpatient, Home/community, School (research)
- **Coverage:** Medicaid, Commercial
- **Example ICD-10:** F84.0; F70–F79
- **Requirements:** Timed, 15-minute units; technician by protocol, 2–8 patients; prior auth usually required.
- **How Linggo LLMs uses it:** ASD/IDD group sessions.
- **Online / async training coverage:** In-person group only.
- **FHIR record:** ServiceRequest
- **Change log:** 2026-11-03: Added fields.
- **Sources:** AMA CPT adaptive behavior code set.

#### 97155 (CPT)

Adaptive behavior treatment with protocol changes, by a qualified professional

- **Populations:** Autism, IDD
- **Settings:** Outpatient, Telehealth, Home/community
- **Coverage:** Medicaid, Commercial
- **Example ICD-10:** F84.0; F70–F79
- **Requirements:** Timed, 15-minute units; BCBA/QHP; face-to-face with the Learner; may direct a technician; prior auth usually required.
- **How Linggo LLMs uses it:** ASD/IDD line: BCBA modifies the communication protocol (e.g. board layout, prompting) based on app data.
- **Online / async training coverage:** BCBA protocol modification; telehealth commonly allowed for the BCBA portion (payer-dependent). Coach app board edits during session can be documented here.
- **FHIR record:** ServiceRequest; CarePlan
- **Change log:** 2026-11-03: Added fields.
- **Sources:** AMA CPT adaptive behavior code set.

#### 97156 (CPT)

Family adaptive behavior treatment guidance (caregiver training in ABA)

- **Populations:** Autism, IDD
- **Settings:** Outpatient, Telehealth, Home/community
- **Coverage:** Medicaid, Commercial
- **Example ICD-10:** F84.0; F70–F79
- **Requirements:** Timed, 15-minute units; BCBA/QHP; with or without the Learner present; one family; prior auth usually required; goals tied to the treatment plan.
- **How Linggo LLMs uses it:** ASD/IDD line: live Companion coaching by the BCBA, in person or by video; Companion app shows assigned modules and practice data.
- **Online / async training coverage:** Live BCBA guidance of parent/guardian (with or without patient); telehealth widely allowed by Medicaid/commercial ABA policies but verify. Self-paced Companion courses not billable; may support private-pay or employer/plan-funded parent-training licenses.
- **FHIR record:** CarePlan + Task; Communication; RelatedPerson
- **Change log:** 2026-11-03: Added fields. Primary ABA caregiver-training code for Companion app.
- **Sources:** AMA CPT adaptive behavior code set; CMS telehealth list (code listed for 2026, verify).

#### 97157 (CPT)

Group family adaptive behavior guidance (several families)

- **Populations:** Autism, IDD
- **Settings:** Outpatient, Telehealth
- **Coverage:** Medicaid, Commercial
- **Example ICD-10:** F84.0; F70–F79
- **Requirements:** Timed, 15-minute units; BCBA/QHP; multiple families, without the Learners present; prior auth usually required.
- **How Linggo LLMs uses it:** ASD/IDD line: group parent training cohorts (could run as live online cohorts).
- **Online / async training coverage:** Live multi-family group (patients absent); live virtual cohort may qualify where payer allows telehealth.
- **FHIR record:** CarePlan + Task
- **Change log:** 2026-11-03: Added fields.
- **Sources:** AMA CPT adaptive behavior code set.

#### 97158 (CPT)

Group adaptive behavior treatment with protocol changes, by a qualified professional

- **Populations:** Autism, IDD
- **Settings:** Outpatient, School (research)
- **Coverage:** Medicaid, Commercial
- **Example ICD-10:** F84.0; F70–F79
- **Requirements:** Timed, 15-minute units; BCBA/QHP; group with protocol modification; prior auth usually required. From 2027, 92508 cannot be billed with 97154/97158.
- **How Linggo LLMs uses it:** ASD/IDD group social-communication sessions led by the BCBA.
- **Online / async training coverage:** In-person group only.
- **FHIR record:** ServiceRequest
- **Change log:** 2026-11-03: Added fields.
- **Sources:** AMA CPT adaptive behavior code set.

### Caregiver training

#### 96202 / 96203 (CPT)

Group caregiver behavior management/modification training, without the patient present: first 60 minutes (96202), each additional 30 minutes (96203)

- **Populations:** Autism, IDD, Dementia, TBI
- **Settings:** Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Group of caregivers; patients not present; consent documented; bill once per patient represented. Medicare-recognized since 1 Jan 2024.
- **How Linggo LLMs uses it:** ASD/IDD line: live group behavior-support classes for Companions. Check whether a BCBA can bill this with each payer.
- **Online / async training coverage:** Live group caregiver behavior training. Not a course.
- **FHIR record:** CarePlan + Task; RelatedPerson
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Policy document](https://www.cms.gov/files/document/health-related-social-needs-faq.pdf)
- **Sources:** CMS HRSN FAQ (CTS codes and group billing example).

#### 97535 (CPT)

Self-care/home management training, direct one-on-one, each 15 minutes (patient present)

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Inpatient, Outpatient, Home/community
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Timed, patient present; plan of care. Many payers don't accept it from SLPs.
- **How Linggo LLMs uses it:** OT partner code for daily routines using the board (e.g. schedules). Not a primary SLP code.
- **Online / async training coverage:** Live, patient present. Not a course.
- **FHIR record:** ServiceRequest
- **Change log:** 2026-11-03: Added fields.
- **Sources:** AMA CPT; payer policies (verify).

#### 97550 (CPT)

Caregiver training in strategies and techniques to facilitate the patient's functional performance (incl. communication), without the patient present, face-to-face, first 30 minutes

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Outpatient, Telehealth, Home/community
- **Coverage:** Medicare, Medicaid, Commercial
- **Example ICD-10:** Patient's dx (I69.320, R47.01, F84.0, F70–F79, F03.9-, S06.- sequela)
- **Requirements:** Full 30 minutes required (Medicare). Patient NOT present. Patient (or representative) consent documented in the record; verbal is enough, signed form not required. Training tied to an individualized plan of care and functional goals; need for each occurrence documented. Billed once per patient regardless of how many caregivers attend. Caregiver = unpaid family member/friend. GN modifier for SLP. Part B deductible/coinsurance apply.
- **How Linggo LLMs uses it:** Primary code-based coverage for the Companion: a Coach-led live session (in person or telehealth) training the Companion on the Learner's AAC, billed to the Learner's insurance. Companion app courses serve as documented pre-work/homework.
- **Online / async training coverage:** Live, face-to-face (in person or real-time audio-video) SLP/OT/PT training of Companion, patient absent, under individualized plan of care; consent documented (verbal OK since 2025). Billed under the patient, not per caregiver. Self-paced Companion courses NOT billable — use as pre-work/homework referenced in the note.
- **FHIR record:** CarePlan + Task (modules); Communication (feedback); RelatedPerson
- **Change log:** 2026-11-03: Added fields. 2026-11-03 (later): Designated primary Companion coverage path.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/coding/slp-cpt-and-hcpcs-code-changes-for-2025/) · [Policy document](https://www.cms.gov/files/document/health-related-social-needs-faq.pdf)
- **Sources:** CMS Health-Related Social Needs FAQ (caregiver training); ACL/UCSF CTS billing guide (CY2026); ASHA 2025 code changes; CMS 2026 telehealth list (verify on cms.gov).

#### 97551 (CPT)

Caregiver training, each extra 15 minutes

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Outpatient, Telehealth, Home/community
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Add-on to 97550 only; each full 15 minutes (Medicare requires the full unit). Same rules as 97550: patient not present, consent documented, plan of care.
- **How Linggo LLMs uses it:** Longer Companion sessions, e.g. eye-gaze device setup and practice.
- **Online / async training coverage:** Same as 97550 (live only).
- **FHIR record:** CarePlan + Task
- **Change log:** 2026-11-03: Added fields; add-on to 97550 only.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/coding/slp-cpt-and-hcpcs-code-changes-for-2025/) · [Policy document](https://www.cms.gov/files/document/health-related-social-needs-faq.pdf)
- **Sources:** CMS HRSN FAQ; ACL/UCSF CTS guide; ASHA 2025 code changes.

#### 97552 (CPT)

Group caregiver training (several caregivers)

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Outpatient, Telehealth, Home/community
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Untimed, per session; group of caregivers of multiple patients with similar needs; patients not present; consent documented for each patient. Bill once per patient represented, regardless of caregivers in the room.
- **How Linggo LLMs uses it:** Live group Companion classes (e.g. stroke family AAC class; ASD/IDD parent cohort), in clinic or online.
- **Online / async training coverage:** Live multi-caregiver group (e.g., Coach-led virtual Companion cohort). Recorded course not billable.
- **FHIR record:** CarePlan + Task
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/coding/slp-cpt-and-hcpcs-code-changes-for-2025/) · [Policy document](https://www.cms.gov/files/document/health-related-social-needs-faq.pdf)
- **Sources:** CMS HRSN FAQ (group billing examples); ACL/UCSF CTS guide.

#### G0539 / G0540 (HCPCS)

Individual caregiver behavior management/modification training, without the patient present: first 30 minutes (G0539), each additional 15 minutes (G0540)

- **Populations:** Autism, IDD, Dementia, TBI
- **Settings:** Outpatient, Telehealth
- **Coverage:** Medicare
- **Requirements:** Effective 1 Jan 2025 (Medicare). Patient not present; consent documented; plan of care; billed once per patient regardless of number of caregivers.
- **How Linggo LLMs uses it:** ASD/IDD and dementia (aphasia line): one-family behavior-support training.
- **Online / async training coverage:** Live caregiver behavior-management training, patient absent. Not a course.
- **FHIR record:** CarePlan + Task; RelatedPerson
- **Change log:** 2026-11-03: Added fields. Scope for BCBA billing under Medicare is limited (BCBAs not Medicare-enrolled provider type) — verify.
- **Links:** [Policy document](https://www.cms.gov/files/document/health-related-social-needs-faq.pdf)
- **Sources:** CMS HRSN FAQ; ACL/UCSF CTS guide.

#### G0541 (HCPCS)

Caregiver training in direct care strategies and techniques to support care for patients with an ongoing condition or illness and to reduce complications (including, but not limited to, techniques to prevent decubitus ulcer formation, wound care, and infection control) (without the patient present), face-to-face; initial 30 minutes.

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Outpatient, Telehealth, Home/community
- **Coverage:** Medicare
- **Example ICD-10:** Underlying condition of the patient (e.g., I69.3-, S06.- sequela, F03.9-, F84.0, F70–F79)
- **Requirements:** NOT Medicare's version of 97550: covers complication prevention, not functional/communication goals. Full 30 minutes; patient not present; consent documented; must be in the plan of care. Effective 1 Jan 2025.
- **How Linggo LLMs uses it:** Rarely. Possible use: training the Companion on aspiration-prevention strategies. Communication training goes to 97550.
- **Online / async training coverage:** Live, face-to-face clinician training of the caregiver (patient absent) under the plan of care; consent (verbal OK since 2025) documented. ASHA: NOT for functional-performance goals (use 97550–97552) — fit for AAC is narrow (e.g., complication prevention). Self-paced Companion courses not billable.
- **FHIR record:** CarePlan + Task
- **Change log:** 2026-11-03: Exact CMS descriptor; status → Verified (code exists/descriptor). Payer rules still vary.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/coding/slp-cpt-and-hcpcs-code-changes-for-2025/) · [Policy document](https://www.cms.gov/files/document/r12980cp.pdf)
- **Sources:** ASHA 2025 code changes; CMS HRSN FAQ; ACL/UCSF CTS guide.

#### G0542 (HCPCS)

Caregiver training in direct care strategies and techniques to support care for patients with an ongoing condition or illness and to reduce complications (…) (without the patient present), face-to-face; each additional 15 minutes (list separately in addition to code for primary service) (use G0542 in conjunction with G0541).

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Outpatient, Telehealth, Home/community
- **Coverage:** Medicare
- **Requirements:** Add-on to G0541 only; full 15 minutes; same rules as G0541.
- **How Linggo LLMs uses it:** As G0541 (rare).
- **Online / async training coverage:** Add-on to G0541 only; same live face-to-face rule.
- **FHIR record:** CarePlan + Task
- **Change log:** 2026-11-03: Exact descriptor; Verified.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/coding/slp-cpt-and-hcpcs-code-changes-for-2025/) · [Policy document](https://www.cms.gov/files/document/r12980cp.pdf)
- **Sources:** ASHA 2025 code changes.

#### G0543 (HCPCS)

Group caregiver training in direct care strategies and techniques to support care for patients with an ongoing condition or illness and to reduce complications (…) (without the patient present), face-to-face with multiple sets of caregivers. Untimed; billed per patient represented.

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Outpatient, Telehealth, Home/community
- **Coverage:** Medicare
- **Requirements:** Untimed; caregivers of multiple patients; bill once per patient represented; patients not present.
- **How Linggo LLMs uses it:** As G0541 (rare).
- **Online / async training coverage:** Live group session (e.g., Coach-led cohort for Companions). Recorded/self-paced course modules not billable.
- **FHIR record:** CarePlan + Task
- **Change log:** 2026-11-03: Exact descriptor; Verified.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/coding/slp-cpt-and-hcpcs-code-changes-for-2025/) · [Policy document](https://www.cms.gov/files/document/r12980cp.pdf)
- **Sources:** ASHA 2025 code changes; CMS HRSN FAQ.

### Cognitive

#### 96125 (CPT)

Standardized cognitive performance testing, per hour

- **Populations:** Stroke, TBI, Dementia
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Example ICD-10:** S06.- sequela; I69.31-; F03.9-; R41.84-
- **Requirements:** Timed, per hour; standardized cognitive performance testing with interpretation and report; SLP or psychologist.
- **How Linggo LLMs uses it:** Aphasia line (TBI, dementia): cognitive-communication baseline; outcomes reporting.
- **Online / async training coverage:** Live testing; not a course.
- **FHIR record:** ServiceRequest; Observation
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/)
- **Sources:** ASHA Medicare coding rules.

#### 97129 (CPT)

Cognitive function intervention, first 15 minutes

- **Populations:** Stroke, TBI, Dementia
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Example ICD-10:** TBI S06.- sequela; I69.31- cognitive deficits after stroke; dementia F03.9-/G30.-; R41.84-
- **Requirements:** Timed, first 15 minutes, direct one-on-one; SLP, OT or psychologist; plan of care; GN modifier for SLP (Medicare). Not changed by the 2027 92507 replacement.
- **How Linggo LLMs uses it:** Aphasia line (TBI, dementia): cognitive strategy work delivered by the Coach, e.g. memory books built in the app.
- **Online / async training coverage:** Live direct clinician time; app-delivered cognitive exercises alone not billable.
- **FHIR record:** ServiceRequest; CarePlan
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/)
- **Sources:** ASHA Medicare coding rules.

#### 97130 (CPT)

Cognitive function intervention, each extra 15 minutes

- **Populations:** Stroke, TBI, Dementia
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Example ICD-10:** As 97129
- **Requirements:** Add-on to 97129 only, each additional 15 minutes, time documented.
- **How Linggo LLMs uses it:** As 97129.
- **Online / async training coverage:** Add-on to 97129; live only.
- **FHIR record:** ServiceRequest
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/)
- **Sources:** ASHA Medicare coding rules.

### Device

#### A9270 (HCPCS)

Non-covered item or service. Per DME policy article A52469, a general computing device (tablet, smartphone, laptop) running E2511 software must be coded A9270 — Medicare does not pay for the hardware.

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Home/community
- **Coverage:** Medicare
- **Online / async training coverage:** N/A. Implication: Linggo LLMs app-on-iPad = family/private-pay hardware unless Medicaid/commercial covers.
- **Change log:** 2026-11-03: Added (needs Ling review).
- **Links:** [Policy document](https://www.cms.gov/medicare-coverage-database/view/article.aspx?articleId=52469)

#### E2500 to E2506 (HCPCS)

Speech generating devices, digitized speech (recorded words), by recording time

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Outpatient, Home/community
- **Coverage:** Medicare, Medicaid, Commercial
- **Example ICD-10:** Severe speech impairment + etiology (I69.320, S06.- sequela, F84.0, F70–F79)
- **Requirements:** All seven Medicare criteria; SLP evaluation before delivery; written order.
- **How Linggo LLMs uses it:** Not Linggo LLMs products (dedicated digitized-speech devices). Listed for coding context.
- **Online / async training coverage:** N/A (DME item). Requires prior SLP formal written evaluation incl. treatment plan with training schedule — Coach app eval template could generate this.
- **FHIR record:** DeviceRequest; Claim (prior auth); ClaimResponse
- **Change log:** 2026-11-03: Coverage criteria 1–7 confirmed in LCD L33739; only one SGD code per beneficiary (E2500–E2511 same essential function).
- **Links:** [Reference](https://www.cms.gov/medicare-coverage-database/view/article.aspx?articleId=52469) · [Policy document](https://www.cms.gov/medicare-coverage-database/view/lcd.aspx?LCDId=33739)
- **Sources:** Medicare LCD L33739; policy article A52469; Colorado DME Questionnaire 13.

#### E2508 (HCPCS)

Speech generating device, synthesized speech, one way to build messages and one way to access

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Outpatient, Home/community
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** All seven Medicare criteria.
- **How Linggo LLMs uses it:** Not a Linggo LLMs product. Listed for coding context.
- **Online / async training coverage:** N/A (DME). Dedicated-device rule (criterion 7) applies.
- **FHIR record:** DeviceRequest; Claim; ClaimResponse
- **Change log:** 2026-11-03: Confirmed in LCD/A52469 (E2508 requires physical contact with keyboard/touch screen of letters).
- **Links:** [Reference](https://www.cms.gov/medicare-coverage-database/view/article.aspx?articleId=52469) · [Policy document](https://www.cms.gov/medicare-coverage-database/view/lcd.aspx?LCDId=33739)
- **Sources:** LCD L33739; A52469.

#### E2510 (HCPCS)

Speech generating device, synthesized speech, several ways to build messages and several ways to access (touch, switch, eye gaze)

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Outpatient, Home/community
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** All seven Medicare criteria; evaluation must show need for multiple access methods.
- **How Linggo LLMs uses it:** If Linggo LLMs is bundled on dedicated hardware with a DME partner, this may be the code (multiple message methods and access methods incl. switch and eye gaze). Open question vs E2511.
- **Online / async training coverage:** N/A (DME). Needs PDAC written coding verification — relevant if Linggo LLMs ever ships a dedicated locked device.
- **FHIR record:** DeviceRequest; Claim; ClaimResponse
- **Change log:** 2026-11-03: Confirmed: E2510 billable only for products on PDAC Product Classification List (DOS ≥ 6/1/2016).
- **Links:** [Reference](https://www.cms.gov/medicare-coverage-database/view/article.aspx?articleId=52469) · [Policy document](https://www.cms.gov/medicare-coverage-database/view/lcd.aspx?LCDId=33739)
- **Sources:** LCD L33739; A52469; Colorado DME Questionnaire 13.

#### E2511 (HCPCS)

Speech generating software program, for personal computer or personal digital assistant. Medicare pays the software only when installed on a general computing device; the device itself is coded A9270 (non-covered). Installation/tech support not separately billable. Requires KX (or GA/GZ) modifier.

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Outpatient, Home/community
- **Coverage:** Medicare, Medicaid, Commercial
- **Example ICD-10:** Severe speech impairment dx + etiology (e.g., I69.320/R47.01; F84.0; F70–F79; G12.21 ALS)
- **Requirements:** All seven Medicare criteria. Most likely code for the Linggo LLMs apps; plain tablets are generally not covered.
- **How Linggo LLMs uses it:** Primary Learner DME target via a future enrolled DME partner (decided 2026-11-03). Coach eval template produces the LCD evaluation. Subscription-only features must be unbundled from the claim. Medicaid states may require a locked dedicated device (E2510/PDAC) instead.
- **Online / async training coverage:** Not a service. SaaS/subscription billing model does not fit DME purchase; Linggo LLMs would need DME supplier enrollment (or partner) and PDAC coding questions. Non-speech features (Companion, video, courses) are excluded from DME benefit.
- **FHIR record:** DeviceRequest; Claim; ClaimResponse
- **Change log:** 2026-11-03: Exact descriptor + A9270 rule (LCD/A52469). 2026-11-03 (later): Decision — pursue via DME partner; see Coverage Pathways page.
- **Links:** [Reference](https://www.cms.gov/medicare-coverage-database/view/lcd.aspx?LCDId=33739) · [Policy document](https://www.cms.gov/medicare-coverage-database/view/article.aspx?articleId=52469)
- **Sources:** LCD L33739; A52469; Colorado DMEPOS manual.

### Modifier / place of service

#### Modifiers GN, KX, 95; POS 02 / 10 (HCPCS)

GN = services delivered under an outpatient SLP plan of care (Medicare). KX = attestation that therapy above the annual threshold is medically necessary: CY2026 $2,480 PT+SLP combined; CY2027 proposed $2,540; targeted medical review at $3,000 through CY2027. On DME (E2500–E2599) KX = LCD criteria met (GA/GZ otherwise). 95 = synchronous telehealth (payer-specific). POS 10 = telehealth in patient home; POS 02 = telehealth elsewhere. CY2027 NPRM also proposes new telehealth modifiers BB/BC — pending.

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** GN on every Medicare Part B SLP claim, including caregiver training and RTM by SLPs. KX once combined PT/SLP spending passes the yearly threshold. Telehealth modifier/POS rules differ by payer and year; check before each payer launch.
- **How Linggo LLMs uses it:** Billing rules engine in the Coach/Admin layer should attach these automatically from setting and delivery mode.
- **FHIR record:** Claim
- **Change log:** 2026-11-03: Added 2026/2027 KX thresholds; Coach app should track running yearly therapy $ per Learner.
- **Links:** [Reference](https://www.ahcancal.org/News-and-Communications/Blog/Pages/CMS-Issues-CY-2027-Medicare-Physician-Fee-Schedule.aspx)
- **Sources:** ASHA Medicare coding rules; CMS telehealth guidance (verify current year).

### Remote monitoring

#### 98975, 98980, 98981 (CPT)

RTM: 98975 initial setup and patient education; 98980 treatment management first 20 minutes per calendar month; 98981 each additional 20 minutes

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Home/community, Outpatient
- **Coverage:** Medicare, Commercial
- **Requirements:** Needs an RTM device-supply code to be billable in principle; current supply codes are respiratory, musculoskeletal and CBT, none for communication. 98980 needs a full 20 minutes and at least one real-time interaction in the month; once per month. Sometimes-therapy codes: GN modifier for SLPs.
- **How Linggo LLMs uses it:** Watch item. Ask payers / ASHA whether AAC usage data can ever support RTM. Don't build revenue models on it yet.
- **Online / async training coverage:** 98975 setup/education billable once per episode; 98980/98981 need ≥20 min/month incl. live interaction. Same device-category problem as 98984/85 for AAC.
- **FHIR record:** Observation; Device
- **Change log:** 2026-11-03: Added fields; High risk retained.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/coding/new_codes_slp/) · [Policy document](https://www.cms.gov/files/document/r13431cp.pdf)
- **Sources:** ASHA 2026 code changes; CMS MM14250.

#### 98979, 98984, 98985 (CPT)

98979: RTM treatment management services, physician or other QHP time in a calendar month requiring at least 1 real-time interactive communication with the patient or caregiver; first 10 minutes. 98984: RTM device(s) supply … respiratory system, 2–15 days in a 30-day period. 98985: RTM device(s) supply … musculoskeletal system, 2–15 days in a 30-day period. (98986 = cognitive behavioral therapy, 2–15 days, also new 2026.) 98979 not combinable with 98980 same month; 2–15 and 16–30 day supply codes mutually exclusive.

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Home/community, Outpatient
- **Coverage:** Medicare, Commercial
- **Requirements:** 98984/98985 are respiratory and musculoskeletal device-supply codes: they do NOT describe communication/language data, so app tap data likely does not qualify. 98979 needs 10–19 minutes of management in a calendar month with at least one real-time interaction with patient or caregiver; app notifications don't count. SLPs must work under a therapy plan of care with GN modifier. Supply codes 2–15 and 16–30 day tiers are not additive. RTM and RPM are mutually exclusive in the same period.
- **How Linggo LLMs uses it:** Wanted for Coach between-visit monitoring of Learner/Companion, but no communication device category exists and the CY2027 NPRM proposes tighter remote monitoring rules. Do not build revenue on this; consider advocacy for an AAC category.
- **Online / async training coverage:** Async data is the point, but supply codes are tied to respiratory/MSK/CBT — no communication/AAC device category exists. Using them for AAC usage data is high risk. Treatment management requires live (not async-chat) interaction per CMS adopting CPT language. Therapists: sometimes-therapy, GN modifier, under plan of care.
- **FHIR record:** Observation; Device
- **Change log:** 2026-11-03: Descriptors verified; High risk. 2026-11-03 (later): Reviewed for Coach monitoring — still not a fit.
- **Links:** [Reference](https://www.nixonlawgroup.com/resources/cms-finalizes-2026-remote-monitoring-reimbursement-updates-what-changed-for-rpm-and-rtm) · [Policy document](https://www.cms.gov/files/document/r13431cp.pdf)
- **Sources:** ASHA 2026 code changes; CMS MM14250 therapy code list 2026; CY2026 PFS final rule (90 FR 49394–49397).

#### G0552 / G0553 / G0554 (DMHT) (HCPCS)

G0552 supply of digital mental health treatment device and initial education/onboarding, per course of treatment (contractor-priced); G0553 first 20 min/month treatment management incl. ≥1 interactive communication; G0554 each additional 20 min. Limited to FDA-cleared devices under 21 CFR 882.5801 (psychiatric) and, from 2026, 882.5803 (ADHD), furnished incident to a behavioral health plan of care.

- **Populations:** Autism
- **Settings:** Home/community
- **Coverage:** Medicare
- **How Linggo LLMs uses it:** Not usable now (AAC is not an eligible FDA category, and the billing practitioner must furnish the device). Watch only: the precedent for paying for software plus monitoring.
- **Online / async training coverage:** N/A
- **Change log:** 2026-11-03: Added as a watch item for the long-term digital therapeutic path.
- **Links:** [Reference](https://www.nixonlawgroup.com/resources/cms-proposes-expanded-coverage-for-digital-mental-health-devicesand-seeks-input-on-broader-digital-therapeutics-use-cases) · [Policy document](https://www.cms.gov/files/document/mm14315-medicare-physician-fee-schedule-final-rule-summary-cy-2026.pdf)

### Speech therapy

#### 92507 (CPT)

Treatment of speech, language, voice, communication, and/or auditory processing disorder; individual. DELETED from CPT effective 1 Jan 2027 — valid for dates of service through 31 Dec 2026 only.

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Example ICD-10:** Stroke aphasia I69.320; TBI S06.- (7th char S for sequela) + R47.01; dementia F03.9-/G30.- + R47.01; autism F84.0 + F80.-; IDD F70–F79 + F80.- (confirm payer-specific dx lists)
- **Requirements:** Untimed, one unit per session (through 31 Dec 2026). SLP under a plan of care with physician/NPP certification (Medicare); GN modifier on Medicare Part B; KX above the yearly therapy threshold. Medical necessity and progress documented each session. From 1 Jan 2027 replaced by timed 92654–92663 (see that row); some Medicaid/commercial payers may switch later.
- **How Linggo LLMs uses it:** Aphasia and ASD/IDD, outpatient. Coach app logs session minutes and goal targets (needed now for the 2027 timed codes); Learner board taps give progress data. Inpatient: bundled in DRG/facility claim.
- **Online / async training coverage:** Billable only for live, skilled treatment by an SLP (in person or synchronous telehealth where payer allows). Self-paced app lessons are not billable under this code; they can be a documented home program.
- **FHIR record:** ServiceRequest; CarePlan; Observation
- **Change log:** 2026-11-03: Confirmed deletion 1/1/2027 (ASHA). Added population/setting/role fields. Migrate Coach app charge capture to 92654–92663 for DOS ≥ 1/1/2027; Medicaid/commercial may keep 92507 temporarily — verify per payer.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/coding/new-speech-language-pathology-treatment-codes-replacing-92507/)
- **Sources:** ASHA Medicare coding rules; ASHA 'Treatment codes replacing 92507' (asha.org/practice/reimbursement/coding/new-speech-language-pathology-treatment-codes-replacing-92507/); CMS CY2027 PFS proposed rule (final rule pending).

#### 92508 (CPT)

Speech, language, voice and communication treatment, group

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Untimed group treatment, two or more individuals; SLP; plan of care; GN modifier (Medicare). Revised for 2027 as the stand-alone group code. Cannot be billed with ABA group codes 97154/97158 from 2027.
- **How Linggo LLMs uses it:** Outpatient and possibly school-like groups (ASD/IDD). Coach app session with multiple Learners; each Learner's data kept separate.
- **Online / async training coverage:** Live group; not a course.
- **FHIR record:** ServiceRequest
- **Change log:** 2026-11-03: Remains untimed group code in 2027 (descriptor revised per CPT 2027).
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/)
- **Sources:** ASHA Medicare coding rules; ASHA 92507 replacement page (92508 revision).

#### 92521 (CPT)

Evaluation of speech fluency (stuttering)

- **Populations:** Stroke, TBI, Autism, IDD
- **Settings:** Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Untimed evaluation of speech fluency; SLP; written report; once per evaluation (re-evaluation only with a change in condition). GN modifier (Medicare).
- **How Linggo LLMs uses it:** Rarely relevant to Linggo LLMs populations. Listed for completeness.
- **Online / async training coverage:** Live eval only.
- **FHIR record:** ServiceRequest
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/)
- **Sources:** ASHA Medicare coding rules.

#### 92522 (CPT)

Evaluation of speech sound production

- **Populations:** Stroke, TBI, Autism, IDD
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Untimed evaluation of speech sound production only; SLP; written report. Do not bill with 92523 (92523 includes it).
- **How Linggo LLMs uses it:** Limited. Use 92523 when language is also evaluated (usual for aphasia and ASD/IDD).
- **Online / async training coverage:** Live eval only.
- **FHIR record:** ServiceRequest
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/)
- **Sources:** ASHA Medicare coding rules.

#### 92523 (CPT)

Evaluation of speech sound production plus language comprehension and expression

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Untimed evaluation of speech sound production plus language comprehension and expression; SLP; written report establishing diagnosis, baseline and plan of care. GN modifier (Medicare). Not with 92522.
- **How Linggo LLMs uses it:** Usual initial language evaluation for aphasia (inpatient: bundled; outpatient: billable) and ASD/IDD. Candidate for a built-in Coach evaluation template (open decision).
- **Online / async training coverage:** Live eval only.
- **FHIR record:** ServiceRequest
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/)
- **Sources:** ASHA Medicare coding rules.

#### 92524 (CPT)

Voice and resonance evaluation

- **Populations:** Stroke, TBI
- **Settings:** Inpatient, Outpatient
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Untimed voice and resonance evaluation; SLP; written report.
- **How Linggo LLMs uses it:** Not a core Linggo LLMs use. Listed for completeness.
- **Online / async training coverage:** Live eval only.
- **FHIR record:** ServiceRequest
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/)
- **Sources:** ASHA Medicare coding rules.

#### 92526 (CPT)

Treatment of swallowing and oral function for feeding

- **Populations:** Stroke, TBI, Dementia, IDD
- **Settings:** Inpatient, Outpatient
- **Coverage:** Medicare, Medicaid, Commercial
- **Requirements:** Untimed treatment of swallowing and oral function for feeding; SLP; plan of care; GN modifier. Not changed by the 2027 92507 replacement.
- **How Linggo LLMs uses it:** Not an app feature. Common co-occurring service after stroke; relevant only for scheduling and bundling.
- **Online / async training coverage:** Live treatment; telehealth payer-dependent (safety).
- **FHIR record:** ServiceRequest
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/)
- **Sources:** ASHA Medicare coding rules.

#### 92654 to 92663 (2027) (CPT)

CPT 2027 individual SLP treatment, timed, direct one-on-one: 92654/92655 fluency; 92656/92657 speech sound production; 92658/92659 language comprehension and expression; 92660/92661 combined speech sound + language; 92662/92663 voice, upper airway dysfunction and/or resonance. Base = initial 30 min, add-on = each additional 15 min. 92508 (group) stays untimed. Medicare values PROPOSED (CY2027 PFS NPRM, CF $32.8409); final rule expected early Nov 2026 — not yet confirmed. CMS also proposed Medicare-only pediatric code GSLPP (see row).

- **Populations:** Stroke, TBI, Dementia, Autism, IDD
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Example ICD-10:** Aphasia/language: I69.320, R47.01, F80.1/F80.2; autism F84.0; IDD F70–F79
- **Requirements:** Effective for dates of service on/after 1 Jan 2027. Base code after 16 minutes of direct one-on-one treatment; add-ons by CPT midpoint rule. Document minutes per disorder area. Speech sound, language and combined codes can't be stacked: treat both areas -> use the combined code. Not reportable with ABA 97153/97155. Medicare values final only in the CY2027 PFS final rule; Medicaid/commercial may adopt later. Exact number-to-category mapping: confirm in the CPT 2027 codebook (aphasia most likely the language pair).
- **How Linggo LLMs uses it:** Aphasia and ASD/IDD outpatient treatment from 2027. Coach app must record minutes and disorder area per session; billing rules must pick code set by date of service. Existing PAs written for 92507 may need conversion.
- **Online / async training coverage:** Live clinician time only; timed codes require minute-level documentation (Coach app must capture start/stop time and clinical category). Not yet confirmed on Medicare telehealth list — ASHA asked CMS to add; check final rule.
- **FHIR record:** ServiceRequest; CarePlan; Observation
- **Change log:** 2026-11-03: Exact category structure confirmed; final Medicare values & telehealth status pending CY2027 final rule — re-check.
- **Links:** [Reference](https://www.asha.org/news/2026/cms-proposes-medicare-payment-for-new-speech-language-pathology-treatment-codes/) · [Policy document](https://www.federalregister.gov/documents/2026/07/16/2026-14327/medicare-and-medicaid-programs-cy-2027-payment-policies-under-the-physician-fee-schedule-and-other)
- **Sources:** ASHA replacement page; ASHA CY2027 NPRM news; Federal Register CMS-1848-P (7/16/2026). Code numbers from CPT 2027 per secondary sources — confirm in AMA CPT 2027 codebook before loading chargemaster.

#### 96105 (CPT)

Assessment of aphasia, per hour

- **Populations:** Stroke, TBI, Dementia
- **Settings:** Inpatient, Outpatient, Telehealth
- **Coverage:** Medicare, Medicaid, Commercial
- **Example ICD-10:** R47.01 + I69.320 / S06.- sequela / F03.9- or G30.-
- **Requirements:** Timed, per hour of professional time including interpretation and report; SLP or psychologist; standardized instrument named. Check NCCI edits with 92523 on the same date.
- **How Linggo LLMs uses it:** Aphasia line: standardized aphasia battery (e.g. WAB-R) at baseline and re-evaluation; scores feed value-based outcome reporting (Observation).
- **Online / async training coverage:** Live standardized testing by SLP; remote administration validity must be documented.
- **FHIR record:** ServiceRequest; Observation
- **Change log:** 2026-11-03: Added fields.
- **Links:** [Reference](https://www.asha.org/practice/reimbursement/medicare/slp_coding_rules/)
- **Sources:** ASHA Medicare coding rules.

#### GSLPP (proposed 2027) (HCPCS)

PROPOSED Medicare-only HCPCS G-code for individual pediatric SLP treatment (CY2027 PFS NPRM). Untimed, valued on 92507 inputs, work RVU 1.30 (~60 min), once per patient per day, always therapy, MPPR applies; proposed for Medicare telehealth list. ASHA opposes. Final status pending CY2027 final rule.

- **Populations:** Autism, IDD
- **Settings:** Outpatient, Telehealth
- **Coverage:** Medicare
- **Online / async training coverage:** Live only. Low Medicare pediatric volume, but Medicaid/MCOs may copy it — watch.
- **Change log:** 2026-11-03: Added (needs Ling review). Not final.
- **Links:** [Reference](https://www.asha.org/news/2026/2027-medicare-part-b-proposed-rule-coding-payment-and-policy-analysis/) · [Policy document](https://www.federalregister.gov/documents/2026/07/16/2026-14327/medicare-and-medicaid-programs-cy-2027-payment-policies-under-the-physician-fee-schedule-and-other)

## Change log

- 2026-11-03: first mirror from Notion, 47 rows; columns Populations, Example ICD-10, Setting, App role, Online/async training coverage and Change log added in Notion the same day.
