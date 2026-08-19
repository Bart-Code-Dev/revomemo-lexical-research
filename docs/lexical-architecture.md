# Lexical architecture

## Principle

The design begins with a concept: a language-independent statement of intended meaning in a bounded context. An English anchor is a reviewed explanatory handle for that concept; it is not automatically treated as ground truth. Each language-specific lexeme is then evaluated as a possible realization of the concept.

## Layers

1. **Concept** — intended sense, scope, and distinction from nearby meanings.
2. **English anchor** — reviewed English explanation used for orientation and comparison.
3. **Language-specific lexeme** — target-language realization with lemma, part of speech, register, and local gloss.
4. **Forms, syntax, and constraints** — relevant morphology, construction, selectional restrictions, and avoidance conditions.
5. **Directed translation relation** — a source-to-target relation that records whether generation is exact, contextual, phrase-based, or unsuitable.
6. **Generation context** — a bounded package of approved information made available to a language model.
7. **Validation** — deterministic and semantic checks applied after generation.

## Why direction matters

Even when two lexemes share a concept, generation is directional. A source-to-target relation can require a construction shift, a phrase, a particular register, or an explicit prohibition. Capturing this on the relation avoids incorrectly attaching one context-specific rule to every use of a lexeme.

## Evidence states

The approach distinguishes candidate, validated, rejected, and needs-review evidence. A missing field or plausible-looking string is not a verified lexical claim. This supports explicit abstention when evidence cannot support a safe decision.
