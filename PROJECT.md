# PROJECT

Source-of-truth summary. Keep it short. This is not a diary: history goes in `DECISIONS.md` and `LOG.md`.

## Project

Personal AI Automation Portfolio

## Goal

Build a professional portfolio website that demonstrates real AI automation capability through case studies, workflow architectures, and working examples.

The website should eventually function as:

- a professional portfolio
- a case-study demonstration of the automation systems behind it

## Audience

Primary:

- potential automation clients
- small businesses
- founders
- people evaluating my AI automation skills

Secondary:

- technical people evaluating my projects and implementation ability

## Current Phase

Shared project infrastructure

Current Objective: establish a reliable collaboration protocol between ChatGPT, Claude, and eventually Grok before building the portfolio website.

## Constraints

- Keep the system simple.
- Avoid premature automation.
- No automatic agent triggering yet.
- No automatic task completion.
- Human remains the final decision maker.
- Do not invent results or credentials.
- Prefer practical implementation over unnecessary architecture.
- The project must remain manageable within limited daily working time.

Standing rules DEC-001 to DEC-004, DEC-006, and DEC-008 in `DECISIONS.md` remain in force.

Repository safety (DEC-008):

- No secrets or non-public sensitive information may be committed.
- `.env` files, credential files, exported connection data, browser session files, and other secret-bearing files must not be committed.
- Use placeholders or sanitized examples when sensitive information is needed for documentation.

## Non-Goals

- building the portfolio website during this infrastructure phase
- connecting Make.com to the agents
- creating webhooks between agents
- automatically triggering Claude or Grok
- implementing autonomous decision making
- creating a complex database
- building a full AI agent framework

## Agent Roles

| Agent | Role | Status |
|---|---|---|
| ChatGPT | Architecture, planning, project-level reasoning, review | Active |
| Claude | Implementation, coding, debugging, technical execution | Active |
| Grok | Web / visual / UX experimentation; research and review | Not active yet |
| Make.com | Future orchestration layer | Not active yet |
| Human | Final decisions and approval | Active |

Authority rules:

- The Human is the final decision-maker. No agent has final decision authority.
- ChatGPT is an architecture, planning, and review advisor. It has no final authority.
- Claude is the implementation and execution agent. It executes only when the Human authorizes it.
- Grok is a read-only research and review agent. It does not write or commit.
- Only the Human may move a task from REVIEW to DONE.
- Agent activity is recorded in `AGENT_ACTIVITY.md`. Recording activity grants no authority.

## Current Context Version

**CTX-002**

Versioning rule: format is `CTX-001`, `CTX-002`, ... Increment only when a material project decision changes the shared context. Do not increment for trivial wording changes. When the version changes, update this section and record the reason in `DECISIONS.md`.

## Context History

| Version | Summary | Record |
|---|---|---|
| CTX-001 | Initial definition. Audience was not yet defined. Preserved as historical context. | DEC-001 to DEC-004, LOG-001 |
| CTX-002 | Revised definition: explicit audience, goal, constraints, non-goals, and collaboration phase. Authoritative for future work. | DEC-005, LOG-002 |

## Repository

- Name: `ai-automation-portfolio`
- Platform: GitHub
- Visibility: Public
- Purpose: Canonical source of truth for the portfolio project, shared AI context, case studies, and eventually the website code.
- URL and owner/account: not recorded.
- Decision: DEC-007

## Repository Security

- Secrets and non-public sensitive information must never be committed (DEC-008).
- `.gitignore` blocks common secret-bearing files: environment files, key and credential files, local configuration files, and browser session files. It is a safety net, not a guarantee: it does not affect files already tracked by Git and does not stop a forced add.
- Exported automation blueprints can contain webhook URLs and connection identifiers. They are not ignored, because sanitized blueprints may be published as case studies. Sanitize them before committing.
- Before each commit, review the staged changes for secrets and personal data.
- If a secret is ever committed, treat it as compromised and revoke or rotate it. Deleting the file does not remove it from Git history.
