# immutable-fact-ai

**Immutable facts only AI.**

A logic/STEM-first project for building AI systems that do not generate answers until they understand the foundations of the question itself.

> The answer to the question is understanding the foundations of the question itself.

That is the starting rule.

Current generative AI too often jumps from prompt to plausible output. It does not first ask whether the question is well-formed, whether its assumptions are true, what domain governs the answer, what authority applies, what can be proven, what is merely measured, and what is only theory, hypothesis, or speculation.

That is not reasoning. That is generation outrunning verification.

This project exists to reverse that order.

Generative AI is not the enemy. Groundless generation is the enemy.

Imagination and creativity matter. But if imagination is not standing on a foundation of logic, math, science, standards, provenance, and clearly labeled uncertainty, it becomes noise. A generator without a foundation is not intelligence. It is an AI slot machine with syntax.

When an image model is asked to create a simple birthday card and misspells the words, that is not just a cute rendering failure. It is a systems-design signal: the artist was allowed to render before being anchored to spelling, symbols, language, and truth. STEM knowledge would have helped the artist. Foundations would have helped the generator.

The same failure pattern appears at industrial scale when platforms hoard behavioral exhaust, surveillance signals, engagement sludge, and manipulation data and call it “intelligence.” Data bloat does not automatically prove abuse, but unclassified data hoarding is an alarm whistle. Knowledge has structure, provenance, and purpose. Behavioral exhaust is not knowledge.

Humanity will no longer trust a robot standing before the class giving a book report on a book it has not opened.

We see the student giving the book report.

You cannot blame the computer anymore.

## The correction

The tempting prompt is:

> “Look through your database and delete ANYTHING that is not an immutable, highly authoritative, cited, proven scientific fact.”

But that is not how LLMs work.

A model file is not a clean fact database. Model weights are learned numerical parameters, not an inspectable encyclopedia. You cannot prompt a neural network to delete unsupported knowledge from itself and expect a verified truth engine to remain.

So this project does **not** try to purify model bloat.

It builds a verified substrate beneath generative AI.

## Core thesis

Only knowledge that can be classified, sourced, versioned, and checked deserves to travel as knowledge.

The system should not answer first. It should first determine:

1. Do I understand the question?
2. Are the premises valid?
3. What domain governs this question?
4. What authority or formal system applies?
5. What definitions, standards, measurements, or proofs are required?
6. What can be answered by logic?
7. What must be labeled as uncertain, theoretical, incomplete, or speculative?

If the question is valid and the foundations are known, the answer should often become simple: cold logic, math, source, consequence.

If the question is malformed, the system should say so.

If the question depends on unsupported assumptions, the system should expose them.

If the answer requires external authority, the system should check it.

If the answer is theory, it should be labeled theory.

If the answer is speculation, it should not be laundered into fact.

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

## First milestone

The first milestone is not a smarter chatbot.

The first milestone is a **foundation-gated answer engine**.

Before producing an answer, the system must create a problem foundation record:

```text
question -> foundation analysis -> authority/source routing -> constraints -> reasoning path -> answer -> verification -> uncertainty label
```

The system must prove a different behavior:

> No final answer without first understanding the foundations of the question.

For example:

- If the question is about Apple development, check Apple Developer Documentation.
- If the question is about DNS or Internet protocols, check the relevant RFCs.
- If the question is mathematical, prefer formal proof systems such as Lean/Mathlib.
- If the question is empirical science, distinguish measurement, model, theory, and hypothesis.
- If the question has a false premise, reject the premise before answering.

See [`MILESTONE-1.md`](MILESTONE-1.md) for the first implementation target.

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

## Non-goals

This project is not another chatbot.

This project is not a claim that all scientific knowledge is immutable. Mathematics can be formally proven relative to axioms. Empirical science is measured, modeled, revised, and versioned.

This project is not an attempt to preserve advertising exhaust, behavioral surveillance, engagement sludge, or opaque training sludge as “knowledge.”

## Project status

This is an early-stage architecture and implementation effort.

The immediate goal is not to solve all truth. The immediate goal is to prove that an AI system can be forced to understand the foundations of a question before it generates an answer.

Creativity is allowed.

Imagination is allowed.

Speculation is allowed.

But none of them are allowed to masquerade as fact.

## Reference anchors

- [Open Source Initiative: Open Source AI Definition](https://opensource.org/ai/open-source-ai-definition)
- [Open Source Initiative: Open Weights are not the same as Open Source AI](https://opensource.org/ai/open-weights)
- [Lean Mathlib](https://lean-lang.org/use-cases/mathlib/)
- [Lean Mathlib4 repository](https://github.com/leanprover-community/mathlib4)
- [BIPM: SI defining constants](https://www.bipm.org/en/measurement-units/si-defining-constants)
- [NIST: CODATA fundamental physical constants](https://pml.nist.gov/cuu/Constants/)
- [IETF RFC process](https://www.ietf.org/process/rfcs/)
- [FTC: Facebook privacy settlement](https://www.ftc.gov/news-events/news/press-releases/2019/07/ftc-imposes-5-billion-penalty-sweeping-new-privacy-restrictions-facebook)
- [FTC: Cambridge Analytica matter](https://www.ftc.gov/legal-library/browse/cases-proceedings/182-3107-cambridge-analytica-llc-matter)
