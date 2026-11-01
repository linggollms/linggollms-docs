# COM Systems: how Linggo LLMs runs

Linggo LLMs is run by one person and a set of AI agents, inside one source of truth. The system that makes that possible is called **COM** (Central Operating Matrix). It is an AI-native operating system built on the ideas of EOS (the Entrepreneurial Operating System), designed and built by the founder in Notion over 2026, and later sold as a paid engagement to another startup. This page describes what it is and how it was built. It leaves out the internal vocabulary; the structure is what matters.

## The idea in one paragraph

Classical EOS assumes humans update static documents on a quarterly cycle: a vision page, quarterly goals, weekly to-dos, a weekly leadership meeting, an issues list, an accountability chart. COM keeps those shapes and makes them continuous. Goals, tasks, records and meetings live in databases, not pages. Agents read those databases, compute whether each goal is on trajectory, check whether each deliverable is actually done, and surface friction as it happens. The founder is asked for input only where judgment is required. Humans set strategy, priorities and trade-offs; agents handle capture, repeatable operations and synthesis; everything queryable lives in a database.

## How EOS maps to COM

| EOS | In COM |
| --- | --- |
| Vision / Traction Organizer | The long arc: the current year, the 3-year and 10-year horizons |
| Rocks (quarterly) | Quarterly goals, one to three per domain, each with one owner (human or agent) and a definition of done |
| Weekly to-dos | 7-day deliverables, five a week at most, each with one metric: a target and an actual |
| Level 10 meeting | An async weekly sync. One agent aggregates status across the others and escalates frictions for the founder's decision |
| Issues list (IDS) | A friction-anomaly system: detection and resolution tracked as records, not as a meeting agenda |
| Accountability chart | An agent registry: one owner per domain |

Each goal and deliverable has an ID, an outcome-shaped name, a definition of done with a date, one proving metric, and a status that is either trajectory (off track, at risk, on track, complete) or velocity (reached or not). Finished or retired work moves to an archive with its original name, so nothing is deleted and the record is auditable.

## The four layers

The system separates what is usually blurred together.

1. **Operating system (data and truth).** Dashboards and databases where work is planned, tracked and reviewed. Four "brains" in Notion: Company (operating system, operations, finance), Customer (revenue, partnerships, marketing), Dev (product and engineering), and Research and Education.
2. **Skills (procedures).** Reusable prompts that produce consistent outputs. A skill does a job; it does not own responsibility over time.
3. **Workers (role specs).** The job description for an AI role: mission and definition of done, ranked sources of truth and tie-breaker rules, three to six operating modes, required integrations, guardrails, success metrics. A worker can exist without an agent; an agent should never exist without a worker.
4. **Agents (executors).** The configured AI entity that runs the worker's skills with explicit permissions, integrations and triggers.

## How a new agent is built (the standard)

The order is deliberate, and it was learned by doing it wrong first.

1. Create or confirm the source-of-truth database the agent will read and write.
2. Write the worker spec: mission, modes, sources of truth, guardrails, metrics.
3. Write three to six skills.
4. Pilot manually for one to two weeks: the founder runs the skills by hand and refines the prompts and database properties.
5. Only then create the agent, with narrow write access, and wire the instructions page into it.
6. Two weeks of stable behaviour before status moves from Pilot to Live.

No agent goes live without six things filled in: a named human supervisor (one person, never a team), inputs, outputs, permissions (read versus write, and what it is barred from touching), an escalation path (the condition that stops it and who it goes to), and a definition of done anyone can check.

## Guardrails

Default to drafts and proposals when confidence is low or critical fields are missing. Require human confirmation for deleting, bulk edits, reparenting, changing sharing or permissions, or changing priorities. Every created record carries its source. Watch for four failure modes: silent drift outside scope, duplicates, overwriting a source of truth, and prompt bloat. Sensitive personal and health data stays out of the agent layer unless there is a specific reason and a compliance path, and for Linggo LLMs that means health data lives in AWS under a BAA, never in the operating-system layer.

## The human side: training people to work with agents

The part of COM the founder considers the durable asset is not the agents. It is a competency framework for the humans who supervise them, built with the Behavioral Skills Training method she used as a clinician: instruction, modelling, rehearsal, feedback, with mastery defined as observable behaviour, not attendance.

The failure mode it exists to prevent: a domain expert in an unfamiliar agentic environment becomes uncertain, over-relies on agent output, and loses agency. The target: the expert understands the environment, directs the agent, evaluates output, corrects errors, delegates deliberately, and stays the decision-maker. Ten competencies, from environmental fluency and agent literacy through instruction, decomposition, delegation, verification (catch seeded errors at an agreed rate), correction, orchestration, generalization to an unfamiliar agent, and independent agency. Maturity is staged: dependence, literacy, fluency, agency. Rehearsal happens against the client's live environment; the agents going live are the training stimuli.

## Built for Linggo LLMs, then sold

COM was built first to run Linggo LLMs itself, through the period when the company was being rebuilt by one person. In August 2026 an early-stage AI startup, met through a women-in-AI community, bought the system as a paid engagement: an eight-week Launch Lab in which the founder built their AI-native operating system in Notion across three machines (company, customer, product), delivered a baseline report, a leadership dashboard and data room, worker workspaces, a CRM sync, agent specifications, and a readiness assessment, and trained the team to run it independently. The engagement produced the reusable template the system is now packaged as: a playbook with engagement anchors, four source databases, a 7-day sprint structure, the six-field go-live gate, and the training framework above.

Everything client-facing is a duplicate of a master template; nothing in the master is shared with a client directly; patterns proven on an engagement are brought back to the master rather than left in the client's tree.

## Where it shows up in the GitHub organization

- [`linggollms-ops`](apps/support-repos.md): the Command Center robot, a daily GitHub Action that reads GitHub, Notion and AWS (read-only) and writes a live status line per workstream back into the operating system.
- [`socialmedia_agent`](apps/support-repos.md): the social media agent and the self-hosted scheduler it posts through.
- Each app repo's `CLAUDE.md` and `AGENTS.md`: the working rules the coding agent reads at the start of every session, which is COM's "worker spec" idea applied to engineering.
- The weekly product history and documentation map, generated from the repos and kept in Notion for reading and commenting.

See [Agents](agents.md) for the agents themselves.
