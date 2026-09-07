# PM Co-Pilot for Codex

> 🎙️ **Featured on How I AI with Claire Vo**: [Watch](https://www.youtube.com/watch?v=p2qmX6TM0kw) · [Listen](https://open.spotify.com/episode/75Adi3KXzDDXIZEJmnv6N6) · [Read](https://www.lennysnewsletter.com/p/how-i-turned-claude-into-a-self-improving)

Being a PM means holding fifty things in your head at once. Tasks pile up across email, chat, and meetings and keep reshuffling while you are stuck in back-to-back calls. The real work, talking to users and digging into the data, gets squeezed out.

PM Co-Pilot carries that overhead so you can get back to it. It catches what comes at you, keeps it organized, and surfaces what actually needs you.

This fork brings the original PM Co-Pilot workflows to Codex as a reusable plugin.

## How it works

You give it context up front: your role, your people, your priorities, and how you like to work. After that, it keeps that memory up to date as you go and fills its own gaps instead of waiting for you to spell everything out.

The more context you give it, the more useful it becomes. Connect the tools you already use and run more of your work through the workflows.

Four core workflows handle the day-to-day, and they build on each other:

- **Weekly prep** starts your week. It pulls from your tools and walks you through setting your priorities and focus.
- **Morning brief** refreshes that each morning: what came in, what is done, and what today needs.
- **Open loops** catches the threads you would otherwise lose, what you are waiting on and who is waiting on you.
- **Self-improvement** closes the week by learning from how you worked and improving your setup.

It checks with you before doing anything, and your memory stays in the workspace you choose.

## What is included

Setup writes two things into your workspace:

- `AGENTS.md`, the Codex routing brain that loads the right memory by topic
- `memory/`, a local folder for your role, people, priorities, decisions, tools, and writing voice

### Skills

- `morning-brief`, a daily capture, inbox cleanup, close-check, and meeting-prep pass
- `weekly-prep`, a guided review that updates the task board only after approval
- `open-loops`, a digest of work waiting on you and work waiting on others
- `self-improvement`, a weekly review of voice signals, repeatable workflows, and system friction
- `memory-keeper`, a propose-only memory capture and context-gap workflow
- `sync`, a propose-only refresh from connected tools
- `consolidate`, a propose-only cleanup and backup pass for local memory
- `pm-copilot-setup`, the first-time workspace setup workflow
- `pm-copilot-first-run`, a safe calibration run for all four core workflows

If a tool is not connected, the relevant workflow step is skipped. External actions are never taken without the user's approval.

## What you need

- Codex with plugin support
- A workspace where PM Co-Pilot can create `AGENTS.md` and `memory/`
- The work tools you want to use, connected through Codex plugins or MCP

Useful sources include chat or messaging, email, calendar, task tracking, meeting notes, transcripts, and documents.

## Install from GitHub

Add this repository as a Codex marketplace:

```bash
codex plugin marketplace add omriuzrad-simply/pm-copilot
```

Then install **PM Co-Pilot** from the marketplace in the Codex app or plugin browser.

From a new Codex session, run:

```text
$pm-copilot-setup
```

After setup, run the calibration pass:

```text
$pm-copilot-first-run
```

## Running it

Invoke a workflow whenever you want it:

- `morning-brief` each morning
- `weekly-prep` at the start of the week
- `open-loops` and `self-improvement` for a periodic sweep
- `sync` followed by `consolidate` to refresh local memory

Run the workflows from the workspace containing `AGENTS.md` and `memory/`, so they can access local context. Scheduled runs may not be able to access local memory, so run these workflows yourself for now.

## Local development

The plugin lives in `plugins/pm-copilot/`.

The repository includes a repo-local marketplace at `.agents/plugins/marketplace.json`. To test a local checkout:

```bash
codex plugin marketplace add ./
```

Validate the plugin manifest and skill layout with:

```bash
python3 /root/.codex/skills/.system/plugin-creator/scripts/validate_plugin.py plugins/pm-copilot
```

## Credits

The workflows are adapted from the original [PM Co-Pilot project](https://github.com/IamBlum/pm-copilot), created by Daniel Blum.

## Feedback

For feedback on the original project, contact [itsdanielsagent@gmail.com](mailto:itsdanielsagent@gmail.com).

## License

MIT.
