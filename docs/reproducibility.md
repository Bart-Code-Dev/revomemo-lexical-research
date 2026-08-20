# Reproducibility

## Planned preregistration

Before confirmatory generation, the study will preregister:

- the case-selection policy and fixed case set;
- the four risk categories;
- condition definitions and information budgets;
- generation settings, token limits, output schemas, seeds where available, and independent-generation rule;
- deterministic validator rules and condition-blinded model-grading instructions;
- repeated-grading procedure, including reversed grading order where applicable;
- grader-stability, agreement, disagreement-flagging, and exclusion policy;
- primary endpoint, aggregation, comparisons, and uncertainty reporting;
- the corrupted-grounding stress-test procedure; and
- the separately specified component-ablation subset, selection policy, multiplicity handling, and analysis policy.

## Resource and evidence freezing

Before confirmatory execution, the study will freeze the external lexical-resource name, release/version, official source, artifact hash or equivalent identity, license, and normalization procedure. It will also freeze the candidate-lookup procedure, semantic-context schema or procedure, case-level lexical evidence, conditions, prompts, model versions, grader instructions, and analysis rules.

An OEWN release is never silently substituted underneath a frozen benchmark. An upgrade from OEWN 2025 to a later release is a new evidence-resource version; after preregistration, it requires an explicit amendment.

## Benchmark evaluation

The benchmark evaluation plan combines deterministic validators for rule-checkable properties with condition-blinded model grading for semantic and educational criteria. Repeated grading estimates stability, and agreement across independent grading runs is measured. Substantial disagreement is handled under preregistered flagging and exclusion rules rather than automatic acceptance.

The study does not promise or assume availability of independent bilingual human reviewers for every benchmark output. Automated and model-based grading are evidence for evaluation, not linguistic ground truth.

## Public boundary

Reproducibility does not require production access. A public package can contain synthetic fixtures, protocol versions, aggregate results, and analysis materials while excluding private lexical data, learner information, operational systems, and credentials.
