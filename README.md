# AgenticProjectInitializer

A vendor-neutral master prompt for creating clean, agent-friendly project structures with a persistent `AGENTS.md` file.

## What This Is

This repository gives you one reusable **master prompt** to start projects in an agent-friendly way.

It helps you create a structure that both humans and AI agents can understand and maintain over time.

You get:
- clear structure
- clean separation of concerns
- reusable workflows
- long-term maintainability
- vendor-neutral setup (no lock-in)

## What "Agentic" Means

Here, "agentic" means using an AI agent as an active project partner, not just for one-off chat answers.

A simple way to think about it:
- you give the goal
- the agent asks setup questions
- the agent proposes structure and next steps
- you review and approve
- the agent helps keep things organized over time

This is not only for coding. The same process works for:
- teaching and course planning
- writing projects
- research workflows
- documentation systems
- mixed projects with code, text, and media

The key idea is persistence: important decisions live in project files (especially `AGENTS.md`), so future work does not depend on old chat history.

## Working With an Agent (Editor or Chat)

If you use VS Code, this feels like chatting with a project assistant inside your editor.

Typical workflow:
- open your project folder
- interact with the agent in editor chat, terminal, or web app
- let it propose edits and structure
- review changes, then approve
- keep rules and decisions in files

## Agent Tools You Can Use

This initializer is vendor-neutral, so you can use whichever tool fits your workflow and comfort level.

- OpenAI Codex: [https://openai.com/codex/](https://openai.com/codex/)
- Codex IDE docs: [https://developers.openai.com/codex/ide](https://developers.openai.com/codex/ide)
- Codex for VS Code (Marketplace): [https://marketplace.visualstudio.com/items?itemName=openai.chatgpt](https://marketplace.visualstudio.com/items?itemName=openai.chatgpt)
- Claude Code overview: [https://docs.anthropic.com/en/docs/claude-code/overview](https://docs.anthropic.com/en/docs/claude-code/overview)
- Google Antigravity: [https://antigravity.google/](https://antigravity.google/)

## What Problem It Solves

Many new projects run into:
- messy folder structures
- mixed source files and generated files
- scattered scripts
- no persistent guidance for agents
- too much reliance on chat context

This project helps by enforcing:
- a clean setup process
- a standard `AGENTS.md`
- consistent organization from day one

## What You Get

- [`master-prompt.md`](master-prompt.md)
  A setup prompt that:
  - asks about project purpose
  - collects requirements
  - proposes a tailored structure
  - drafts `AGENTS.md`

## How to Use

1. Create a new project folder (local or GitHub).
2. Open that folder in your editor or agent tool so it is the active working context.
3. Copy the contents of `master-prompt.md`.
4. Paste the prompt contents into your preferred AI tool.
5. Answer the setup questions.
6. Review the proposed structure.
7. Approve and apply:
   - folder structure
   - `AGENTS.md`
   - starter files (if useful)

## Beginner-Friendly Workflow

If you are new, the prompt can guide you step by step.

It may:
- ask clarifying questions
- spot missing inputs
- offer an optional setup checklist file before building folders

### Optional Setup Checklist

The checklist can help you:
- gather source materials
- define outputs
- identify constraints
- organize references

When used, the checklist should be created as `setup-checklist.md` (not just posted in chat).

You can use it first, or skip it and continue.

### Example: TEJ 3M Course Planning

A teacher planning a Grade 11 TEJ 3M Computer Engineering Technology course (Ontario, Canada) can use the checklist to prepare:
- curriculum expectations and unit goals
- lesson and lab plans
- rubrics and assessments
- safety and classroom constraints
- policy and reference documents

This makes the generated structure more accurate on the first pass.

## Core Concepts

### AGENTS.md

This is the main instruction file for the project.

It defines:
- purpose and scope
- folder map
- working rules for agents
- conventions for scripts, workflows, and outputs

It replaces vendor-specific files such as:
- `CLAUDE.md`
- `GEMINI.md`

### Scripts vs Skills

- `scripts/`
  Shared project utilities

- `skills/`
  Reusable agent workflows

Example skill layout:

```text
skills/
`-- example-generic/
    |-- SKILL.md
    |-- scripts/
    |   `-- example-task.ps1
    `-- references/
        `-- README.md
```

### Clean Root Principle

Keep the project root minimal and intentional.

Avoid:
- random scripts
- temporary files
- mixed concerns

## Example Project Structure

```text
my-project/
|-- AGENTS.md
|-- README.md
|-- docs/
|-- src/
|-- scripts/
|-- skills/
|   `-- research-assistant/
|       |-- SKILL.md
|       |-- prompts/      (optional)
|       `-- examples/     (optional)
`-- data/                 (optional)
```

## Preparing Source Materials

Best formats for AI-friendly reuse:
- Markdown (preferred)
- plain text
- PDF (works, but less ideal for repeated use)

If you depend on curriculum docs, policies, or papers, converting PDFs to Markdown first is recommended.

Free utility (Mac and PC):
- [Pete's PDF to MD](https://github.com/pbeens/Petes-PDF-to-MD)

## Design Principles

- Start with purpose, not structure
- Keep root clean
- Separate source files from generated output
- Group reusable workflows
- Avoid vendor lock-in
- Prefer clarity over cleverness
- Scale only when needed

## When to Use This

Good for:
- software projects
- writing/book projects
- curriculum design
- research projects
- documentation systems
- knowledge bases
- hybrid projects

## When Not to Use This

May be overkill for:
- throwaway projects
- one-file experiments
- quick prototypes with no structure needs

## Philosophy

An agentic project is more than a folder.

It is a system where:
- structure carries intent
- instructions persist beyond chat
- workflows are reusable
- humans and agents can work reliably

## Project History

See [CHANGELOG.md](CHANGELOG.md) for release history.

## License

[MIT License](LICENSE)
