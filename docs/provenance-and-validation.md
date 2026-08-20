# Provenance and validation

## Proposals are not truth

Language models may propose candidate senses, lexemes, examples, constructions, relations, repairs, or grades. A proposal remains a proposal until it satisfies the applicable checks and review policy. Fluency, confidence language, or agreement between generated outputs is not proof of correctness.

## Evidence roles

The methodology distinguishes five roles:

- **Lexical-resource evidence** supplies versioned external candidate inventory information.
- **Model proposal** assesses contextual compatibility or proposes a lexical or generated realization.
- **Contextual mapping evidence** links the available source context and candidate inventory to a possible reviewed decision.
- **Deterministic validation** checks observable structural and procedural requirements.
- **Human/review decision** resolves evidence that remains ambiguous, conflicting, incomplete, or high-risk.

No role is silently promoted into another. In particular, external-resource presence and model agreement do not establish intended meaning.

## Context identity and freshness

Each semantic assessment is associated conceptually with three distinct identities: the semantic context it saw, its provenance, and the procedure or request that produced it. This permits later assessment of applicability when the current effective anchor context changes.

Historical evidence is retained rather than deleted. Its applicability may be **current**, **stale**, or **unknown**. The same response evaluated against changed context can therefore become stale evidence. Evidence from different context versions must not be reported as model disagreement over the same evidence.

## Two kinds of validation

**Deterministic validation** checks observable structure: required fields, identifiers, allowed states, internal references, duplicate handling, serialization, and consistency of declared constraints.

**Semantic validation** asks whether a realization expresses the intended concept in context, whether its construction is natural, and whether a relation preserves required information. It may return pass, reject, ambiguity, or a request for review.

Keeping these layers separate prevents a well-formed record from being confused with a linguistically sound one.

## Abstention and disagreement

Incomplete source context, multiple plausible senses, conflicting assessments, unsupported confidence, or an unresolved distinction should produce abstention or a review queue rather than silent acceptance. Valid outcomes include `NO_MATCH`, `MULTIPLE_PLAUSIBLE_SENSES`, `INSUFFICIENT_SOURCE_CONTEXT`, `CONFLICTING_EVIDENCE`, and `NONE_OF_THE_ABOVE`. Automated grading can assist analysis but is not linguistic ground truth.
