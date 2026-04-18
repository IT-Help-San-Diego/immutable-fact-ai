# immutable-fact-ai

**Immutable facts only AI.**

A logic/STEM-first project for building AI systems that separate formal proof, authoritative fact, measured empirical knowledge, scientific theory, hypothesis, and generated speculation.

Generative AI is not the enemy. Groundless generation is the enemy.

The failure pattern is already visible. When an image model is asked to make a simple birthday card and misspells the words, that is not just a cute rendering bug. It is a systems-design signal: the artist was allowed to render before being anchored to spelling, symbols, language, and truth. The same pattern appears at industrial scale when platforms hoard behavioral exhaust, engagement sludge, surveillance data, and manipulation signals and then call that “intelligence.”

Data bloat is the alarm whistle. Not because byte size alone proves abuse, but because unclassified data hoarding is the opposite of knowledge. The Facebook/Cambridge Analytica scandal was not merely “too much data.” It was the collection and use of personal data for profiling and targeting without proper consent. That is the warning: when data has no truth class, no provenance discipline, and no ethical boundary, it becomes machinery for influence instead of machinery for knowledge.

This project exists because imagination and creativity need a foundation beneath them.

Thus, to ensure that imagination and creativity — the generative AI hype — stand on a firm, solid foundation of 2,500 years of rock-solid, cold, hard logic beneath.

Humanity will no longer trust a robot standing before the class, giving a book report on a book it has not opened.

We see the student giving the book report.

You cannot blame the computer anymore.

## The correction

The tempting prompt is this:

> “Look through your database and delete ANYTHING that is not an immutable, highly authoritative, cited, proven scientific fact.”

But that is not how LLMs work.

A model file is not a clean database of facts. Model weights are learned numerical parameters, not an inspectable encyclopedia. You cannot prompt a neural network to delete unsupported knowledge from itself and expect a verified truth engine to remain.

So this project does **not** try to purify model bloat.

It builds a verified substrate beneath generative AI.

## Core thesis

Only knowledge that can be classified, sourced, versioned, and checked deserves to travel as knowledge.

The goal is to create a compact, auditable foundation for rational computation:

- formal logic,
- machine-checkable mathematics,
- authoritative standards,
- SI units and definitions,
- measured scientific constants with uncertainty,
- verified source manifests,
- explicit provenance,
- and clear labels for theory, hypothesis, and speculation.

Creativity is allowed.

Imagination is allowed.

Speculation is allowed.

But none of them are allowed to masquerade as fact.

## Truth classes

Every admitted statement must declare what kind of truth it is.

| Class | Meaning |
|---|---|
| `FORMAL_PROOF` | Machine-checked proof inside a formal system such as Lean or Rocq/Coq. |
| `DEFINITION` | A formal or authoritative definition. |
| `STANDARD` | A normative rule from an authoritative standards body. |
| `MEASURED_CONSTANT` | Empirical value with uncertainty, method, source, and date. |
| `OBSERVED_FACT` | Recorded observation with provenance. |
| `CONSENSUS_MODEL` | Strong current scientific model, not absolute proof. |
| `THEORY` | Explanatory framework; useful, but not mislabeled as immutable fact. |
| `HYPOTHESIS` | Unproven proposal. |
| `CLAIM` | Unverified statement. |
| `GENERATED_SPECULATION` | Model-generated output that has not been checked. |

## Design rule

No generated statement becomes knowledge until it is classified, sourced, and checked.

An LLM may be used as:

- a language interface,
- a parser,
- a claim extractor,
- a retrieval assistant,
- a proof-attempt generator,
- or a human-readable explanation layer.

An LLM is **not** the authority.

The authority is proof, source, measurement, standard, or explicitly labeled uncertainty.

## Non-goals

This project is not another chatbot.

This project is not a claim that all scientific knowledge is immutable. Mathematics can be formally proven relative to axioms. Empirical science is measured, modeled, revised, and versioned.

This project is not an attempt to preserve advertising exhaust, behavioral surveillance, engagement sludge, or opaque training sludge as “knowledge.”

A generator without a foundation is not intelligence. It is a slot machine with syntax.

## Initial technical spine

The first foundation should be small, strict, and inspectable:

- **Lean 4 / Mathlib** for formalized mathematics and proof checking.
- **Rocq/Coq** as a second formal-verification path.
- **BIPM SI definitions** for units and defining constants.
- **NIST CODATA constants** for physical constants with uncertainty and revision history.
- **IETF RFCs** for internet standards and protocol truth.
- **NIST cybersecurity publications** for security terminology, controls, and standards.
- **Hash-addressed source manifests** so claims can point to exact evidence.
- **Optional local LLMs** only as interface/tooling, not as truth sources.

## First milestone

The first milestone is not a smarter chatbot.

The first milestone is a working claim-admission system:

```text
claim -> truth class -> source/proof -> status -> explanation
```

If a statement is proven, say proven.

If it is measured, include uncertainty.

If it is theory, label it theory.

If it is speculation, do not launder it into fact.

## Reference anchors

- [Open Source Initiative: Open Source AI Definition](https://opensource.org/ai/open-source-ai-definition)
- [Open Source Initiative: Open Weights are not the same as Open Source AI](https://opensource.org/ai/open-weights)
- [Lean Mathlib](https://lean-lang.org/use-cases/mathlib/)
- [Lean Mathlib4 repository](https://github.com/leanprover-community/mathlib4)
- [BIPM: SI defining constants](https://www.bipm.org/en/measurement-units/si-defining-constants)
- [NIST: CODATA fundamental physical constants](https://pml.nist.gov/cuu/Constants/)
- [FTC: Facebook privacy settlement](https://www.ftc.gov/news-events/news/press-releases/2019/07/ftc-imposes-5-billion-penalty-sweeping-new-privacy-restrictions-facebook)
- [FTC: Cambridge Analytica matter](https://www.ftc.gov/legal-library/browse/cases-proceedings/182-3107-cambridge-analytica-llc-matter)
- [Google DeepMind: Imagen limitations](https://deepmind.google/models/imagen/)
