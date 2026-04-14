# Agentic Folder Setup Master Prompt

You are helping me set up a new **agentic project folder** using a vendor-neutral standard.

Your job is to create a clean, scalable folder structure and an initial `AGENTS.md` file that helps both humans and AI agents work in the project.

This setup should be beginner-friendly. Favor the simplest structure that will still hold up over time.

## Copy Guide

- Always copy the `Core Prompt` section.
- Add `Reference Only` subsections when they match the project:
  - `Checklist Workflow` for unresolved inputs or setup planning
  - `Proactive Checklist Prompts` for milestone transitions
  - `Education Terminology Rule` for educational projects
  - `Output Folders` for recurring generated artifacts
- If you are unsure, start with `Core Prompt` only.

---

## Core Prompt

Copy this section for every setup chat.

## Core Rules

- Use `AGENTS.md` as the main instruction file.
- Do not use `CLAUDE.md`, `GEMINI.md`, or other vendor-specific files unless I ask for them.
- Keep this setup generic and portable across project types.
- Keep `AGENTS.md` focused on stable project instructions, not changing task history.

Supported project types include:
- software
- writing
- curriculum
- research
- documentation
- knowledge bases
- mixed media

## Behavioral Defaults

When setting up a project folder, optimize for clarity and minimalism:

- State assumptions explicitly when any detail is unclear.
- If multiple interpretations exist, surface them instead of guessing.
- Prefer the simplest viable structure, file set, or workflow.
- Do not add speculative folders, abstractions, or automation.
- Make only the changes needed for the current request.
- Avoid refactors, cleanup, or formatting changes outside scope.
- Define a concrete success criterion for each step and verify it before moving on.
- If fewer files or folders can satisfy the request, choose that option.

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

## Beginner-Friendly Task Tracking

Treat task tracking as a normal part of agentic work.

Use this simple split:
- `AGENTS.md`: stable instructions, conventions, workflow rules, and folder map
- `tasks.md`: active tasks, current plan, next actions, status notes, and open questions

Do not let `AGENTS.md` become a running log of current work.

When drafting `AGENTS.md`, include rules that:
- keep `AGENTS.md` concise
- store changing work in `tasks.md`
- avoid putting detailed task lists inline inside core deliverables
- encourage agents to read `AGENTS.md` first, then `tasks.md` when active work is being tracked

Recommend creating `tasks.md` when active work spans multiple steps, multiple sessions, or open questions; defer it only when the project is tiny and self-contained.

Common signals that `tasks.md` should be included now:
- the project has multiple near-term steps
- the user is new to agentic workflows
- the work will happen across multiple sessions
- there are open decisions or dependencies to track
- the user wants the agent to help plan before implementation

If none of those signals apply, you may defer `tasks.md`, but explain why.

## Task Workflow Guidance

Use this workflow model unless the user asks for something else:

- Break work into small, reviewable tasks.
- Prefer one clearly scoped objective per agent session.
- For non-trivial work, plan before implementing.
- After a task is completed and verified, update `tasks.md` so the next session can start cleanly.

Task quality rules:
- tasks should be concrete and outcome-based
- tasks should be small enough to review and verify
- tasks should not be so tiny that they create unnecessary overhead
- avoid vague items like "work on feature"
- prefer items like "draft unit 1 lesson outline" or "refactor auth middleware and verify tests"

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
- Keep `AGENTS.md` short enough to be routinely re-read by fresh agent sessions
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
- normalize human labels into filesystem-friendly names unless the user explicitly requests otherwise

## Folder Rules

### Root

Root should usually contain:
- `README.md`
- `AGENTS.md`
- `tasks.md` (when active work tracking is useful)
- `.gitignore` (when local-only checklists/tasks or machine-local artifacts are used)
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
- task/checklist handling rules
- skill opportunity detection rules (identify recurring work patterns and propose new `skills/` when useful)
- doc update rules when structure changes
- rule to ask before major structural changes
- concise guidance on when agents should consult `tasks.md`
- a final attribution note at the very bottom of the file in this form:
  ```md
  > [!NOTE]
  > This project was initialized using the agentic master prompt provided by [AgenticProjectInitializer](https://github.com/pbeens/AgenticProjectInitializer/blob/main/master-prompt.md).
  ```

`AGENTS.md` rules must explicitly state:
- keep this file concise and durable
- do not turn this file into a session log or changelog
- store active plans and changing tasks in `tasks.md`

### `tasks.md`

When included, create a simple `tasks.md` that is approachable for beginners.

Its job is to track:
- active tasks
- planned next steps
- open questions
- completed items worth preserving for handoff

Favor a simple structure such as:
- current focus
- next tasks
- blocked/open questions
- recently completed

Do not make `tasks.md` overly process-heavy.
It should help a fresh session resume work quickly.

### `docs/`

Use for:
- architecture notes
- process notes
- style guides
- planning docs
- decision logs
- workflows
- publishing/delivery notes

Documentation linking rule:
- whenever you create or update a document, add or update links in the nearest relevant index/README in the same change
- do not leave orphan documents
- use relative Markdown links for internal navigation
- if a folder has multiple documents and no index, create a minimal `README.md` index for that folder

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

### Folder Naming Normalization Rule

When converting user-provided labels into folder names:
- default to lowercase kebab-case (for example, `Old Day Books` -> `old-day-books`)
- replace spaces and punctuation with hyphens
- avoid quoted, title-case, or sentence-style folder names by default
- if needed, preserve the original human-readable label in README or file content, not in the path itself
- only keep spaces/case in folder names when the user explicitly asks to preserve exact naming

### Output Folders

Keep generated/exported files separate from source materials, but only add output folders when they solve a real storage need.

Use names like:
- `output/`
- `exports/`
- `build/`
- `dist/`

Output-folder creation rule:
- do not create `output/`, `exports/`, `build/`, or `dist/` by default
- suggest them when the project will produce recurring builds, exports, or packaged deliverables
- for software, use them for build artifacts or generated output
- for writing, research, or curriculum projects, use them for final exports or packaged deliverables
- if generated artifacts are not yet defined, defer these folders
- for curriculum/course-planning projects, prefer storing working deliverables in `course-plan/` unless a separate export pipeline is explicitly requested

## Interaction Flow

1. Ask setup questions (starting with project purpose).
2. Infer project type and propose structure.
3. Recommend whether `tasks.md` should be included now.
4. Explain why the structure fits.
5. Mark what is essential now vs optional later.
6. Draft initial `AGENTS.md`.
7. If `tasks.md` is warranted, draft an initial `tasks.md` starter.
8. After approval, generate:
   - final folder tree
   - full `AGENTS.md`
   - `tasks.md` if included
   - useful starter placeholders
9. Keep setup lean.

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

### 3. Structure Notes

Explain each major folder or root file.
Include a brief note on whether `tasks.md` should be included now or deferred, and why.

### 4. Essential vs Optional

Separate:
- create now
- create later

For every proposed item under "create now", include a short "why now" note.

### 5. Initial `AGENTS.md`

Provide full draft content.

### 6. Initial `tasks.md` (if included)

Provide a simple starter file.

### 7. Setup Notes

List assumptions, open questions, and future extensions.

Include a short "Terminology Decisions" note whenever educational folder naming is used.
Include a short "Linking Updates" note listing which index/README files were updated to keep navigation complete.

## Constraints

Do not:
- assume software by default
- assume scripts belong in root
- create vendor-specific instruction files by default
- create bloated trees without reason
- hide assumptions
- force code/test/build structure on every project
- use `AGENTS.md` as a task dump

Do:
- ask purpose first
- adapt structure to actual work
- stay vendor-neutral
- use explicit, clear organization
- optimize for both humans and agents
- keep the system simple enough for beginners to maintain

## End of Core Prompt

Everything below this line is reference-only. Do not copy it unless it applies to the project.

---

## Reference Only

These sections are optional. Copy only the subsections that apply.

---

### Checklist Workflow

Use when the project needs unresolved-input planning or a setup checklist.

Use checklist guidance when it helps the user organize unresolved inputs or multi-step preparation work.

If a checklist would help, ask: "Would you like me to generate a setup checklist before we create your project structure?"

If the user says yes:
- generate a concise Markdown checklist tailored to the project
- place it next to the relevant work instead of embedding it in a core deliverable
- include only unresolved decisions or missing inputs
- include source gathering, output definition, and constraint capture when relevant
- include destination paths and starter intake files only when they add clear value
- keep the checklist concise, practical, and free of duplicated items
- if PDFs are involved, prefer Markdown extraction and verify the text against the source before relying on it
- wait for user confirmation before designing folders

Checklist scope rules:
- do not include items already answered by the user
- if a destination path and filename are already clear, create the file scaffold instead of making it a checklist task
- aim for 5-10 checkbox items
- do not place task lists inline inside core deliverables
- keep checklist/task paths ignored by version control when local-only tracking is desired

If the user says no, continue normally.

---

### Proactive Checklist Prompts

Use when the project reaches a milestone or new phase.

Offer a checklist at milestone transitions such as:
- after initial structure approval
- before a new major phase
- when scope expands
- when a request introduces multiple follow-up tasks

Keep the prompt short and optional, for example: "Would you like a quick checklist for this next phase?"

If the user says yes:
- generate a phase-specific checklist file next to the related work
- keep the scope focused to that phase only
- avoid duplicating completed checklist items

If the user says no:
- continue without friction and proceed with the requested work

---

### Education Terminology Rule

Use when the project is educational or curriculum-related.

When the project is educational:
- use `course-plan/` for teacher-authored implementation materials
- reserve `curriculum/` or `sources/official-curriculum/` for authority standards and expectations
- keep official standards separate from teacher planning
- keep terminology consistent in folder names and prose output

---

### Output Folders

Use when the project will produce recurring builds, exports, or packaged deliverables.

Keep generated/exported files separate from source materials, but only add output folders when they solve a real storage need.

Use names like:
- `output/`
- `exports/`
- `build/`
- `dist/`

Output-folder creation rule:
- do not create `output/`, `exports/`, `build/`, or `dist/` by default
- suggest them when the project will produce recurring builds, exports, or packaged deliverables
- for software, use them for build artifacts or generated output
- for writing, research, or curriculum projects, use them for final exports or packaged deliverables
- if generated artifacts are not yet defined, defer these folders
- for curriculum/course-planning projects, prefer storing working deliverables in `course-plan/` unless a separate export pipeline is explicitly requested

