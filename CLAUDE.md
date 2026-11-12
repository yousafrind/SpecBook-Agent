# Claude Code project entry point

This file provides Claude Code-specific entry guidance. The vendor-neutral engineering policy lives in the repository's `AGENTS.md` files.

## Required first steps

1. Read the root `AGENTS.md`.
2. Read every applicable nested `AGENTS.md` along the path of files you intend to inspect or change.
3. Inspect the current repository state before proposing or editing files.
4. Treat the checked-in repository—not a NotebookLM answer, prior conversation, or generated summary—as the source of truth.

## Project context

SpecBook-Agent is an open-source experiment in knowledge-grounded, specification-driven engineering. Its intended lifecycle connects:

- Curated engineering knowledge and source provenance.
- Requirements and constraints.
- Reviewable specifications and architecture decisions.
- Coding-agent implementation.
- Automated and human verification.
- Implementation knowledge derived from the actual repository.
- Feedback into future engineering work.

Claude and NotebookLM are initial tools used to explore the methodology. They are not mandatory architectural dependencies of the eventual system.

## Working expectations

- Ground technical claims in repository evidence or identified external sources.
- Do not invent repository capabilities, test results, citations, or implementation status.
- Distinguish proposed design from implemented behaviour.
- Prefer portable, version-controlled artifacts.
- Ask for clarification before making material product, security, licensing, or architectural decisions that cannot be safely inferred.
- Keep changes incremental and reviewable.
- Run relevant checks when available and report their actual results.
- Do not create or modify secrets or expose sensitive information.

## Instruction precedence

Follow the root `AGENTS.md` and all applicable nested `AGENTS.md` instructions. This file supplements those instructions with Claude Code entry guidance; it does not replace them.
