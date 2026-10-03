# DECISIONS

Append-only. Never edit or delete an existing entry. To change or reverse something, add a new entry that references the old one.

## Rules

- Every entry has `Type: PROPOSAL` or `Type: DECISION`.
- A PROPOSAL is only a suggestion. It binds no one.
- A DECISION requires explicit human approval. `Decided by` must name the human.
- No agent may silently convert a proposal into a decision. To promote a proposal, the human approves it and a new DECISION entry is appended that references the proposal ID.
- Decision IDs are stable: `DEC-001`, `DEC-002`, ... (one sequence for both types).
- Add new entries at the bottom, using the template below.

## Entry template

```
### DEC-XXX
- Type: PROPOSAL | DECISION
- Date: YYYY-MM-DD
- Decision: <what is proposed or decided>
- Reason: <why>
- Decided by: <human name or role; for a PROPOSAL, write "Proposed by <agent>, not yet decided">
- Affected components: <files, agents, tools>
- Context version: <CTX-XXX introduced or affected>
```

## Entries

### DEC-001
- Type: DECISION
- Date: 2026-10-03
- Decision: The GitHub repository is the initial shared source of truth for project state. Notion and Google Drive are not used for this.
- Reason: Plain text files are versioned, diffable, and readable by every agent.
- Decided by: Human (explicit approval in session, 2026-10-03)
- Affected components: PROJECT.md, DECISIONS.md, TASKS.md, LOG.md
- Context version: CTX-001

### DEC-002
- Type: DECISION
- Date: 2026-10-03
- Decision: The system stays manual for now. Make.com, webhooks, and automatic agent triggering are not connected.
- Reason: Establish and test the collaboration loop by hand before automating any step.
- Decided by: Human (explicit approval in session, 2026-10-03)
- Affected components: Make, all agents
- Context version: CTX-001

### DEC-003
- Type: DECISION
- Date: 2026-10-03
- Decision: The human owns project decisions and final approval. Agents own execution of their assigned tasks. An agent may update its own task and move it only up to REVIEW. Only the human may mark a task DONE.
- Reason: Keeps one accountable decision-maker and prevents agents from approving their own work.
- Decided by: Human (explicit approval in session, 2026-10-03)
- Affected components: TASKS.md, all agents
- Context version: CTX-001

### DEC-004
- Type: DECISION
- Date: 2026-10-03
- Decision: Every handoff must identify the context version it was based on and include an Evidence field. Every task and log entry has a stable ID. Every decision is explicitly marked PROPOSAL or DECISION. Context versions use the format CTX-001, CTX-002, ... and increment only on material decisions.
- Reason: Prevents agents from working from different assumptions and prevents untested claims.
- Decided by: Human (explicit approval in session, 2026-10-03)
- Affected components: LOG.md, TASKS.md, DECISIONS.md, PROJECT.md
- Context version: CTX-001

### DEC-005
- Type: DECISION
- Date: 2026-10-03
- Decision: The approved project definition has been revised to explicitly define the website audience, goal, constraints, non-goals, and current collaboration phase. These changes constitute CTX-002.
- Reason: The previous CTX-001 definition was incomplete. The revised context is now the authoritative project definition for future work.
- Decided by: Human + ChatGPT
- Affected components: PROJECT.md, future tasks, future agent handoffs.
- Context version: CTX-002

### DEC-006
- Type: DECISION
- Date: 2026-10-03
- Decision: The human is the sole final decision-maker for project-level decisions. ChatGPT acts as an advisor, architect, and reviewer. Claude and Grok act as execution/specialist agents and do not have final decision authority.
- Reason: Clarifies decision authority. The "Human + ChatGPT" wording in DEC-005 left it ambiguous whether it conflicts with DEC-003. DEC-005 is not modified.
- Decided by: Human (explicit instruction, 2026-10-03)
- Affected components: all agents, PROJECT.md, DECISIONS.md
- Context version: CTX-002

### DEC-007
- Type: DECISION
- Date: 2026-10-03
- Decision: The canonical shared project repository is the GitHub repository named `ai-automation-portfolio`.
- Reason: A single version-controlled repository is required as the project's initial shared source of truth for documentation, project context, case studies, and eventually website code.
- Decided by: Human
- Affected components: PROJECT.md, agent handoffs, project documentation, future website implementation.
- Context version: CTX-002

### DEC-008
- Type: DECISION
- Date: 2026-10-03
- Decision: The public repository must never contain secrets, API keys, access tokens, passwords, private credentials, client personally identifiable information, confidential contracts, private business data, or other non-public sensitive information. Project documentation must use placeholders or sanitized examples when such information is needed to describe a workflow.
- Reason: The repository is public and is intended to function as a portfolio and shared project source of truth.
- Decided by: Human
- Affected components: PROJECT.md, DECISIONS.md, TASKS.md, LOG.md, future case studies, source code, and automation configuration.
- Context version: CTX-002
