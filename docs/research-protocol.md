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

1. lexical polysemy and sense selection;
2. non-equivalent translation choices;
3. construction-sensitive realization;
4. explicit lexical or grammatical constraints.

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

- Evaluators will assess outputs against the prespecified intended meaning and context.
- Automated grading will not be treated as linguistic ground truth.
- Ambiguous ratings will be retained and handled under a preregistered adjudication policy.
- Outputs, evaluation forms, and analysis code will be versioned before primary analysis.
