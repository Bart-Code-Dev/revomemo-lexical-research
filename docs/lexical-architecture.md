# Lexical architecture

## Principle

The downstream design begins with a RevoMemo concept: a language-independent statement of intended educational meaning in a bounded context. An English anchor is a reviewed explanatory handle for that concept; it is not ground truth. Each language-specific lexeme is evaluated as a possible realization of the concept.

An upstream evidence-construction layer now makes candidate-space construction explicit:

```text
external lexical resource
  -> lexical candidate inventory
  -> context-conditioned mapping evidence
  -> reviewed RevoMemo lexical decision
```

## External sense inventory

Open English WordNet (OEWN) 2025 core is the primary external sense inventory for enumerating English candidate senses. Its role is deterministic candidate enumeration and secondary lexical evidence for English-anchor review. It is not a RevoMemo concept database, automatic word-sense disambiguation system, translation database, or source of automatic lexical truth.

OEWN distinguishes words, senses, synsets, and lexical relations. That structure is useful for candidate-space control, but **an OEWN synset != a RevoMemo Concept**. OEWN asks which lexical senses are available as candidates; RevoMemo asks which intended meaning is justified for this research case.

## Candidate-sense enumeration

Candidate inventory is independent of a particular source sentence or example. A deterministic lookup is defined by the pinned resource version and artifact identity, lemma, part of speech, and normalization-procedure version. The resulting lookup identity (for example, a `lookup_sha256`) identifies this candidate inventory.

Changing source context does not itself invalidate an unchanged lemma-plus-POS candidate lookup. Candidate enumeration may return zero, one, or many candidates. A unique OEWN candidate is **not** a verified concept.

## Context-conditioned mapping

Context-conditioned mapping happens after enumeration. It considers the current effective anchor context together with the candidate inventory to produce mapping evidence. This assessment is associated with a semantic-context identity (for example, a `semantic_context_sha256`), so a later reviewer can determine what context an evaluator saw and whether the assessment remains applicable.

The relation from external evidence to a RevoMemo decision is conceptually `0..N`: there may be no justified mapping, a close mapping, or evidence that needs review. The model can assess which candidate is compatible with available context, but its output is evidence or a proposal, not automatic acceptance.

## Downstream layers

1. **RevoMemo Concept** — intended sense, scope, and distinction from nearby meanings.
2. **English anchor** — reviewed English explanation used for orientation and comparison.
3. **Language-specific lexeme** — target-language realization with lemma, part of speech, register, and local gloss.
4. **Forms, syntax, and constraints** — relevant morphology, construction, selectional restrictions, and avoidance conditions.
5. **Directed translation relation** — a source-to-target relation that records whether generation is exact, contextual, phrase-based, or unsuitable.
6. **Generation context** — a bounded package of approved information made available to a language model.
7. **Validation** — deterministic and semantic checks applied after generation.

## Why direction matters

Even when two lexemes share a concept, generation is directional. A source-to-target relation can require a construction shift, a phrase, a particular register, or an explicit prohibition. Capturing this on the relation avoids incorrectly attaching one context-specific rule to every use of a lexeme.

## Evidence freshness and abstention

Semantic assessments preserve, conceptually, semantic-context identity, provenance identity, and procedure/request identity. Historical evidence is retained and can be current, stale, or unknown. The lesson is that evidence generated against different context versions must not be treated as disagreement over the same evidence: context-version disagreement is not model disagreement.

`NO_MATCH`, `MULTIPLE_PLAUSIBLE_SENSES`, `INSUFFICIENT_SOURCE_CONTEXT`, `CONFLICTING_EVIDENCE`, and `NONE_OF_THE_ABOVE` are valid outcomes. For example, a context-free `bank` with multiple OEWN candidates should support deferment rather than forced selection.
