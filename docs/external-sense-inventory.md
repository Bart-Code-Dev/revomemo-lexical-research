# External sense inventory

## Purpose

This document records the role of Open English WordNet (OEWN) 2025 core in constructing and auditing research grounding before generation. OEWN is the **primary external sense inventory** for English candidate enumeration. It helps define and constrain the lexical candidate space; it does not determine the intended educational concept or test whether WordNet is correct.

## Why an external inventory is used

An external inventory turns an open-ended question such as “What does this word mean?” into a bounded evidence question: given a versioned candidate inventory and available source evidence, which candidate, if any, is justified? This is a methodological refinement intended to reduce unbounded sense invention, unsupported lexical confidence, and implicit sense collapse. It does not claim those outcomes have been reduced.

OEWN represents words, senses, synsets, definitions, and lexical relations. Its English lexical graph can also support later enrichment, generator grounding, competing-sense and negative-context evidence, and—at lower priority—future multilingual bridging through the Interlingual Index (ILI).

## Resource identity and attribution

The preflight used **Open English WordNet 2025 core**: the common-noun, verb, adjective, and adverb edition, rather than the 2025+ edition that additionally contains curated proper nouns. Official sources describe the 2025 release and downloads at [en-word.net/downloads](https://en-word.net/downloads), the resource structure at [globalwordnet/english-wordnet](https://github.com/globalwordnet/english-wordnet), and the license as [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

| Field | Pinned preflight identity |
| --- | --- |
| Resource | Open English WordNet |
| Edition | 2025 core |
| Release/tag | `2025-edition` |
| Canonical interchange | WN-LMF |
| Local query representation | JSON |
| JSON SHA-256 | `7d749f6e2c39e6970e4997839dcf6e42fd281f3c2fae0171d2192bae8cfa4b51` |

For each frozen research use, the public methodology requires preservation of the resource name, release/version, official source, downloaded artifact identity or hash, license, and normalization procedure. This repository does not reproduce OEWN data; aggregate statistics and synthetic examples are used instead.

## Candidate enumeration and contextual mapping

Candidate enumeration is deterministic and context-independent: pinned OEWN version plus artifact identity, normalized lemma, POS, and normalization version produce the candidate inventory. Its lookup identity may be represented as `lookup_sha256`.

Contextual mapping is different: current effective anchor context plus the candidate inventory produces contextual mapping evidence. Its semantic-context identity may be represented as `semantic_context_sha256`. A changed semantic context can stale a mapping assessment but should not invalidate an unchanged lemma-plus-POS lookup.

OEWN candidate enumeration does not perform automatic WSD or automatic acceptance. `bank` with no source sense or context and many candidates supports `INSUFFICIENT_SOURCE_CONTEXT` or deferment, not a forced selection. Even one candidate after POS filtering does not prove that a RevoMemo concept equals that candidate.

## Deterministic resource preflight — not confirmatory model results

The following aggregate results describe a deterministic lexical-resource and engineering preflight on the current research corpus. They are **not confirmatory model results**, do not measure generation quality, and do not support a causal claim about the primary hypothesis.

Source for every quantitative result in this section: the deterministic OEWN 2025-core preflight of the current research corpus, reported only in aggregate in this public repository.

| Measure | Result |
| --- | ---: |
| Translation groups | 7,900 |
| Unique English surfaces | 7,866 |
| Unique lemmas | 7,857 |
| Exact surface match | 7,744 / 98.03% |
| Lemma match | 7,747 / 98.06% |
| Lemma + POS candidate match | 7,649 / 96.82% |
| Zero candidates | 251 / 3.18% |

Candidate ambiguity after POS filtering was 251 / 3.18% with zero candidates, 1,916 / 24.25% with one, 1,859 / 23.53% with two, 2,742 / 34.71% with three to five, 902 / 11.42% with six to ten, and 230 / 2.91% with more than ten candidates. Among candidate synsets, definition coverage was 100%, example coverage 59.01%, and ILI coverage 99.51%.

For multiword expressions, 24 records were identified: 13 exact matches, two normalized or lemma matches, and nine absent. OEWN 2025+ supplied one additional corpus match, `Midwest`; this preflight otherwise concerns OEWN 2025 core. These are descriptive coverage observations only.

## Sense granularity and upgrades

OEWN sense boundaries and RevoMemo teaching-concept boundaries may differ. Resource coverage, sense granularity, domain fit, and source-context quality therefore remain review questions. An OEWN 2025-to-future-release upgrade is a new evidence-resource version and must not silently replace a release beneath a frozen benchmark; after preregistration it requires an amendment.
