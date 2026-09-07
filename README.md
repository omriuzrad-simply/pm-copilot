# PM Co-Pilot for Codex

PM Co-Pilot is a local, context-aware operating system for product managers. It keeps user-approved memory about your role, people, priorities, decisions, and writing voice, then turns connected work sources into guided workflows.

This fork ports the original PM Co-Pilot workflows to the Codex plugin format.

## Included workflows

- `morning-brief`, a daily capture, inbox cleanup, close-check, and meeting-prep pass
- `weekly-prep`, a guided review that updates the task board only after approval
- `open-loops`, a digest of work waiting on you and work waiting on others
- `self-improvement`, a weekly review of voice signals, repeatable workflows, and system friction
- `memory-keeper`, a propose-only memory capture and context-gap workflow
- `sync`, a propose-only refresh from connected tools
- `consolidate`, a propose-only cleanup and backup pass for local memory
- `pm-copilot-setup`, the first-time workspace setup workflow
- `pm-copilot-first-run`, a safe calibration run for all four daily workflows

## How it works

Setup creates two parts in the workspace you confirm:

- `AGENTS.md`, the Codex instruction file that routes each request to the right memory files
- `memory/`, a local folder for role, colleagues, scope, tools, voice, decisions, and recurring topics

The workflows read local memory and any tools listed in `memory/day-to-day.md`. Missing tools are skipped. External actions are never taken without the user's approval.

## Install from GitHub

Add this repository as a Codex marketplace:

```bash
codex plugin marketplace add omriuzrad-simply/pm-copilot
```

Then install `PM Co-Pilot` from the marketplace in the Codex app, or use the plugin browser in your Codex environment.

From a new Codex session, run:

```text
$pm-copilot-setup
```

After setup, run:

```text
$pm-copilot-first-run
```

## Connect your tools

PM Co-Pilot is provider-neutral. Connect the services you already use through Codex plugins or MCP, then record the available tools in `memory/day-to-day.md` during setup.

Useful sources include:

- Chat or messaging
- Email
- Calendar
- Task tracker
- Meeting notes or transcripts
- Documents and project references

The skills only use sources that are available and named in your local memory.

## Local development

The plugin lives in `plugins/pm-copilot/`.

The repository also includes a repo-local marketplace at `.agents/plugins/marketplace.json`. To test a local checkout:

```bash
codex plugin marketplace add ./
```

Validate the plugin manifest and skill layout with the bundled Codex plugin validator:

```bash
python3 /root/.codex/skills/.system/plugin-creator/scripts/validate_plugin.py plugins/pm-copilot
```

## Credits

The workflows are adapted from the original [PM Co-Pilot project](https://github.com/IamBlum/pm-copilot), created by Daniel Blum.

## License

MIT.
