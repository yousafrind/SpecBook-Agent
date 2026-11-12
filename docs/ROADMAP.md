# Project roadmap

## 1. Roadmap principles

This roadmap prioritizes validating the engineering method before building a large automation platform.

- Deliver useful, reviewable artifacts incrementally.
- Demonstrate the workflow on a bounded but realistic software system.
- Keep all foundational knowledge portable and version-controlled.
- Separate proposed capabilities from demonstrated implementation.
- Add automation only when the process and verification criteria are clear.

## 2. Current status

The repository currently contains the initial README and foundational project documents. The project is at the documentation and methodology-definition stage.

No agent orchestration, ingestion pipeline, retrieval service, or codebase intelligence engine should be considered implemented unless corresponding code and tests are added.

## 3. Milestones

### M0 — Project foundation

- [x] Publish initial README.
- [x] Establish repository-wide engineering instructions.
- [x] Establish Claude Code entry guidance.
- [x] Define the concept and dual-knowledge model.
- [x] Define the conceptual architecture.
- [x] Define the knowledge and provenance model.
- [x] Define the specification standard.
- [x] Define the engineering workflow.
- [x] Establish an initial roadmap.
- [ ] Review foundation documents through a real project walkthrough.

### M1 — Curated engineering knowledge

- [ ] Define and validate the source registry format.
- [ ] Add source curation and license-review guidance.
- [ ] Select a small set of authoritative engineering sources.
- [ ] Create reviewed patterns and implementation-analysis examples.
- [ ] Define a repeatable NotebookLM source preparation process.
- [ ] Demonstrate source-grounded design research.

### M2 — Specification workflow

- [ ] Select a representative application and define its requirements.
- [ ] Add specification templates and stable identifier conventions.
- [ ] Create an example requirements package.
- [ ] Generate architecture and component specifications using the knowledge base.
- [ ] Review and revise the specifications.
- [ ] Demonstrate requirement-to-specification traceability.

### M3 — Reference implementation

- [ ] Choose a bounded application with meaningful components and integrations.
- [ ] Implement incrementally using Claude Code or a replaceable coding agent.
- [ ] Add automated tests and reproducible quality checks.
- [ ] Record architecture decisions and implementation deviations.
- [ ] Publish the reference implementation and engineering walkthrough.

### M4 — Implementation knowledge

- [ ] Define the implementation dossier format.
- [ ] Extract repository structure and module documentation.
- [ ] Capture APIs, schemas, dependencies, and test evidence.
- [ ] Tie generated knowledge to a commit SHA.
- [ ] Prepare a second NotebookLM notebook from selected implementation artifacts.
- [ ] Demonstrate repository-grounded feature and debugging questions.

### M5 — Repeatability and evaluation

- [ ] Define evaluation tasks and a baseline workflow.
- [ ] Compare specification completeness and change-impact accuracy.
- [ ] Evaluate defects, regressions, and documentation drift.
- [ ] Record time, effort, and limitations transparently.
- [ ] Publish findings, including negative results.

### M6 — Selective automation

- [ ] Automate source registry validation and ingestion preparation.
- [ ] Add repository extraction and refresh scripts.
- [ ] Add specification and traceability validation.
- [ ] Evaluate retrieval and indexing approaches.
- [ ] Define agent adapter contracts.
- [ ] Introduce bounded orchestration with human approval gates.

## 4. Demonstration criteria

The initial end-to-end demonstration should show that a reader can:

1. Identify the sources used for an engineering decision.
2. Follow how requirements become specifications.
3. Review the specifications before code is generated.
4. Inspect the implementation and its tests.
5. Query implementation documentation to understand a feature.
6. Validate the answer against the actual repository.
7. Make a change and refresh affected implementation knowledge.

## 5. Risks and open questions

- How much knowledge curation is worthwhile before retrieval quality plateaus?
- Which source metadata and license details are essential for the first experiment?
- What specification format provides useful structure without creating excessive ceremony?
- How should implementation knowledge combine static code analysis and runtime evidence?
- How can freshness be measured and stale notebook sources detected?
- Which tasks benefit from agents, and which are more reliable as deterministic scripts?
- How should the method be evaluated fairly against conventional AI-assisted development?

These questions should be resolved through experiments and documented decisions, not assumptions.
