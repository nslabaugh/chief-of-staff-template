# Create Workspace

Standard process for creating an operational workspace under `~/work`.

## When to use

Use this when a new piece of operational work (a ticket, investigation,
vendor issue, configuration task, etc.) needs a home and does not already
have one. Prefer resuming an existing workspace over creating a duplicate —
check `~/workspaces.yaml` first.

## Standard workspace structure

```
~/work/<identifier>-<short-name>/
  TASK.md
  NOTES.md
  workspace.yaml
  attachments/
```

The `<identifier>` may be a ticket ID such as `PROJ-1842`, or another
meaningful work identifier if there is no ticket.

## Steps

1. Choose an identifier and short name (e.g. `PROJ-1423-short-name`).
2. Create the directory `~/work/<identifier>-<short-name>/` with an
   `attachments/` subdirectory.
3. Create `workspace.yaml` in that directory using this structure:

   ```yaml
   id: PROJ-1423
   title: Short description of the work
   type: ticket
   path: ~/work/PROJ-1423-short-name
   employee: example-specialist
   jira: PROJ-1423
   status: active
   next_action: The single next concrete step
   ```

   Omit `jira` (or rename the field to match your tracker) if there is no
   associated ticket. `type` may be `ticket`, `project`, or another
   meaningful category.

4. Create `TASK.md` with these headings:

   - Objective
   - Ticket
   - Employee
   - Systems
   - Current State
   - Decisions
   - Open Questions
   - Next Action
   - Completed
   - Waiting On
   - Notes for Claude

   Under "Notes for Claude", include:

   - Read TASK.md before doing meaningful work.
   - Preserve important decisions.
   - Update Current State as work progresses.
   - Keep Next Action current.
   - Record blockers under Waiting On.
   - Do not perform production writes without explicit approval.
   - Ask before consequential ticket-tracker writes, external emails, or
     production changes.
   - Before ending meaningful work, make sure TASK.md reflects the current
     state.

5. Create `NOTES.md` with:

   ```
   # Working Notes

   Use this file for investigation notes, temporary findings, commands,
   URLs, and other supporting information that does not belong in TASK.md.
   ```

6. Add an entry for the new workspace to `~/workspaces.yaml`, keyed by the
   identifier, mirroring the fields in `workspace.yaml`.

## Notes

- Do not automatically create a tmux session as part of this process.
- Not every workspace needs a ticket-reference field — only add it when a
  ticket exists.
