# Specification standard

## 1. Purpose

This document defines the minimum expectations for specifications created or maintained in SpecBook-Agent. Specifications should be readable by people, useful to coding agents, traceable to requirements, and verifiable through tests or inspection.

The standard is intentionally format-light at this stage. Markdown with YAML front matter is the default. A formal JSON Schema or other machine validation can be introduced after the fields stabilize.

## 2. Specification package

A project specification package may contain:

```text
specifications/
  README.md
  requirements/
  architecture/
  components/
  interfaces/
  data/
  security/
  testing/
  decisions/
  templates/
```

Use only the sections needed for a particular project. A small change does not require a heavyweight document set.

## 3. Common document metadata

Where useful, include YAML front matter:

```yaml
---
id: SPEC-COMP-001
title: Example component specification
type: component
status: draft
version: 0.1.0
owner: TBD
created: YYYY-MM-DD
updated: YYYY-MM-DD
related_requirements:
  - REQ-001
related_decisions:
  - ADR-001
---
```

Allowed statuses should be used consistently:
- `draft`
- `in_review`
- `approved`
- `implemented`
- `verified`
- `superseded`
- `rejected`

Do not mark a specification implemented or verified without corresponding evidence.

## 4. Requirement format

Each requirement should have:
- Stable identifier, such as `REQ-F-001` or `REQ-NF-001`.
- Name and rationale.
- Statement using clear, testable language.
- Priority.
- Source or stakeholder.
- Constraints and dependencies.
- Acceptance criteria.
- Verification method.
- Status.

Use normative terms carefully:
- **MUST** indicates a mandatory requirement.
- **SHOULD** indicates a strong recommendation with justified exceptions.
- **MAY** indicates an optional capability.

Avoid vague words such as fast, scalable, secure, user-friendly, or robust unless accompanied by measurable or inspectable criteria.

## 5. Architecture specification

An architecture specification should address, as applicable:
- Context, goals, and non-goals.
- System boundaries and external actors.
- Quality attributes and constraints.
- Components, responsibilities, and interactions.
- Data flows and trust boundaries.
- Technology choices and rationale.
- Alternatives considered and trade-offs.
- Failure modes and recovery.
- Security, privacy, and operational concerns.
- Deployment topology and environments.
- Risks, assumptions, and open decisions.

## 6. Component specification

Each component specification should identify:
- Component ID and responsibility.
- Scope and explicit non-responsibilities.
- Inputs, outputs, and interfaces.
- State and data ownership.
- Dependencies and upstream/downstream relationships.
- Business rules and invariants.
- Error handling and failure behaviour.
- Security and authorization expectations.
- Observability requirements.
- Performance or capacity constraints where known.
- Acceptance criteria and tests.

## 7. Interface and data specifications

API and event contracts should define:
- Operation or event name and stable identifier.
- Request, response, and error structures.
- Types, required fields, validation, and constraints.
- Authentication and authorization.
- Idempotency, retries, ordering, and versioning where relevant.
- Compatibility expectations.
- Examples that are valid against the contract.

Data specifications should define:
- Entity and field meaning.
- Types, nullability, constraints, and defaults.
- Keys and relationships.
- Ownership and lifecycle.
- Retention and privacy classification where applicable.
- Migration and compatibility strategy.
- Data quality and validation rules.

## 8. Security specification

Identify:
- Assets and sensitive data.
- Actors and trust boundaries.
- Threats and abuse cases.
- Authentication and authorization model.
- Secrets and key handling.
- Input validation and output handling.
- Audit and monitoring expectations.
- Data residency and external service flows.
- Security testing and release criteria.

Do not treat a checklist as a substitute for threat modelling where risk warrants deeper analysis.

## 9. Test and acceptance specification

Each acceptance criterion should be observable and linked to one or more verification methods.

Specify relevant:
- Unit tests.
- Integration tests.
- Contract tests.
- End-to-end tests.
- Performance and load tests.
- Security tests.
- Migration and recovery tests.
- Manual review or operational acceptance.

Record test commands, environment assumptions, expected results, and actual evidence when executed.

## 10. Architecture decision records

Use a short ADR structure:

1. ID, title, date, and status.
2. Context and problem.
3. Decision drivers and constraints.
4. Decision.
5. Alternatives considered.
6. Consequences, trade-offs, and risks.
7. Related requirements and specifications.
8. Supersedes / superseded by, if applicable.

An approved decision may be changed, but the change must be recorded and its impact assessed.

## 11. Traceability

Maintain links in both directions where practical:

```text
Requirement
  -> Architecture decision
  -> Component / interface / data specification
  -> Implementation path or symbol
  -> Test and verification evidence
```

Traceability is not satisfied by a generic statement that a feature is covered. Links should identify actual artifacts and stable identifiers.

## 12. Change control

When a requirement or specification changes:
1. Explain why it changed.
2. Identify affected artifacts and components.
3. Assess compatibility and migration impact.
4. Update acceptance criteria and tests.
5. Obtain required approval.
6. Preserve the change in version history.

Agents must not silently change an approved specification to match generated code. If implementation reveals a flaw in the specification, raise the discrepancy and propose a reviewed change.
