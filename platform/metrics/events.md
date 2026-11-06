# Metrics spec: Learner communication and founding beta (ASD/IDD)

Repo: `linggollms-docs` at `platform/metrics/events.md`. Mirror to Notion under REV-3.
Status: draft for Ling's review, 2026-11-06.
Scope: **linggollms-asd-idd-webapp only** (Wave 1). Aphasia is the next phase, designed with Shawna Fleming.
Plan this serves: REV-3 Founding Membership page (Notion).

## 1. Goals

1. Show how often each Learner communicates, and whether that rises over time (the "high line").
2. Show whether families stay, by wave (cohort retention, the "smile").
3. Give Companions their Learner's word list, and give Ling each Learner's patterns and feedback.
4. Feed the gates that decide when the next wave opens.

## 2. Phases

| Phase | When | What is tracked |
| --- | --- | --- |
| A. Wave 1 | Nov 2026 | Learner communication, word usage, feedback and comments, retention, sign-up and wave data |
| B. Billing | Dec 1 | Subscription events (founding price, refunds) |
| C. Coach beta | Dec 2026 | Coach review only; no Learner data collection yet |
| D. Coach and Companion data | Jan 2027 onward | Prompted vs independent, Coach data checks, Companion modeling |
| E. Aphasia | After D | Aphasia history and measures with Shawna |

Companion training completions come from a **DISCO export**, not this backend.

## 3. Where things live in the app

- **Communication Patterns** is a new section of the **Dashboard** (behind the PIN). It is not added to the Learner's communication board: per decision M10 (`docs/logic/decisions.md` in the ASD/IDD repo), learner screens (Language Tree, My Words, Type, Quick Chat) stay free of extra controls.
- **My Words** already orders words most used first. The count is the `frequency` field on each word ("times spoken in a sentence") in `src/lib/model.ts`. Build on it rather than adding a second count.
- **Offline first.** The communication board must keep working with no connection (see "Offline support" in each app's `docs/ops-notes.md`). Events are saved on the device and sent when the connection returns. Recording an event never delays speech, and a failed send never shows an error on a learner screen.

## 4. Events (Phase A and B)

All events carry: `event_id`, `learner_id` (internal ID, never a name), `account_role`, `occurred_at` (UTC), `app_version`, `platform`.

| Event | Extra fields | Notes |
| --- | --- | --- |
| `account_created` | `role` (learner, companion, coach, organization), `line` (asd_idd), `wave` (wave_1, wave_2, ...), `language`, `signup_source`, `referral_ref` (clinic code) | From the tracked sign-up link (`?wave=1&src=...&ref=...`) |
| `onboarding_completed` | `needed_help` (bool) | Gate: 80% complete without help |
| `session_started` / `session_ended` | `duration_s` | Time in the app. Does not define an active day (see section 5) |
| `message_spoken` | `word_count`, `word_ids[]`, `typed_word_count`, `access_method` (touch, switch, eye_gaze), `build_time_ms` | One event per spoken output. See section 5 |
| `word_first_used` | `word_id` | Derived on write when a Learner uses a board word for the first time |
| `feedback_submitted` | `type` (text, voice, symbols), `topic`, `rating` (optional), `body_ref` | Body stored in AWS; only `body_ref` in analytics |
| `comment_submitted` | `type`, `body_ref` | Messages and comments from Companions to Linggo LLMs |
| `safety_issue` | `status` (opened, closed), `severity` | Gate: zero open |
| `subscription_event` (Phase B) | `kind` (started, renewed, cancelled, refunded), `plan` (founding_asd_idd_100), `amount`, `channel` (stripe, apple, google) | Founding prices: see section 4a |

### 4a. Founding prices

Confirmed and locked by Ling on 2026-11-06. Founding members pay:

| Line | Plan name | Price |
| --- | --- | --- |
| ASD/IDD | `founding_asd_idd_100` | $100 a year |
| Aphasia | `founding_aphasia_75` | $75 a year (used from Phase E) |

The founding price is reserved at waitlist sign-up. The price goes up after the beta.

## 5. Counting rules

- **A message** = one spoken output from the Learner's communication board.
- **Repeat filter:** the same button or message repeated within 3 seconds counts once (decided by Ling on 2026-11-05). This stops exploring or repeated tapping from inflating the high line.
- **Typed words** (from Type) have no `word_id`. They are counted in `word_count` and `typed_word_count` only. The typed text itself is never recorded in an event.
- **Prompted and independent are combined in Phase A.** Label all charts "all communication (prompted and independent)". Separation starts in Phase D.
- **Active day** = a day with at least one `message_spoken`. This is the only definition used.

## 6. Derived metrics

| Metric | Definition | Use |
| --- | --- | --- |
| Messages per active day | Average per Learner, by week since joining, per wave | **The high line** |
| Words per active day | Sum of `word_count` per active day | High line (words) |
| Different words per week | Count of distinct `word_ids` (board words only) | Vocabulary growth |
| New words per week | Count of `word_first_used` | Vocabulary growth |
| Words per message | `word_count` per message, averaged | Longer utterances |
| Build time | Median `build_time_ms` | Fluency |
| Activation | Onboarding plus first Learner session without help | Gate (80%) |
| Weekly active | Learners active in weeks 2 and 3 | Gate (60%) |
| Retention by cohort | Share active on day 1, 7, 30 after joining, per wave | The smile. Working benchmark floor 60 / 30 / 15% (source to confirm, see section 11) |
| Days active of last 28 | Histogram across Learners | Power-user curve |
| Feedback volume and themes | Count by type and topic | Gate: all feedback read |
| Paying founders, MRR, conversion | From `subscription_event` | Business |

## 7. Who sees what

| Who | Sees | Where |
| --- | --- | --- |
| Companion | Their Learner's word list (word, how often, first used) and communication over time | **Dashboard → Communication Patterns** (behind the PIN), ASD/IDD web app |
| Ling (Admin) | Each Learner: words, frequency, new words, feedback, comments and messages | Admin panel in the app, on AWS, access logged |
| Business dashboard | Counts only: sign-ups, retention by wave, high line averages, paying founders, MRR, feedback themes. No word lists, not even de-identified ones | On AWS |
| Coach (from Phase D) | Word lists for Learners whose Companions granted access | Coach app via consent grant |

Why no word lists on the business dashboard: Wave 1 is a handful of families, so a list of words can point to one child. Why AWS: the Anthropic BAA covers Claude Enterprise and the Anthropic API only, so anything drawn from Learner data stays on AWS unless a covered plan is confirmed first.

## 8. Privacy and safety

- Message content and word lists stay in AWS. Analytics tables and the business dashboard receive counts only, never names, words or what a Learner said.
- Every Admin view of a Learner's data is logged.
- **Children's privacy (COPPA).** Learners in the ASD/IDD app are children. Events are recorded only after verifiable parental consent from the Companion (the ASD/IDD app's COPPA consent step). The consent text must say that Linggo LLMs staff can view word lists to support the family and improve the app. Counsel is reviewing that text.
- The Learner owns their data (Lifelong Learner spec). Deleting an account deletes its events, including events still waiting on the device.

## 9. Accessibility

The Communication Patterns section and Admin views follow the Linggo LLMs Accessibility Runbook (`linggollms-design-system/docs/accessibility-runbook.md`). Log results in `linggollms-design-system/docs/accessibility-log.md`.

## 10. Acceptance criteria (Phase A)

- [ ] Events in section 4 fire in the ASD/IDD web app and land in the backend
- [ ] Events recorded with no connection are kept on the device and sent later; speech never waits on them
- [ ] Repeat filter applied before metrics are calculated
- [ ] Dashboard → Communication Patterns shows the Companion their Learner's word list (word, how often, first used), messages per day over time, and new words this week
- [ ] Admin panel shows each Learner's patterns, feedback and comments, with access logging
- [ ] A daily de-identified export (counts only) exists for the business dashboard
- [ ] Accessibility pass logged
- [ ] No message content, typed text, word lists or names in analytics tables

## 11. Research basis

- Kent-Walsh, J., Murza, K. A., Malani, M. D., & Binger, C. (2015). Effects of communication partner instruction on the communication of individuals using AAC: a meta-analysis. *Augmentative and Alternative Communication*, 31(4), 271–284. 17 single-case studies, 53 participants, mostly autism/IDD under 12. Supports tracking Companion modeling in Phase D.
- Tan, L. L. (2021). Can AAC systems and interventions benefit from ABA? *Closing The Gap Solutions*, 40(1). Recommends tracking independent and prompted communication over time, mean length of utterance, request vs comment vocabulary, and frequency and fluency. Practitioner article; autism/IDD. **To check:** confirm the citation against the Autism + AAC Research Database before relying on it.
- Retention benchmark (60% day 1, 30% day 7, 15% day 30). Attributed to Chen, A. (2021), *The Cold Start Problem*. **To check:** this figure may come from Andrew Chen's writing on retention rather than the book. Confirm the source, or label it "working target" only. It is a consumer-app benchmark, not one for AAC users.
