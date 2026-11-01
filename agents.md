# Agents

The agents that help run Linggo LLMs, described by what they do. Every one of them follows the standard in [COM Systems](com-systems.md): a worker spec first, skills second, a manual pilot, then the agent, with a named human supervisor, declared inputs, outputs and permissions, an escalation path and a definition of done. The supervisor for every agent today is the founder.

None of these agents touches health information. The operating-system layer (Notion, GitHub Actions, the scheduler) holds company records, research, public content and status; what a person says in the app lives in AWS under a BAA and is never read by any of them.

## Engineering

**Claude Code** is the coding agent for both products and every supporting repo. It works from `CLAUDE.md` and `AGENTS.md` in each repo (the engineering worker spec: what to read first, the checks before a pull request, the words we use, what never goes in a commit), on a branch, through a pull request. A catch-up script (`whats-new.sh`) lets every session start by reading what changed. Since September 4, 2026: 2,049 commits and 179 merged pull requests across the organization.

**Command Center robot** (`linggollms-ops`). A GitHub Action that runs every morning. It reads open pull requests and the week's merges from GitHub, the week's deliverables from Notion, and, read-only through a role that can only look, deployment and setup status from both AWS accounts. It writes one live status line per workstream into the operating system and saves a plain-text copy so any computer can read it. No keys are stored; no information about people goes in.

**AWS DevOps Agent** (AWS). Enabled on the accounts for backend troubleshooting; used for release-readiness checks until the founder dropped that check from pull requests in October to keep PR review in human hands.

## Research and clinical evidence

**Evidence review agent** (Acquired Communication Disorders research database, Notion). Reviews a release of the aphasia product against the AAC research base for its target population (adults with aphasia, dementia, brain injury) and produces a build list of what the evidence says to change before the next supervised users. Its October 2026 review of the v1 beta became `docs/reviews/2026-10-v1beta-handoff.md` in the aphasia repo. A companion research brain covers autism and IDD, with the rule that studies are weighed by whether their participants match the people the product serves: minimal to no speech, autism/IDD, acquired disorders.

**Competitor Observer** (weekly, Thursdays). Watches AAC and speech-device companies, AI communication startups, Big Tech accessibility and voice moves, and market shifts (Medicare/Medicaid, FDA, HIPAA, AAC research). Only real, dated news from the last 7 to 10 days; adds rows to the Competitor Watch database and posts a dated notice to the Company Intel Log.

**Grant Monitor** (weekly, Mondays). Finds open or upcoming non-dilutive funding that fits Linggo LLMs (AAC, autism, aphasia, assistive technology, communication access) from funder sites and aggregators, checks eligibility (U.S. for-profit, within six months) on the funder's own page, and adds rows to Funding Applications. It never applies.

## Operations

**Front desk / inbox router.** Triages incoming company email within 24 hours and routes each thread to the right database: a lead to the CRM, a receipt to expenses, a funding notice to grants, an investor message to the investor pipeline. Drafts and proposes; the founder confirms before anything is created or sent.

**Finance capture.** Turns receipts and bank transactions into clean expense records with a source link, flags missing fields, and supports the tax filings for a company that has operated in two countries.

**Grants and non-dilutive funding.** Tracks the SBIR and other grant pipeline: deadlines, requirements, drafts. Works with the Grant Monitor above.

**Investor relations.** Keeps the investor pipeline, pitch deck and data room current and drafts investor updates. Drafts only: nothing is sent without the founder's approval, and financial figures come from the finance records, not from the agent.

**Partnerships and CRM.** Owns the pipeline from first conversation to close; routes lead conversations from email into the CRM.

**Chief-of-staff / weekly sync.** Aggregates status across the other agents into the weekly sync, computes trajectory on quarterly goals and velocity on weekly deliverables, and escalates frictions for the founder's decision.

## Content and community

**Social media agent** (`socialmedia_agent`). Plans and posts through Postiz, an open-source scheduler Linggo LLMs runs on its own AWS server. Public words come from the website copy, the Notion brand voice and the design system; nothing that identifies a learner, family or patient goes into a post. Works on a branch; the founder merges.

**Training content and translation.** Turns research and product changes into training material for families, SLPs, BCBAs, RBTs and teachers, including CEU content and translation into the five product languages. The animation studio (`linggollms-animation-studio`) is its production tool, and it exists because no available video creator reflects the real lives of people with disabilities: most training video is sanitized, and AI video generators cannot simulate scenarios they have never seen. A 58-character cast with measured heights, hand-drawn and mesh rigs, real AAC screens per child and language, five-language narration, MP4 and caption export, all running on the founder's own computer.

**Brand.** The Linggo LLMs design system (logo, palette, type, icons, voice) lives as a Claude design system and in `linggollms-design-system`; it guides the Notion pages, the apps and the website so one brand appears everywhere.

## The go-live gate, for every agent

| Field | What it must say |
| --- | --- |
| Supervisor | One named human |
| Inputs | Source systems, databases, documents, triggers |
| Outputs | What it produces and where it writes |
| Permissions | Which systems, read vs write, what it is barred from touching |
| Escalation path | The condition that stops it, and who it goes to |
| Definition of done | How anyone can tell it is working |

Agents are reviewed quarterly: instructions re-read against current scope, skills checked, guardrails tightened, changes logged, and any agent whose instructions changed is run manually for a week before its triggers are re-enabled.
