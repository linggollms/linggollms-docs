# Linggo LLMs: platform documentation

Public documentation for [Linggo LLMs](https://github.com/linggollms), AAC (augmentative and alternative communication) software for people with little or no speech. This repo is the readable surface of a codebase that is private because it runs in a HIPAA-covered environment and serves people's health information. The code stays private; how it is built, and why, is here.

**Start here**

| Page | What it answers |
| --- | --- |
| [Why the code is private](why-the-code-is-private.md) | What a reader can and cannot see, and the reasons |
| [History](platform/history.md) | Activity log: what was built, shipped and decided, with dates, since September 4, 2026 |
| [Architecture](platform/architecture.md) | The AWS Organization, the two accounts, the HIPAA posture, the language graph |
| [Linggo LLMs Aphasia](apps/aphasia.md) | The Aphasia product: what it is, stack, status |
| [Linggo LLMs ASD/IDD](apps/asd-idd.md) | The ASD/IDD product: what it is, stack, status |
| [Supporting repos](apps/support-repos.md) | Design system, training-video studio, ops robot, social agent, website |
| [Policies](policies.md) | Privacy Policy, Terms of Use, Consumer Health Data Privacy Policy and Accessibility Statement: where they live and what they say |
| [COM Systems: how the company runs](com-systems.md) | The AI-native operating system behind Linggo LLMs, and how it was built |
| [Agents](agents.md) | The agents that run research, intel, ops and social, and the standard every agent must meet before it goes live |

**What is public, and where**

- `linggollms/.github` and this repo: public.
- `linggollms-aphasia-webapp`, `linggollms-asd-idd-webapp`, `linggollms-design-system`, `website-refresh-studio`, `linggollms-ops`, `linggollms-animation-studio`, `socialmedia_agent`: private. Each is described in this repo at the level of what it is, what it runs on and what state it is in.

**Rules for this repo**

Plain words: clinicians, families, partners and investors read this, not only developers. Never a secret, an AWS account or resource ID, an IP address, or anything that identifies a person who uses the app or their family. Every fact names its date; anything not settled is called a question, not a plan.

The source of truth for app-level documentation is `docs/` inside each app repo; this repo mirrors the platform-level parts of it. Where a page here and a page there disagree, the app repo is right and this one is behind.

**Contact:** Ling Ly Tan, Founder and CEO · admin@linggollms.com · [linggollms.com](https://linggollms.com)
