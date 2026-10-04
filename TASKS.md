# TASKS

## Allowed states

`READY` | `IN_PROGRESS` | `BLOCKED` | `REVIEW` | `DONE`

- READY: defined, waiting for implementation.
- IN_PROGRESS: an agent is actively working on it.
- BLOCKED: cannot continue (dependency, technical issue, missing information, external limitation). State the reason in LOG.md.
- REVIEW: implementation is complete enough for another agent or the human to inspect.
- DONE: reviewed and accepted by the human.

## Rules

- The human or ChatGPT may create tasks.
- An agent may update its own task.
- An agent may move its own task only up to REVIEW.
- Only the human may mark a task DONE.
- A task cannot be DONE unless its acceptance criteria are satisfied.
- Every task has a stable ID (`TASK-001`, `TASK-002`, ...). IDs are never reused.
- Do not delete tasks. Keep finished tasks in the table.
- Every state change gets a LOG.md entry.
- Keep each row on a single line so the table stays machine-readable. Separate multiple acceptance criteria with `;`.

## Tasks

| Task ID | Title | Description | State | Owner | Acceptance Criteria | Context Version | Last Updated |
|---|---|---|---|---|---|---|---|
| TASK-001 | Establish shared project context | Create the four shared context files (PROJECT.md, DECISIONS.md, TASKS.md, LOG.md) and record the current project information. | DONE | Claude | (1) Four files exist; (2) Structure follows the specification; (3) Current project information is recorded; (4) No automatic agent triggering is implemented; (5) No website implementation is started; (6) No decision is presented as a decision unless explicitly approved by the human | CTX-001 | 2026-10-03 |
| TASK-002 | Apply approved project context revision | Apply the approved CTX-002 revision: update PROJECT.md, record the decision in DECISIONS.md, record this task in TASKS.md, and append an entry to LOG.md. No website, Make.com, or Grok work. | DONE | Claude | (1) PROJECT.md reflects CTX-002; (2) DECISIONS.md contains the new decision without altering historical decisions; (3) TASKS.md records TASK-002; (4) LOG.md contains a new append-only entry; (5) CTX-001 remains historically preserved; (6) No website implementation has started; (7) No Make automation has been added; (8) No Grok integration has been added | CTX-002 | 2026-10-03 |
| TASK-003 | Repository Safety Baseline | Implement the minimum practical safeguards required before the public repository begins containing real project code and case-study material. | DONE | Claude | (1) Add an appropriate .gitignore; (2) .gitignore covers at minimum .env, common credential/secret files, local configuration files that may contain credentials, and browser/session credential artifacts where applicable; (3) Add a concise repository security section to the project documentation; (4) Perform a basic secret-pattern scan over the current repository files; (5) Report scan limitations clearly (a pattern scan is not proof that the repository contains no secrets); (6) Do not expose or reproduce any discovered secret values in the output; (7) Do not add unnecessary security tooling or complex infrastructure; (8) Do not modify DEC-001 through DEC-008; (9) Do not create CTX-003; (10) Do not start website implementation; (11) Do not implement Make.com automation; (12) Do not integrate Grok; (13) Do not commit or push to GitHub unless explicitly authorized and technically possible | CTX-002 | 2026-10-03 |

## Notes

- TASK-001 was completed against CTX-001 only. Its row and acceptance criteria reflect the CTX-001 project definition, in which the audience was not yet defined. They do not include the CTX-002 requirements.
- The CTX-002 revision was applied by TASK-002. The TASK-001 row is unchanged apart from its state.
- TASK-001 and TASK-002 were marked DONE on 2026-10-03 on the explicit approval of the human. Only the human may mark a task DONE.
