# Research protocol

## Status

This is a planned confirmatory design. It has not been executed, and its benchmark has not yet been preregistered.

## Objective

Evaluate whether typed lexical grounding reduces the rate of critical educational errors in multilingual language-learning generation.

## Case set

The confirmatory case set will contain 240 concept-direction cases:

- 80 Polish-English cases
- 80 Polish-German cases
- 80 Polish-Spanish cases

Cases will be allocated across four prespecified risk categories:

1. Polysemy and false friends.
2. Construction, part-of-speech, valency, or case/preposition-government changes.
3. Contextual, phrase-based, or one-to-many equivalents.
4. Low-risk exact equivalents.

## Conditions

Each case will be evaluated under four conditions.

| Condition | Context supplied to the generator |
| --- | --- |
| A. Legacy flat source/target fields | Minimal paired fields without explicit sense or typed constraints. |
| B. On-demand lexical planning | A planning prompt that asks the model to reason about the case at generation time. |
| C. Information-matched unstructured prose | The same substantive information as D, expressed as prose rather than typed objects. |
| D. Typed lexical grounding | Concept, anchor, lexeme, form/syntax/constraint, and directed-relation context represented as typed fields. |

Two independent generations will be collected for every case-condition combination: 240 × 4 × 2 = **1,920 outputs**.

## Primary endpoint

The primary endpoint is the presence of at least one critical educational error in an output.

Critical errors are:

- wrong lexical sense;
- non-equivalent translation;
- invalid target construction;
- ambiguous expected answer;
- explicit constraint violation.

The primary analysis will use a preregistered case-level aggregation rule. Generation identity, prompts, evaluators, adjudication rules, exclusions, and uncertainty estimates will be fixed before execution.

## Corrupted-grounding stress test

A separate planned 60-case stress test will introduce controlled defects into otherwise structured grounding. It tests whether validation and review detect inconsistent sense, relation, construction, or constraint evidence. This is a planned robustness assessment, not a completed result.

## Evaluation safeguards

- Deterministic validators will evaluate rule-checkable properties.
- Condition-blinded model-based graders will evaluate semantic and educational criteria against the prespecified intended meaning and context.
- Automated and model-based grading will not be treated as linguistic ground truth.
- Repeated judgments will be used to estimate grader stability; grading order will be reversed in repeated evaluations where applicable.
- Agreement across independent grading runs will be measured.
- Substantial grader disagreement will flag a case under the preregistered policy rather than automatically accepting it.
- The study does not assume that independent bilingual human reviewers will be available for every output in the full benchmark.
- Outputs, evaluation forms, and analysis code will be versioned before primary analysis.
