# Decisions

## 2026-11-10 — Keep consequential decisions in a separate dated log

**Decision:** Initialized projects should maintain consequential project decisions in a separate root-level `decisions.md` file.

**Context:** The initializer prompt and `AGENTS.md` should remain concise, stable, and operational. Decision rationale evolves over time and needs to be discoverable without turning either instruction file into a historical record.

**Recommendation credit:** This idea was prompted by feedback from [Will Lee](https://x.com/WillLeeAI).

**Alternatives considered:** Put decisions in `prompts.md`, which would make the prompt-history file unnecessarily long and mix prompt traceability with decision rationale; put them directly in the initializer prompt or `AGENTS.md`; use `tasks.md`; maintain no persistent rationale record.

**Revisit when:** The project’s instruction, documentation, or handoff model changes substantially.
