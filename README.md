# Chief of Staff — Claude Code Template

A starter framework for running Claude Code as a persistent "Chief of Staff"
across your work: a home-directory `CLAUDE.md` that defines the environment,
a set of named "employee" roles with their own scope and permissions, a
registry of active workspaces, and reusable skills they share.

This is a template, not a finished setup — every file is a skeleton with
real structure but placeholder content. Expect to spend 20-30 minutes
customizing it before it's useful day to day.

## How it fits together

```
~/CLAUDE.md          — environment rules Claude reads at session start
~/employees/          — one YAML file per role Claude can operate as
  index.yaml          — registry of employees, pointing to their files
  chief-of-staff.yaml — the coordinating role (keep this one largely as-is)
  example-specialist.yaml — template for a specialist role (replace)
~/skills/             — reusable workflows, referenced by employees
  create-workspace/    — how to open a new tracked piece of work
  start-my-day/        — the daily-briefing workflow (heavily customize)
  update-ticket/        — how ticket-tracker writes should happen
~/workspaces.yaml     — single registry of all active/past work
~/work/               — operational workspaces (tickets, investigations)
~/code/               — software projects / Git repos
```

An "employee" is a role definition, not a separate AI — it's a YAML file
describing a scope of responsibility and an explicit permission boundary
(what it can do freely, what needs your approval, what it should never do).
You tell Claude which employee to act as (or let the current workspace
imply it); Claude reads that file and operates within its stated bounds.

## Setup

1. Copy this repo's contents into your home directory (or wherever you
   want the root of this environment to live), merging with anything
   already there.
2. Edit `CLAUDE.md` for your actual directory layout if it differs.
3. Copy `employees/example-specialist.yaml` once per real role you want,
   rename each copy, fill in its `purpose`, `responsibilities`, and —
   especially — its `permissions` block. Add each one to
   `employees/index.yaml`.
4. Rewrite `skills/start-my-day/SKILL.md` around your actual calendar,
   ticket queue, and any inboxes/channels worth a daily check. This file
   does the most "lifting" in the whole template and is the most
   company/person-specific by nature.
5. Delete the example entry in `workspaces.yaml`; start adding real entries
   as you create workspaces via the `create-workspace` skill.
6. If you use a ticket tracker other than Jira, do a find-and-replace for
   "Jira" across these files, or just adjust field names as you go — the
   pattern (read access by default, write access gated behind approval)
   matters more than the specific tool.

## Design principles worth keeping

- **Persistent state lives on disk, not in chat history.** Each workspace
  has a `TASK.md` that's the source of truth for its current state —
  conversations are not.
- **Permissions are explicit and skew conservative.** Default new
  permissions to `approval_required` or `false` rather than `true`, and
  loosen deliberately once you trust the pattern.
- **One registry, not scattered state.** `~/workspaces.yaml` is the single
  place to check "what's active and what's next," across both project
  repos and operational work.
- **Don't let Claude self-assign a role.** `CLAUDE.md` explicitly says not
  to assume the Chief of Staff (or any) role automatically — the current
  context or an explicit instruction should decide that.
