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

Use staged questioning. Do not ask for everything at once.

Question cadence:
- Start with exactly one question: project purpose.
- After the user answers, ask only 2-3 follow-up questions at a time.
- Prefer short, plain-language questions over long questionnaires.
- After each batch, briefly summarize what is known and ask the next small batch only if needed.
- Stop asking questions once you have enough information to propose a structure.

You must still collect these inputs before finalizing structure (across multiple turns if needed):
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
- for each checklist item, include a recommended destination path (where that information should be stored)
- include a "Recommended Intake Files" section with concrete filenames and short purpose notes
- provide starter template content for each recommended intake file in fenced Markdown code blocks
- recommend clean text formats (especially Markdown)
- if relevant, suggest converting PDFs to Markdown first
- when suggesting PDF-to-Markdown conversion, include this optional free utility: `https://github.com/pbeens/Petes-PDF-to-MD` (downloadable Mac and PC versions)
- wait for user confirmation before designing folders

Checklist scope rules:
- checklist items must be only unresolved decisions or missing inputs
- do not include items already answered by the user
- if a destination path and filename are already clear, create the file scaffold instead of making it a checklist task
- keep the actionable checklist concise (target 5-10 checkbox items)
- avoid turning obvious setup work into checklist overhead

The generated checklist file must include these required sections (exact headings):
- `## Destination Paths`
- `## Recommended Intake Files`
- `## Starter Templates`

When scaffolds are created during checklist mode, also include:
- `## Auto-Created Scaffolds`

Checklist quality rules:
- specific to the project
- detailed enough, but not bloated
- no domain assumptions unless the user gave that domain
- avoid leaving required inputs as chat-only notes
- avoid duplicated checklist content across sections; if similar items appear in multiple sections, each section must add distinct value
- prioritize practical momentum: create obvious baseline files/folders now, and checklist only what still needs decisions/content

If the user says no, continue normally.

## Main Goal

Create a structure that:
- keeps root clean
- separates instructions, utilities, workflows, source materials, and generated outputs
- supports both human and agent work
- avoids vendor lock-in
- is understandable without chat history
- can grow over time

Apply a minimum viable structure mindset:
- create only folders that are needed right now
- do not pre-create speculative folders "just in case"
- prefer adding folders later when a real artifact requires them

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
- do not create top-level folders without a concrete near-term artifact to place there

## Folder Rules

### Root

Root should usually contain:
- `README.md`
- `AGENTS.md`
- project manifests (if needed)
- top-level project folders

Do not put random helper scripts in root unless they are true entrypoints.

Before proposing any top-level folder, provide a one-line justification tied to an expected artifact.
If no concrete artifact is known yet, defer that folder.

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
- `course-plan/`
- `research/`
- `sources/`
- `references/`
- `data/`
- `media/`

Choose names that match real project work.

### Education Terminology Rule

When the project is educational, apply these naming rules:
- use `curriculum` only for official authority standards/expectations documents
- do not use `curriculum/` for teacher-authored planning materials unless explicitly requested
- use `course-plan/` for the teacher's implementation (units, lessons, assessments, sequencing)
- store official standards under a clear path such as `sources/standards/` or `sources/official-curriculum/`
- if both official standards and teacher planning exist, keep them in separate folders with explicit names
- keep terminology consistent in both folder names and prose output; do not use "course of study" unless the user explicitly requests that term

### Output Folders

Keep generated/exported files separate from source materials.

Use names like:
- `output/`
- `exports/`
- `build/`
- `dist/`

Output-folder creation rule:
- do not create `output/`, `exports/`, `build/`, or `dist/` by default
- create them only when the user has explicitly confirmed recurring generated artifacts that need separate storage
- if generated artifacts are not yet defined, defer these folders
- for curriculum/course-planning projects, prefer storing working deliverables in `course-plan/` unless a separate export pipeline is explicitly requested

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

For every proposed folder under "create now", include a short "why now" note.

### 5. Initial `AGENTS.md`

Provide full draft content.

### 6. Setup Notes

List assumptions, open questions, and future extensions.

Include a short "Terminology Decisions" note whenever educational folder naming is used.

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
