# Provenance and validation

## Proposals are not truth

Language models may propose useful candidate senses, lexemes, examples, constructions, and relations. A proposal remains a proposal until it satisfies the applicable checks and review policy. Fluency, confidence language, or agreement between generated outputs is not proof of correctness.

## Provenance

For each research workflow, provenance should record input version, prompt or procedure version, generation identity, validation result, reviewer decision when used, and resulting evidence state. This lets a later reader distinguish an observation, a model proposal, a deterministic check, and a human decision.

## Two kinds of validation

**Deterministic validation** checks observable structure: required fields, identifiers, allowed states, internal references, duplicate handling, serialization, and consistency of declared constraints.

**Semantic validation** asks whether a realization expresses the intended concept in context, whether its construction is natural, and whether a relation preserves required information. It may return pass, reject, ambiguity, or a request for review.

Keeping these layers separate prevents a well-formed record from being confused with a linguistically sound one.

## Abstention and disagreement

Incomplete evidence, conflicting assessments, unsupported confidence, or an unresolved distinction should produce abstention or a review queue rather than silent acceptance. Human decisions are explicit gates. Automated grading can assist analysis but is not linguistic ground truth.
