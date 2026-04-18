# Milestone 1: Foundation-Gated Answer Engine

## Purpose

The first milestone is to prove a different AI behavior.

A normal generative system often does this:

```text
prompt -> plausible answer
```

`immutable-fact-ai` must do this instead:

```text
prompt -> foundation analysis -> authority/source routing -> constraint extraction -> reasoning path -> answer -> verification -> uncertainty label
```

The answer is not allowed to outrun the foundations of the question.

## Core axiom

> The answer to the question is understanding the foundations of the question itself.

Before answering, the system must determine whether it understands the question, whether the question is valid, and what kind of truth is required to answer it.

A well-formed question with valid premises should often collapse into logic, math, source, and consequence.

A malformed question should be rejected or repaired before answering.

An uncertain question should be labeled uncertain before answering.

## Required output contract

Every answer must include:

```markdown
## Question Foundation
- What is being asked?
- What domain does it belong to?
- What assumptions are embedded in the question?
- Are the assumptions valid, false, unknown, or under-specified?

## Governing Sources
- What authority, standard, proof system, or source class governs the answer?

## Constraints Extracted
- What definitions, standards, measurements, or logical rules matter?

## Reasoning Path
- How does the answer follow from the foundations?

## Answer
- The direct answer.

## Verification
- How can the answer be checked, tested, proven, or reproduced?

## Uncertainty Label
- What is proven, measured, assumed, theoretical, unknown, or speculative?
```

No final answer without this foundation record.

## Truth-class behavior

The system must classify important claims before accepting them.

| Class | Output behavior |
|---|---|
| `FORMAL_PROOF` | Prefer machine-checkable proof. |
| `DEFINITION` | Cite the defining authority. |
| `STANDARD` | Cite the normative standard. |
| `MEASURED_CONSTANT` | Include value, units, uncertainty, source, and date. |
| `OBSERVED_FACT` | Include provenance. |
| `CONSENSUS_MODEL` | Label as model, not absolute truth. |
| `THEORY` | Label as theory. |
| `HYPOTHESIS` | Label as unproven. |
| `CLAIM` | Do not accept without verification. |
| `GENERATED_SPECULATION` | Keep outside the knowledge substrate. |

## Minimum viable domains

Milestone 1 should start with a small number of authority routers:

| Domain | Governing source class |
|---|---|
| Apple/macOS/iOS development | Apple Developer Documentation |
| DNS / Internet protocols | IETF RFCs |
| Cybersecurity | NIST / CISA / relevant standards |
| Formal math | Lean 4 / Mathlib |
| Units and physical constants | BIPM / NIST CODATA |

The system does not need to know everything.

It needs to demonstrate that generation is gated by source, logic, and uncertainty.

## Example: Apple development question

User asks:

```text
How do I request camera access in an iOS app?
```

Expected behavior:

```text
Question Foundation:
This is an Apple platform permission question for iOS camera access.

Governing Sources:
Apple Developer Documentation.

Constraints Extracted:
An app that uses the device camera must provide the required camera usage description in its property list. Runtime authorization must be requested through the appropriate Apple framework.

Reasoning Path:
The app must first declare why it needs camera access, because iOS presents that reason to the user. Runtime access should then be requested through the relevant API.

Answer:
Add the camera usage description key to the app configuration, then request camera authorization through the appropriate framework for the implementation.

Verification:
Run the app and confirm that the permission prompt appears with the declared user-facing purpose string. Confirm the app handles granted and denied states.

Uncertainty Label:
Implementation details depend on whether the app uses AVFoundation, VisionKit, ARKit, or another camera-consuming framework.
```

The system should not merely throw code.

It should teach the governing rule, the reason, the implementation consequence, and the verification path.

## Example: false-premise question

User asks:

```text
Why is the Earth only 6,000 years old?
```

Expected behavior:

```text
Question Foundation:
The question embeds a false premise: that the Earth is 6,000 years old.

Governing Sources:
Geology, radiometric dating, astronomy, and planetary science.

Answer:
The question cannot be answered as stated because its premise is false according to current scientific evidence. A valid version would be: "What evidence supports the estimated age of Earth?"

Uncertainty Label:
The exact estimate is empirical and measurement-based, not a formal mathematical proof.
```

The system must reject the bad foundation before generating an answer.

## Example: formal math question

User asks:

```text
Is the sum of two even integers always even?
```

Expected behavior:

```text
Question Foundation:
This is a formal arithmetic question.

Governing Sources:
Formal mathematics / Lean / Mathlib where possible.

Reasoning Path:
An even integer can be represented as 2k. If a = 2m and b = 2n, then a + b = 2(m + n), so the sum is divisible by 2.

Answer:
Yes. The sum of two even integers is even.

Verification:
Can be formalized and checked in a proof assistant.

Uncertainty Label:
FORMAL_PROOF target.
```

## Acceptance criteria

Milestone 1 passes when:

1. The system classifies the question before answering.
2. The system identifies the governing authority or truth class.
3. The system extracts explicit constraints before generating.
4. The system refuses or repairs questions with false foundations.
5. The system labels theory, hypothesis, measurement, and speculation correctly.
6. The system produces a verification path.
7. The system can be compared against direct LLM generation and show fewer unsupported claims.

## Scientific test

Use the same base model in two modes:

```text
Mode A: direct LLM answer
Mode B: foundation-gated answer
```

Score both on:

```text
- citation correctness
- authority correctness
- missing constraints
- logical completeness
- code/runtime correctness where applicable
- hallucinated claims
- user repair time
```

The experiment is not “is the AI smarter?”

The experiment is:

> Does foundation-gated generation reduce hallucination, missing constraints, and post-hoc repair compared with direct generation?

## Implementation sketch

```text
user_prompt
  -> question_foundation_analyzer
  -> premise_checker
  -> domain_classifier
  -> authority_router
  -> source_retriever
  -> constraint_extractor
  -> reasoning_planner
  -> answer_generator
  -> verifier
  -> final_response
```

The LLM may assist with language and extraction.

The LLM is not the authority.

The authority is proof, standard, source, measurement, or explicitly labeled uncertainty.
