# Knowledge model and source provenance

## 1. Purpose

This document defines how SpecBook-Agent should represent, curate, and maintain engineering knowledge. It covers both reusable external knowledge and project-specific implementation knowledge.

The initial format should be portable and simple: Markdown for human-readable content, YAML front matter for metadata, and JSON or YAML for structured records when needed.

## 2. Knowledge classes

### 2.1 Engineering knowledge

Reusable knowledge about engineering methods and technologies:
- Architecture patterns and design principles.
- Language, framework, database, and infrastructure documentation.
- Open-source project patterns and implementation examples.
- Security, testing, reliability, and operations practices.
- Reusable skills, checklists, and playbooks.

### 2.2 Project knowledge

Knowledge specific to a project:
- Requirements and constraints.
- Approved specifications and architecture decisions.
- Domain vocabulary and business rules.
- System components, interfaces, and data models.
- Project conventions and operational assumptions.

### 2.3 Implementation evidence

Facts derived from the implementation:
- Source files and symbols.
- Dependencies and call relationships.
- Database schemas and migrations.
- API definitions and event contracts.
- Configuration and deployment artifacts.
- Test results, build results, and runtime observations.

### 2.4 Derived knowledge

Human- or machine-generated representations based on other artifacts:
- Summaries and technical dossiers.
- Architecture and dependency maps.
- Notebook source collections.
- Retrieval indexes and embeddings.
- Change-impact reports.

Derived knowledge must identify its source and freshness. It is rebuildable and subordinate to its evidence.

## 3. Source record

Every curated external source should have a record with as many of the following fields as are available:

| Field | Meaning |
|---|---|
| `source_id` | Stable unique identifier |
| `title` | Human-readable title |
| `publisher` | Organization, project, author, or maintainer |
| `source_type` | Official docs, repository, standard, article, book, example, etc. |
| `canonical_url` | Original source location |
| `version` | Product, framework, release, or document version |
| `published_at` | Publication date, if known |
| `retrieved_at` | Date the source was collected or checked |
| `license` | License or terms, if known |
| `reuse_notes` | Attribution, redistribution, or excerpt restrictions |
| `domains` | Engineering topics covered |
| `applicability` | Contexts in which the source is relevant |
| `limitations` | Known gaps, assumptions, or caveats |
| `review_status` | Unreviewed, reviewed, stale, rejected |
| `content_hash` | Optional digest for detecting content changes |

Unknown values should be recorded as unknown or omitted, not guessed.

## 4. Knowledge item metadata

A knowledge item may be a pattern, principle, example, procedure, or observation. Suggested metadata:

- Stable item identifier.
- Title and concise summary.
- Knowledge class and domain.
- Source identifiers.
- Applicable technologies and versions.
- Preconditions and constraints.
- Recommended use and anti-patterns.
- Evidence strength and review status.
- Last reviewed date.
- Related items and known conflicts.

A pattern should explain when it applies and when it does not. Avoid presenting context-dependent trade-offs as universal rules.

## 5. Provenance and confidence

Separate these categories explicitly:

- **Source fact:** directly supported by an identified source.
- **Observed implementation fact:** verified from a particular repository revision or execution.
- **Engineering interpretation:** reasoned conclusion based on evidence.
- **Assumption:** plausible but not yet verified.
- **Recommendation:** proposed action with rationale and trade-offs.
- **Unknown:** information not established.

Confidence labels do not replace evidence. A high-confidence statement still needs a source or reproducible observation when it materially affects an engineering decision.

## 6. Freshness and versioning

- Prefer version-specific official documentation for version-sensitive decisions.
- Record the version used when evaluating a framework or library.
- Recheck critical sources before relying on them for implementation.
- Mark sources stale when a newer version may materially change guidance.
- Tie implementation-derived knowledge to a commit SHA or other immutable revision.
- Regenerate indexes and summaries when their source revision changes.
- Preserve historical decisions; record superseding decisions rather than erasing history.

## 7. Knowledge curation workflow

1. Discover a candidate source.
2. Check relevance, authority, date, version, and license.
3. Register its metadata.
4. Extract only useful material within applicable terms.
5. Create or update knowledge items with source links.
6. Review technical interpretation and applicability.
7. Make the material available to the chosen research/retrieval interface.
8. Periodically review freshness and conflicts.

A source being public does not mean its full contents can be republished or redistributed. Follow license and copyright terms.

## 8. NotebookLM as an interface

For the initial experiment:
- Create focused notebooks rather than one unlimited notebook.
- Include source metadata and original links.
- Prefer official and version-appropriate sources.
- Keep the curated source register in Git.
- Record notebook purpose, source selection, and last refresh date.
- Treat notebook answers as research leads that must be checked against original sources for consequential decisions.

NotebookLM is not the canonical store, source registry, or live code index.

## 9. Implementation knowledge records

Implementation-derived records should include:
- Project and repository identifier.
- Branch and commit SHA.
- Extraction timestamp and tool version.
- Paths or symbols examined.
- Evidence links or file references.
- Generated summary and known limitations.
- Freshness status.

A generated architecture map must not imply runtime behaviour unless supported by runtime evidence.

## 10. Initial directory convention

The knowledge directory may evolve toward:

```text
knowledge/
  AGENTS.md
  README.md
  sources/
    sources.yaml
  architecture/
  programming/
  frameworks/
  databases/
  infrastructure/
  security/
  testing/
  open-source/
  patterns/
  skills/
  evaluations/
```

Do not create empty categories merely to make the tree look complete. Add categories when there is useful, curated content to maintain.
