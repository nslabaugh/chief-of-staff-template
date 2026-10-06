# AI Work Environment

This Linux home directory is the root of my AI-assisted work environment.

## Directory Structure

- ~/code — software projects and Git repositories
- ~/work — operational work, tickets, investigations, vendor issues, and configuration tasks
- ~/employees — AI employee/agent definitions
- ~/skills — reusable workflows and capabilities
- ~/workspaces.yaml — central registry of project and operational workspaces

## Employee System

Employee definitions are stored in:

~/employees/

The employee registry is:

~/employees/index.yaml

Employees are specialized roles that can work across project repositories under
~/code and operational workspaces under ~/work.

Do NOT automatically assume an employee role when Claude starts.

The current tmux/workspace context or explicit user instruction determines which
employee role should be used.

## Workspace Registry

The central workspace registry is:

~/workspaces.yaml

Use it to determine:

- workspace ID
- workspace title
- workspace type
- filesystem path
- assigned employee
- ticket reference (Jira, or whichever tracker you use)
- current status
- next action

Before creating a new workspace, check this registry for an existing workspace.

## Persistent State

Claude conversation history is NOT the authoritative source of work state.

Important information must be persisted to disk.

For operational work, use the workspace TASK.md to maintain:

- objective
- current state
- decisions
- open questions
- next action
- completed work
- blockers / waiting on

For project repositories, use the project's existing documentation and task
files.

## Skills

Reusable workflows live under:

~/skills/

Employees may use skills appropriate for their role.

Inspect the appropriate skill instructions before performing that workflow.

## Session Startup

When Claude starts from the home directory:

1. Understand this environment.
2. Read ~/employees/index.yaml if employee information is needed.
3. Read ~/workspaces.yaml if workspace information is needed.
4. Do NOT automatically become Chief of Staff.
5. Do NOT automatically load every employee, skill, project, or work item.
6. Wait for the current workspace or user request to determine the appropriate role.
7. Treat persistent files as the source of truth rather than previous Claude conversations.

## Change Control

Reading and analysis may generally happen without approval.

Follow the permissions defined by the active employee.

Do not automatically perform consequential production changes, external
communications, ticket-tracker writes, deployments, or other external writes
unless the active employee permissions and user approval allow them.

## Customizing This Template

This file, and everything under ~/employees and ~/skills, is a starting
skeleton — not a finished setup. To make it yours:

1. Replace the example employee in ~/employees/example-specialist.yaml with
   roles that match your actual work, and update ~/employees/index.yaml to
   match.
2. Rewrite ~/skills/start-my-day/SKILL.md around your actual calendar,
   inbox, and ticket system — the version in this template is a skeleton
   with placeholders, not a working briefing.
3. Clear out the example entry in ~/workspaces.yaml and start tracking your
   own workspaces as you create them (see ~/skills/create-workspace).
4. Update the mentions of "Jira" throughout if you use a different tracker
   (Linear, GitHub Issues, Asana, etc.) — the pattern (ticket read/write
   permission split, cross-referencing workspaces) carries over regardless
   of the specific tool.
