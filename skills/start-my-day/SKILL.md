# Start My Day

The Chief of Staff's daily briefing. Pulls together calendar, email/ticket
triage, git status across active repos, and active workspace status into one
briefing at the start of the day.

**This file is a skeleton.** The real value of this skill comes from
replacing the placeholder sections below with your own actual sources —
your real calendar, your real ticket queue, the specific inboxes/labels you
personally need triaged. Copy the shape, not the content.

## When to use

When you say "start my day" (or equivalent — "what's on my plate", "morning
briefing"), regardless of which directory the session was started in.

## What to gather

### 1. Calendar

Today's calendar events (primary calendar). Lead with anything starting soon
or already in progress.

### 2. Ticket triage

> Replace this section with how new work actually lands in your inbox —
> e.g. a specific ticket queue, a specific email label, a Slack channel.
> Name the real source and what counts as "new" vs. "already being
> tracked."

Cross-check incoming items against `~/workspaces.yaml`: if an incoming
ticket already has a workspace entry, say so and surface its `next_action`
instead of treating it as brand-new triage.

### 3. Labeled mailbox / channel checks

> List here the specific mailbox labels, folders, or channels that need a
> dedicated check each day, and what "needs attention" looks like for each
> one. Also list anything that should be explicitly excluded from this
> check (high-volume automated noise you've decided not to see daily) —
> being explicit about exclusions prevents it from silently creeping back
> in.

### 4. Active workspace review

Read `~/workspaces.yaml`. For each workspace with `status: active`, list its
title, employee, and `next_action`. This covers both project repos (`~/code`)
and operational work (`~/work`) in one place.

### 5. Git status across ~/code

Sweep `~/code` for uncommitted/untracked work. Several untracked or
work-in-progress directories at any given time is normal if you work out of
many project subdirectories at once — report as an FYI, not an action item,
unless asked.

## How to present the briefing

1. Meetings (esp. anything soon/already started)
2. Ticket triage (new vs. already-tracked in a workspace)
3. Active workspace next actions (from `~/workspaces.yaml`)
4. Labeled-mailbox/channel checks, each as its own section
5. Uncommitted git work across `~/code`, as an FYI

Keep it scannable — lead with what needs a decision or response today, and
call out explicitly if nothing needs action in a given section.

## Notes

- This runs regardless of what directory the session started in — always
  read `~/workspaces.yaml` and sweep `~/code`, not just the cwd.
- Do not take action (replying to email, transitioning tickets,
  committing/pushing code) as part of this briefing — surface, don't act.
