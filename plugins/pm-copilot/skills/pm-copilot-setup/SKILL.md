---
name: pm-copilot-setup
description: Set up PM Co-Pilot in a workspace by creating an AGENTS.md routing brain and local memory scaffold from the user's confirmed context. Use for first-time setup or when the user asks to configure PM Co-Pilot.
---

# PM Co-Pilot setup

Set up the user's personal routing brain and memory. This is the point where the generic workflow becomes specific to them.

## Ground rules

- Ask questions conversationally in small batches, not as one giant form.
- Offer sensible defaults and proposed answers from connected tools when available. The user can accept, correct, or skip each item.
- Never invent facts about the user, company, colleagues, priorities, or tools.
- Use only tools that are actually connected in the current Codex environment.
- Write only to the workspace folder the user confirms.
- Show a concise write preview and get confirmation before creating or changing files.

## Step 1: Locate the workspace

Confirm the folder where `AGENTS.md` and `memory/` should live. A fresh folder keeps this system separate from other Codex instructions.

Before writing anything, check the selected folder:

- If it already contains `AGENTS.md` or `memory/`, stop and explain that setup will not overwrite it.
- Offer either a fresh folder, or a guided merge of the existing `AGENTS.md` and memory files.
- Continue only after the user chooses and confirms the safe path.

## Step 2: Check connected tools

Note which relevant tools are available: chat or messaging, task tracker, email, calendar, meeting notes or transcripts, and documents. Use connected tools to propose answers and say which workflow steps will be skipped when a source is unavailable.

## Step 3: Ask setup questions in short batches

Use a few conversational rounds. For each answer, make it clear that the user can accept the proposal, adjust it, or skip it.

### About the user

- Name
- Role or title, defaulting to Product Manager when appropriate
- Company and one-line description
- Work email domain
- Location and timezone
- Manager, proposed from recurring one-to-ones when possible
- Current focus
- What they are working toward, optional

### Tools and working surface

- Chat or messaging tool
- Task tracker and its lists or statuses
- Email
- Calendar
- Meeting notes or transcripts
- Documents store
- Optional personal capture channel
- Any tools the company does not allow

If the user has no task tracker, offer either a simple markdown board in the workspace or a connected task tool. Do not create one without confirmation.

### Key people and channels

When chat or calendar is connected, propose priority channels and VIPs using recent activity. Include a brief reason for each proposal. Otherwise ask the user for a short list.

### Rhythm and voice

- Week start
- Week wrap-up or review time
- Morning brief time and timezone
- Non-working days or holidays
- General tone
- Writing habits or things to avoid
- Optional examples of the user's writing

## Step 4: Preview and write

Use the templates bundled with this plugin:

- `templates/AGENTS.md`
- `templates/memory/role.md`
- `templates/memory/colleagues.md`
- `templates/memory/scope.md`
- `templates/memory/day-to-day.md`
- `templates/memory/voice.md`
- `templates/memory/decisions.md`

Create the full scaffold in the confirmed workspace:

- `AGENTS.md`
- `memory/role.md`
- `memory/colleagues.md`
- `memory/scope.md`
- `memory/day-to-day.md`
- `memory/voice.md`
- `memory/decisions.md`
- `memory/topics/`
- `memory/state/`
- `memory/context-gaps.md`
- `memory/context-watchlist.md`
- `memory/skill-improvements.md`
- `memory/meeting-prep-recurring.md`
- `memory/_backups/`

Fill only facts the user provided or confirmed. Leave skipped fields blank. Show a short summary of what each file will contain, then write only after confirmation.

## Step 5: Close

Confirm what was written and which workflow steps are live or skipped based on connected tools. Then tell the user:

- Codex will load `AGENTS.md` automatically when working in the workspace.
- Run `$pm-copilot-first-run` for a calibration pass.
- Invoke `morning-brief`, `weekly-prep`, `open-loops`, `self-improvement`, `sync`, or `consolidate` whenever needed.
- Add topic files under `memory/topics/` as projects recur.
