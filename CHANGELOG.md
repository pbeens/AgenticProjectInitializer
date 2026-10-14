# Changelog

All notable changes to this project will be documented in this file.

## [0.1.7] - 2026-10-14

### Changed
- Replaced the general-purpose `docs/` convention with `project-docs/` for architecture notes, workflows, decision logs, planning notes, and other project documentation.
- Reserved `docs/` for generated website output when a project publishes a site from that folder, regardless of whether it uses GitHub Pages, Quarto, Slidev, plain HTML, or another tool.
- Clarified that website source files must remain outside `docs/` and that builds may overwrite or delete the generated site contents.
- Added intake guidance asking whether the project will publish a website from `docs/`.
- Added README requirements for source-material, asset, reference, data, media, documentation, workflow, and output folders, including provenance, licensing, naming, and generation guidance where relevant.
- Added an exception for build-managed folders: their build process must generate or restore the folder README when the folder is deleted and recreated.
- Removed the duplicate Reference Only output-folder guidance so output rules have a single source of truth.

### Added
- Added explicit guidance distinguishing source materials and assets from generated outputs.
- Added `project-docs/` and generated website output examples to the README and master-prompt folder structures.

## [0.1.6] - 2026-08-15

### Added
- Added explicit prompt-traceability guidance requiring initialized projects to maintain a root-level `prompts.md` log for program-related user prompts while excluding unrelated administrative requests.
- Added prompt-log requirements to the README and the generated `AGENTS.md` guidance.

## [0.1.5] - 2026-07-16

### Changed
- Added explicit operating modes to `master-prompt.md` for initializing new projects and working within existing projects.
- Added file and action safety guidance covering inspection, preservation of existing work, authorization, reversible edits, and verification.
- Refined the required opening question so the prompt establishes the project's purpose before proposing files or folders.
- Generalized guidance about vendor-specific instruction files and added a reusable skill contract covering triggers, inputs, outputs, side effects, workflow, and verification.
- Clarified in `README.md` that this initializer repository intentionally does not contain an `AGENTS.md`; the target project creates it after requirements are gathered and the structure is approved.

## [0.1.4] - 2026-04-13

### Changed
- Added a `Behavioral Defaults` section to `master-prompt.md` covering explicit assumptions, simple viable structure, scoped edits, and verification.
- Updated `README.md` to summarize the new prompt guardrails.
- Refined `master-prompt.md` to make beginner task tracking explicit: keep stable instructions in `AGENTS.md` and track active work in a single root-level `tasks.md`.
- Added prompt guidance to keep `AGENTS.md` concise and durable (not a session log or changelog), with changing work moved to `tasks.md`.
- Updated prompt interaction flow and required response format to include a `tasks.md` recommendation and starter content when appropriate.
- Updated `README.md` wording and examples to align with the `AGENTS.md` + `tasks.md` split for beginner-friendly project setup.

## [0.1.3] - 2026-04-06

### Changed
- Updated the AGENTS.md attribution instruction in `master-prompt.md` so the backlink is formatted as an Obsidian-style `> [!NOTE]` callout.

## [0.1.2] - 2026-04-04

### Changed
- Updated onboarding flow to use staged questioning (purpose first, then small follow-up batches).
- Added lean-structure guardrails to avoid speculative folders and require "why now" justification for create-now folders.
- Made `output/`, `exports/`, `build/`, and `dist/` opt-in only when recurring generated artifacts are confirmed.
- Strengthened education terminology rules (`course-plan/` for teacher implementation; official standards kept under `sources/standards/` or `sources/official-curriculum/`).
- Generalized checklist behavior for all users (not beginner-only) and added proactive checklist prompts at milestone transitions.
- Tightened checklist quality rules: unresolved items only, concise scope, anti-duplication, and practical momentum.
- Switched checklist/task convention to co-located files near related work (for example `lesson-00-01-checklist.md`), not inline in core deliverables.
- Updated `.gitignore` guidance for local checklist/task tracking patterns (for example `*-checklist.md`, `*-tasks.md`).
- Added PDF extraction safety rules: split focused files, add verification notes, and require user confirmation/corrections before relying on extracted text.
- Added folder-name normalization defaults (lowercase kebab-case unless exact naming is explicitly requested).
- Added explicit document-linking requirements to prevent orphan docs and keep indexes/README navigation updated.

### Added
- Added optional PDF-to-Markdown utility recommendation in prompt guidance: [Pete's PDF to MD](https://github.com/pbeens/Petes-PDF-to-MD) (Mac and PC).
- Added README feedback section linking to GitHub Issues: [https://github.com/pbeens/AgenticProjectInitializer/issues](https://github.com/pbeens/AgenticProjectInitializer/issues).

## [0.1.1] - 2026-04-03

### Changed
- Updated checklist behavior so setup checklists are created as `setup-checklist.md` instead of chat-only output
- Updated `master-prompt.md` and `README.md` to reflect file-based checklist workflow
- Updated checklist guidance to include recommended destination paths, intake filenames, and starter template content

## [0.1.0] - 2026-04-03

### Added
- Initial `README.md`
- Initial `master-prompt.md`
- Initial `LICENSE`
- Initial `.gitattributes`
