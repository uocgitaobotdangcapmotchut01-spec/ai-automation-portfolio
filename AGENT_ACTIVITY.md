# AGENT_ACTIVITY

## Purpose

A short, append-only record of what each agent or the Human did in the repository, so anyone can see recent activity at a glance. It does not replace `LOG.md` (task handoffs) or `DECISIONS.md` (decisions). Recording activity grants no authority: only the Human makes final decisions.

## Entry format

Each entry has five fields: `Date / Agent / Task ID / Action / Result`.

- Date: `YYYY-MM-DD`
- Agent: `ChatGPT`, `Claude`, `Grok`, or `Human`
- Task ID: `TASK-XXX`, or `N/A` for human-requested work without a task
- Action: what was done, in one short sentence
- Result: what actually happened

## Rules

- Append only. Add new entries at the bottom of the table. Do not edit or delete existing entries.
- One row per meaningful action. Do not backfill earlier history.
- Write only what actually happened. Do not claim testing, review, or commits that did not occur.
- Never record secrets, credentials, tokens, private information, or other sensitive data (DEC-008).

## Entries

| Date | Agent | Task ID | Action | Result |
|---|---|---|---|---|
