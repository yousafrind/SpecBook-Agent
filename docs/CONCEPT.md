# Concept: Knowledge-grounded, specification-driven engineering

## 1. Purpose

SpecBook-Agent explores a repeatable engineering method for using AI coding agents to design, build, understand, and evolve large software systems.

The method addresses a gap between code generation and systems engineering. A coding agent can produce code from a prompt, but a long-lived system also requires coherent requirements, architecture, interfaces, data models, security controls, tests, operational practices, and change management.

The central proposition is to ground AI-assisted engineering in two connected knowledge environments:

1. **Engineering Knowledge Base (EKB):** curated external and reusable knowledge about how systems can be engineered.
2. **Implementation Knowledge Base (IKB):** evidence-derived knowledge about what a particular system actually contains and how it behaves.

Specifications connect the two: engineering knowledge informs design; approved specifications guide implementation; implementation evidence informs future engineering work.

## 2. Problem statement

Large systems accumulate complexity across components, teams, technologies, and time. AI-assisted development can amplify this complexity when an agent:

- Works from incomplete or ambiguous requirements.
- Selects patterns without understanding constraints.
- Generates inconsistent interfaces or duplicated responsibilities.
- Makes local changes without understanding system-wide dependencies.
- Produces documentation that drifts from the code.
- Treats plausible explanations as verified facts.

Simply adding more documents to a prompt does not solve these problems. The engineering process needs curation, provenance, structured specifications, verification, and continuous reconciliation.

## 3. Proposed approach

The method follows a lifecycle:

1. Curate relevant engineering knowledge and preserve provenance.
2. Capture business requirements, user needs, and system constraints.
3. Retrieve relevant knowledge for the problem at hand.
4. Generate structured requirements, architecture, component, interface, data, security, and test specifications.
5. Review and approve material decisions.
6. Implement incrementally against the approved specifications.
7. Verify the implementation through tests, analysis, and review.
8. Derive implementation knowledge from the repository and runtime evidence.
9. Use that knowledge to support feature development, debugging, impact analysis, and refactoring.
10. Feed validated lessons back into reusable engineering knowledge.

This is one methodology that can be performed with human-managed tool handoffs initially and progressively automated later. These are maturity stages of the same workflow, not separate products or incompatible operating modes.

## 4. The two knowledge environments

### 4.1 Engineering Knowledge Base

The EKB may contain:

- Official language, framework, database, and infrastructure documentation.
- Architecture and design patterns.
- Open-source project documentation and selected code examples.
- Testing, security, reliability, and operational practices.
- Reusable engineering skills and playbooks.
- Evaluations, known limitations, version information, and source licenses.

The EKB is curated, not an indiscriminate dump of the internet. Each knowledge item should retain enough metadata to identify its source, version, relevance, and reuse conditions.

### 4.2 Implementation Knowledge Base

The IKB is project-specific and derived from the actual implementation. It may contain:

- Repository structure and module responsibilities.
- Source-code symbol and dependency indexes.
- Architecture and data-flow maps.
- Database schemas, migrations, and data contracts.
- API and event contracts.
- Configuration and deployment descriptions.
- Test suites, test results, and quality evidence.
- Architecture decision records.
- Known defects, limitations, and technical debt.

The IKB is a navigational and analytical representation, not an alternative source of truth. It must be refreshable from version-controlled and executable evidence.

## 5. Role of specifications

Specifications are the contract between engineering intent and implementation.

A useful specification package should include, as applicable:

- Problem statement, goals, non-goals, and stakeholders.
- Functional and non-functional requirements.
- Constraints, assumptions, and dependencies.
- System context and architecture.
- Component responsibilities and boundaries.
- Data models and lifecycle rules.
- API, event, and integration contracts.
- Security and privacy requirements.
- Failure handling and operational expectations.
- Test strategy and measurable acceptance criteria.
- Traceability to requirements and architecture decisions.

Specifications are versioned artifacts. They change when requirements or validated engineering understanding changes. An agent must not silently reinterpret an approved decision.

## 6. Tooling philosophy

The methodology is tool-agnostic.

The initial experiment uses:
- **NotebookLM** as a convenient research and synthesis interface over selected source material.
- **Claude** for reasoning, requirements analysis, and specification development.
- **Claude Code** for repository-level implementation and engineering tasks.
- **Git** as the versioned source of truth.
- **Automated tools** for tests, static analysis, security checks, dependency inspection, and documentation extraction.

Other models, coding agents, notebooks, retrieval systems, and orchestration tools may be substituted. Core knowledge and specifications should remain portable.

Notebook interfaces are not expected to replace code search, AST or symbol indexing, dependency graphs, executable tests, or runtime observability.

## 7. Human accountability

AI agents may draft, analyse, implement, and recommend. Humans remain accountable for:

- Business goals and priorities.
- Acceptance of requirements and constraints.
- Material architecture and security decisions.
- Source and license approval.
- Risk acceptance.
- Code review and release authorization.

Automation should be introduced where the workflow is understood and its outputs can be verified.

## 8. Hypothesis and evaluation

The project explores the hypothesis that a curated engineering knowledge base, explicit specifications, and a continuously reconciled implementation knowledge base can improve the consistency and maintainability of AI-assisted development.

This is a hypothesis, not an established result.

Potential evaluation measures include:

- Requirements and specification completeness.
- Architecture and interface consistency.
- Defect and regression rates.
- Accuracy of change-impact analysis.
- Test effectiveness and reproducibility.
- Documentation-to-code alignment.
- Time and effort for feature changes.
- Reuse of validated engineering patterns.

Comparisons should use a defined task, comparable models and constraints where possible, and transparent evaluation criteria.

## 9. Scope boundaries

SpecBook-Agent is not:
- A promise of fully autonomous software engineering.
- A replacement for engineering judgment, code review, or testing.
- A claim that a notebook can continuously understand an entire live repository.
- A generic prompt collection without traceability or verification.
- A commitment to Claude or NotebookLM as permanent dependencies.

## 10. Long-term direction

The long-term ambition is an engineering environment in which validated knowledge accumulates across projects. New work can reuse proven patterns and lessons, while each implementation contributes evidence that improves future decisions.

The intended progression is from knowledge-grounded manual workflows to selectively automated, verifiable engineering workflows—not automation for its own sake.
