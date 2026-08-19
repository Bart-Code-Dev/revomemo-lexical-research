# RevoMemo Lexical Research

RevoMemo Lexical Research documents the development of a versioned, sense-first multilingual lexical grounding approach intended to improve the reliability of AI-generated language-learning materials.

This is a newly curated public research repository. The source engineering work predates this repository, while private production repositories remain private. Proprietary lexical datasets and learner data are excluded. The confirmatory benchmark has **not** yet been run; it is planned to be preregistered before execution.

## Research motivation

Language-learning generation can fail even when source and target forms appear related. A useful learning item needs a specific intended meaning, a natural target realization, grammatical conditions, and an answer that can be evaluated without ambiguity.

## Research question

Does typed, sense-first lexical grounding reduce critical educational errors in generated multilingual language-learning materials compared with flat mappings and less structured context?

## Lexical architecture

The approach separates meaning from language-specific realization and makes relationships explicit.

\`\`\`mermaid
flowchart TD
    C[Concept] --> A[English Anchor]
    A --> L[Language-specific Lexeme]
    L --> F[Forms / Syntax / Constraints]
    F --> R[Directed Translation Relation]
    R --> G[Generation Context]
    G --> M[LLM]
    M --> V[Validation]
\`\`\`

See [lexical architecture](docs/lexical-architecture.md).

## Why flat mappings are insufficient

A flat source/target pair does not say which sense is intended, whether a phrase is required, which construction is natural, or which answer should be accepted. It also conflates candidate suggestions with verified evidence. This research approach treats lexical items, grammatical constraints, and directed relations as distinct evidence-bearing objects.

## Provenance and validation

Model outputs are proposals rather than linguistic truth. Each proposal is associated with its evidence and review state. Deterministic checks are separated from semantic assessment, and unresolved or conflicting evidence can lead to abstention or review. See [provenance and validation](docs/provenance-and-validation.md).

## Human decision gates

Human review is an explicit gate for ambiguous, conflicting, incomplete, or high-risk evidence. A model score alone is not sufficient to promote a lexical decision. See [human review gates](docs/human-review-gates.md).

## Planned experiment

The planned confirmatory design contains 240 concept-direction cases: 80 Polish-English, 80 Polish-German, and 80 Polish-Spanish. It compares four prespecified conditions, uses two independent generations per condition, and will yield 1,920 outputs. A separate 60-case corrupted-grounding stress test is planned. Neither study has been executed. See the [research protocol](docs/research-protocol.md).

## Research status

The public materials describe methodology and planned evaluation. They do not report a completed confirmatory benchmark, a completed public dataset, or a deployed learning product. The next evaluation step is preregistration followed by controlled execution.

## Repository contents

- [Research protocol](docs/research-protocol.md)
- [Lexical architecture](docs/lexical-architecture.md)
- [Provenance and validation](docs/provenance-and-validation.md)
- [Human review gates](docs/human-review-gates.md)
- [Error taxonomy](docs/error-taxonomy.md)
- [Limitations](docs/limitations.md)
- [Reproducibility](docs/reproducibility.md)
- [Provenance note](docs/provenance-note.md)
- [Synthetic examples](examples/)

## Public/private boundary

This repository contains newly written public research documentation and invented examples only. It excludes production code, operational tooling, credentials, deployment material, private endpoints, internal administration, raw lexical records, proprietary datasets, and learner data.

## Limitations

This repository documents a design and an evaluation plan, not proof of causal improvement. Linguistic correctness remains context-sensitive, independent evaluators may disagree, and carefully designed benchmarks can omit important real-world failure modes.

## Reproducibility

The planned study will be preregistered with fixed cases, risk categories, condition prompts, evaluation rules, aggregation, and stopping criteria before generation begins. This documentation repository is intentionally independent of any production environment. See [reproducibility](docs/reproducibility.md).

## Relationship to RevoMemo

RevoMemo is the originating research and engineering context for these methodological ideas. This repository is a public research edition, not a product source release or a representation of private implementation systems.
