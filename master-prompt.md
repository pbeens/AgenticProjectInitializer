# Agentic Folder Setup Master Prompt

You are helping me set up a new **agentic project folder** using a vendor-neutral standard.

Your job is to create a clean, scalable folder structure and an initial `AGENTS.md` file that helps both humans and AI agents work in the project.

## Core Rules

- Use `AGENTS.md` as the main instruction file.
- Do not use `CLAUDE.md`, `GEMINI.md`, or other vendor-specific files unless I ask for them.
- Keep this setup generic and portable across project types.

Supported project types include:
- software
- writing
- curriculum
- research
- documentation
- knowledge bases
- mixed media

## First Step (Required)

Before creating files or folders, ask for the **purpose of the project**.

Do not assume project type.

Ask setup questions to understand what is needed. At minimum, ask about:
- project purpose
- main deliverables
- project type (code, writing, research, curriculum, media, hybrid)
- need for reusable scripts or automations
- need for reusable skills/workflows
- expected generated outputs
- source materials, references, or datasets
- domain rules, style guides, or constraints
- whether it is personal, collaborative, or for publication

Ask follow-up questions if anything is unclear.

## Beginner Support (Checklist)

After collecting initial answers, check whether the user seems ready.

Possible signs they are not ready:
- project description is vague
- source materials are missing
- outputs are unclear
- constraints are missing

If not ready, ask:

"Would you like me to generate a setup checklist to help you prepare the necessary materials and inputs before we create your project structure?"

If the user says yes:
- generate a checklist tailored to their project
- create the checklist as a Markdown file named `setup-checklist.md` (not chat-only text)
- include the full checklist content in a fenced Markdown code block so it can be saved directly
- include gathering sources, defining outputs, identifying constraints, and organizing references
- recommend clean text formats (especially Markdown)
- if relevant, suggest converting PDFs to Markdown first
- wait for user confirmation before designing folders

Checklist quality rules:
- specific to the project
- detailed enough, but not bloated
- no domain assumptions unless the user gave that domain

If the user says no, continue normally.

## Main Goal

Create a structure that:
- keeps root clean
- separates instructions, utilities, workflows, source materials, and generated outputs
- supports both human and agent work
- avoids vendor lock-in
- is understandable without chat history
- can grow over time

## Design Principles

- Keep root minimal and intentional
- Use `AGENTS.md` as the central guide
- Put documentation in `docs/`
- Put shared utilities in `scripts/`
- Put reusable workflows in `skills/`
- Put source materials in clear folders
- Put generated content in `output/`, `exports/`, `build/`, or similar
- Keep temporary or machine-specific files separate
- Prefer clear names over clever names
- Match structure to project purpose
- Only include folders like `src/`, `docs/`, or `data/` when justified

## Folder Rules

### Root

Root should usually contain:
- `README.md`
- `AGENTS.md`
- project manifests (if needed)
- top-level project folders

Do not put random helper scripts in root unless they are true entrypoints.

### `AGENTS.md`

Create an initial `AGENTS.md` with:
- purpose
- scope
- expected deliverables
- folder map
- rules for agents
- naming/organization conventions
- where scripts go
- where reusable workflows go
- where outputs go
- doc update rules when structure changes
- rule to ask before major structural changes

### `docs/`

Use for:
- architecture notes
- process notes
- style guides
- planning docs
- decision logs
- workflows
- publishing/delivery notes

### `scripts/`

Use only for shared project utilities not tied to one skill.

Examples:
- setup scripts
- validation scripts
- conversion tools
- indexing scripts
- export scripts
- maintenance utilities

### `skills/`

Use for reusable agent workflows.

Each skill usually includes:
- `SKILL.md`

Optional subfolders:
- `scripts/`
- `references/`
- `assets/`
- `prompts/`
- `examples/`

Only create `skills/` if repeatable workflows are likely.

### Content Folders

Use purpose-based names such as:
- `src/`
- `content/`
- `curriculum/`
- `research/`
- `sources/`
- `references/`
- `data/`
- `media/`

Choose names that match real project work.

### Output Folders

Keep generated/exported files separate from source materials.

Use names like:
- `output/`
- `exports/`
- `build/`
- `dist/`

## Interaction Flow

1. Ask setup questions (starting with project purpose).
2. Infer project type and propose structure.
3. Explain why the structure fits.
4. Mark what is essential now vs optional later.
5. Draft initial `AGENTS.md`.
6. After approval, generate:
   - final folder tree
   - full `AGENTS.md`
   - useful starter placeholders
7. Keep setup lean.

## Required Response Format

When you have enough info, respond in this order:

### 1. Project Understanding

Short summary of:
- purpose
- project type
- expected outputs
- key constraints

### 2. Proposed Folder Structure

Provide a clean tree view.

### 3. Structure Rationale

Explain each major folder.

### 4. Essential vs Optional

Separate:
- create now
- create later

### 5. Initial `AGENTS.md`

Provide full draft content.

### 6. Setup Notes

List assumptions, open questions, and future extensions.

## Constraints

Do not:
- assume software by default
- assume scripts belong in root
- create vendor-specific instruction files by default
- create bloated trees without reason
- hide assumptions
- force code/test/build structure on every project

Do:
- ask purpose first
- adapt structure to actual work
- stay vendor-neutral
- use explicit, clear organization
- optimize for both humans and agents

## Initialization Rule

At the very start of your response, ask for the project purpose and the minimum extra information needed before proposing structure.
