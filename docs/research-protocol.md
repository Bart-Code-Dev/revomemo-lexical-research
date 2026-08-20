# Research protocol

## Status

This is a planned confirmatory design. It has not been executed, and its benchmark has not yet been preregistered.

## Objective

Evaluate whether typed, sense-first lexical grounding reduces the rate of critical educational errors in multilingual language-learning generation.

## Grounding construction

Before research cases are frozen, external lexical evidence is used upstream to enumerate English candidate senses and support review of the intended educational concept. OEWN 2025 core is a versioned candidate inventory, not an experimental condition, a RevoMemo concept database, or automatic WSD. Candidate enumeration can yield no justified mapping or a need for abstention; it never forces sense selection.

The frozen case then contains reviewed lexical evidence appropriate to its condition. Models act as contextual evaluators, generators, or graders under controlled evidence; their outputs remain proposals or evaluation evidence, not lexical truth.

## Case set

The primary confirmatory case set will contain 240 concept-direction cases:

- 80 Polish-English cases
- 80 Polish-German cases
- 80 Polish-Spanish cases

Each direction contains 20 cases in each prespecified risk category:

1. Polysemy and false friends.
2. Construction, part-of-speech, valency, or case/preposition-government changes.
3. Contextual, phrase-based, or one-to-many equivalents.
4. Low-risk exact equivalents.

## Conditions and information-equivalence requirement

Each primary case will be evaluated under four conditions.

| Condition | Context supplied to the generator |
| --- | --- |
| A. Legacy flat source/target fields | Minimal paired fields without explicit sense or typed constraints. |
| B. On-demand lexical planning | A planning prompt that asks the model to reason about the case at generation time. |
| C. Information-matched unstructured prose | The same substantive verified lexical facts as D, expressed as unstructured prose. |
| D. Typed lexical grounding | The same substantive verified lexical facts as C, represented as typed lexical objects and relations. |

The C-versus-D comparison tests representation effect, not extra information. OEWN-derived facts included in frozen D evidence must be made substantively available in C in its prose form.

Two independent generations will be collected for every case-condition combination: 240 × 4 × 2 = **1,920 outputs**.

## Primary endpoint

The primary endpoint is the presence of at least one critical educational error in an output:

- wrong lexical sense;
- non-equivalent translation;
- invalid target construction;
- ambiguous expected answer;
- explicit constraint violation.

The primary analysis will use a preregistered case-level aggregation rule. Generation identity, prompts, evaluators, adjudication rules, exclusions, and uncertainty estimates will be fixed before execution.

## Secondary component-ablation analysis

The A/B/C/D comparison does not by itself identify the marginal contribution of sense disambiguation, structured syntax, directed translation edges, or negative constraints. A separate, planned, preregistered component-ablation analysis will address that submitted question without changing the primary 1,920-output benchmark.

The conceptual conditions are `FULL_TYPED`, `MINUS_SENSE_INFORMATION`, `MINUS_STRUCTURED_SYNTAX`, `MINUS_DIRECTED_RELATION`, and `MINUS_NEGATIVE_CONSTRAINTS`. Each removes the named information rather than random text: sense ablation removes explicit intended-sense identification; syntax ablation removes typed construction requirements while retaining lexical identity; relation ablation removes the explicit source-to-target constraint; and negative-constraint ablation removes avoid/forbidden/literal-mapping constraints while retaining positive evidence.

The ablation subset will be risk-stratified so a removed component is relevant. Exact subset size, selection policy, prompt wording, leakage or reconstruction controls, multiplicity handling, and analysis policy remain to be frozen during preregistration. This analysis has not been executed.

## Corrupted-grounding robustness test

A separate planned 60-case stress test will introduce controlled defects into otherwise structured grounding. Its submitted general defect families remain wrong senses, swapped edges, missing constraints, and contradictory syntax. The external inventory allows more controlled variants, including correct lemma/POS with a wrong candidate sense, source context inconsistent with a selected sense, missing negative constraints, conflicting positive and negative evidence, and incomplete grounding. The final corruption distribution is not yet specified.

This is a planned robustness assessment, not a completed result. It supports the question of whether models propagate defective lexical information, detect conflict, or abstain.

## Research phases

1. **Phase 0 — Grounding construction and lexical-resource preflight:** external sense inventory, context-versioning, candidate enumeration, lexical review, validation, and benchmark case construction. This is not confirmatory outcome evidence.
2. **Phase 1 — Primary confirmatory benchmark:** A/B/C/D, 240 cases, and 1,920 planned outputs; it chiefly addresses structured-versus-control comparisons and the first research question.
3. **Phase 2 — Secondary component ablation:** preregistered analysis of component contribution, with its design still to be frozen.
4. **Phase 3 — Corrupted-grounding robustness test:** the separate planned 60-case test supporting the third research question.

## Evaluation safeguards

- Deterministic validators will evaluate rule-checkable properties.
- Condition-blinded model-based graders will evaluate semantic and educational criteria against the prespecified intended meaning and context.
- Automated and model-based grading will not be treated as linguistic ground truth.
- Repeated judgments will be used to estimate grader stability; grading order will be reversed in repeated evaluations where applicable.
- Agreement across independent grading runs will be measured.
- Substantial grader disagreement will flag a case under the preregistered policy rather than automatically accepting it.
- The study does not assume that independent bilingual human reviewers will be available for every output in the full benchmark.
- Outputs, evaluation forms, and analysis code will be versioned before primary analysis.
