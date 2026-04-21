# Studio OS Harness Template

> A forkable, portable AI harness — system prompts, tools, skills, webhooks, and automations bundled as a complete deployable stack.

## What Is a Harness?

A **harness** is everything a model needs to operate correctly in a specific context. It goes beyond a single system prompt — it's the full stack:

| Layer | What it contains |
|---|---|
| `prompts/` | System prompts as structured `.json` + `.md` pairs |
| `tools/` | Tool schemas the model can invoke |
| `skills/` | Domain knowledge, reference docs, SOPs |
| `webhooks/` | Event trigger definitions |
| `automations/` | Multi-step workflow specs |
| `harnesses/` | Named, pre-assembled harness bundles |

## Quick Start

1. **Fork this repo** for your use case (e.g. `lashfit-harness`, `calendar-harness`)
2. Edit `HARNESS.md` to describe your harness type and purpose
3. Add prompts to `prompts/` following the schema in `prompts/_template.json`
4. Add tools to `tools/` following the schema in `tools/_template.json`
5. Assemble a named harness in `harnesses/` that references your prompts + tools
6. Connect to your codebase or LLM via the index at `harness.index.json`

## Harness Types

Set `type` in `HARNESS.md` to one of:

- `dev-assistant` — coding, spec writing, repo management
- `customer-service` — support, intake, FAQ, escalation
- `scheduling` — calendar, booking, reminders, availability
- `medical` — intake, triage, aftercare, documentation
- `creative` — writing, brainstorming, content generation
- `sales` — outreach, objection handling, follow-up
- `custom` — define your own

## Model-Specific Harnesses

See `harnesses/` for pre-built seeds:
- `harnesses/claude-code/` — seeded from Claude Code's known prompt architecture
- `harnesses/cursor/` — seeded from Cursor Agent's known prompt architecture

## Repo Structure

```
studio-os-harness-template/
├── HARNESS.md                  ← harness identity card
├── harness.index.json          ← machine-readable index of all prompts + tools
├── prompts/
│   ├── _template.json          ← prompt schema
│   └── example-prompt.json
├── tools/
│   ├── _template.json          ← tool schema
│   └── example-tool.json
├── skills/
│   └── example-skill.md
├── webhooks/
│   └── example-webhook.json
├── automations/
│   └── example-automation.md
└── harnesses/
    ├── claude-code/
    │   ├── system-prompt.md
    │   └── harness.json
    └── cursor/
        ├── system-prompt.md
        └── harness.json
```
