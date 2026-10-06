# Update Ticket

Standard process for updating a ticket in your tracker (Jira, Linear,
GitHub Issues, etc.) in a way that stays consistent across employees.

> This is a stub — fill in the actual steps for your tracker. The pattern
> worth keeping regardless of tool:

## When to use

When meaningful progress, a decision, or a status change on a piece of work
needs to be reflected back in the ticket tracker, not just in the local
workspace's TASK.md.

## Steps

1. Identify the ticket from the workspace's `workspace.yaml` or
   `~/workspaces.yaml` entry.
2. State what changed: comment text, status transition, fields to update.
3. Ticket writes are `approval_required` for every employee by default
   (see each employee's `permissions` block) — confirm with the user before
   posting, transitioning, or editing a ticket.
4. After the write succeeds, update the workspace's `TASK.md` and
   `~/workspaces.yaml` entry so the local record and the tracker agree.

## Notes

- Keep time-tracking/worklog entries in whatever field your tracker uses
  for that (e.g. a worklog), not duplicated into the visible comment text.
- When flagging a ticket for attention, quote its exact title/subject
  rather than paraphrasing it.
