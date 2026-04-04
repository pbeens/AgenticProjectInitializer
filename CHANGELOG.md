# Changelog

All notable changes to this project will be documented in this file.

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
