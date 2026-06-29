# AGENTS.md — immutable-fact-ai

Canonical source of truth for all AI agents and human contributors on the
**immutable-fact-ai** repository. Read this fully before any edit.

## What this is — stated precisely

A **logic/STEM-first formal project**: AI systems that do not generate answers
until they understand the foundations of the question itself. The thesis (from
the README, in the owner's voice): *"The answer to the question is understanding
the foundations of the question itself."* Generation must never outrun
verification. Imagination is welcome only when standing on a foundation of
logic, math, science, standards, provenance, and clearly-labeled uncertainty.

This is the **formal/proof embodiment of the Verification Principle** that runs
through the whole Intellectual Resistance body of work — the same principle the
DNS Tool's audit engines enforce at runtime, here stated as machine-checked
mathematics.

## Stack — this is a Lean 4 project (not a typical app)

- **Lean 4** theorem prover + **Lake** build system. `lakefile.toml`,
  `lean-toolchain` (pins the exact Lean version), `lake-manifest.json`.
- Source: `ImmutableFactAI.lean` (root module) + `ImmutableFactAI/` (the
  library). `.lake/` is the build cache — **build artifact, never edit**.
- Build/check with `lake build` using the toolchain pinned in `lean-toolchain`.
  Do not change the toolchain pin casually — proofs are version-sensitive.

## Working rules

- **The artifact is a PROOF, not prose.** A change is only "done" when
  `lake build` succeeds — a green type-check is the verification bar. Never
  claim a theorem holds without the build passing. (This is the repo that
  most literally embodies Carey's Verification Principle: machine-checked or
  it didn't happen.)
- Do not weaken a theorem statement to make it compile. If a proof won't close,
  say so and show the stuck goal — don't `sorry` it shut and call it proven.
- Keep claims labeled by epistemic status (proven / measured / hypothesis /
  speculation) — that taxonomy is the project's whole point.
- Read `MILESTONE-1.md` and `immutable_fact_ai_gap_analysis.md` for current
  scope and known gaps before extending the formalization.
- License/`NOTICE.md`: protected product path (merged via
  `licensing/protected-product-path`). Keep headers intact.

## Family context

A project of the **Intellectual Resistance** (intellectualresistance.com),
same scientific-authority family as it-help.tech / dnstool.it-help.tech /
organiccomputer.me. `the_real_bot_manifesto.pdf` carries the philosophical
framing.
