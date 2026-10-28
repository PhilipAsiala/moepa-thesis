# A Dual-Domain Cognitive Architecture for Enterprise AI Governance: Decoupling Probabilistic Epistemic Inference from Deterministic Axiological Arbitration

A model proposes. It does not commit.

Working front matter, drawn from [draft/thesis.md](draft/thesis.md). The eight-chapter outline, the commitment function, and the development plan remain there. This page does not replace the prospectus. Where the two differ, the prospectus governs.

Specification cited: Philip Asiala, *The MOEPA Cognitive Architecture — Technical Specification* (v3.1, 18 October 2026), in [moepa-cognitive-architecture](https://github.com/PhilipAsiala/moepa-cognitive-architecture) `catalog/ARCHITECTURE.md`. The reference implementation is the [moepa-lab](https://github.com/PhilipAsiala/moepa-lab) stack. The record is JSON-LD against an owned context, normatively shaped by [moepa-profile](https://github.com/PhilipAsiala/moepa-profile).

## Abstract

Enterprise AI fails first as organizational design. Eligibility rules, safety interlocks, and the thresholds that authorize or block a transaction are written into application code and into the sampling procedure. An engineer who blocks a transaction whenever a model’s confidence falls below $0.85$ has inscribed a strategic decision in an implementation artifact. The threshold is then invisible to the leadership that owns the constraint, unauditable as policy, and fused with the epistemic state that occasioned it. Prompt engineering, reinforcement learning from human feedback, and raw token probability do not restore the separation.

This prospectus proposes MOEPA (Metrology, Ontology, Epistemology, Praxeology, Axiology) as the architecture that reverses that anti-pattern. The ledger stores the business logic. The technology implements it. A foundation model remains an uncommitted advisor: its output is an epistemic proposal, a tuple of candidate, graded confidence, metrological metadata (how each value was measured, and how far it can be trusted), evidence pointers, defeaters (facts or cues that reduce confidence or rebut the claim), and an explicit unknown. Commitment is a separate decision procedure. The candidate is admitted only when three deterministic checks pass against one snapshot: ontological grounding in discrete identifiers, praxeological preconditions and allowable transitions, and axiological non-compensatory constraints encoded as policy. Confidence is not an input to the axiological check, and it never overrides a deny. Inscribing a probability on an entity record is a category mistake. Uncertainty stays attached to the claim.

A decision is auditable when it records the policy snapshot identifier and the gate results. Data sovereignty, on this account, is retention of that cognitive history — lineage, refinement rules, and epistemic claims — in an open serialization: the MOEPA record, one triple with its epistemic, metrological, axiological, and praxeological envelopes as JSON-LD against an organization-owned context, stored in Apache Iceberg. A bare export of extensional rows does not preserve it. The prospectus formalizes the commitment function, specifies a reference implementation, and proposes an evaluation of the gating design. The gating design does not prove alignment, and it does not prove that the snapshot is correct or complete.

## Central Thesis Statement

A model proposes. It does not commit. The prevailing failure of enterprise AI is an inversion of authority. Business strategy is implemented as control flow: a confidence cutoff, an eligibility branch, a block-or-allow literal in service code. The organization then cannot inspect, version, or amend the rule except by changing the program. Leadership has lost the steering wheel to the codebase.

MOEPA reverses the inversion. An epistemic proposal carries a graded confidence and does not commit a fact, an entity, or a permission. Three deterministic admission checks follow, in order: ontological grounding, praxeological preconditions, and axiological non-compensatory constraints. Commit only if all three pass. The rules those checks apply are stored in the ledger and exported as a policy bundle. The runtime evaluates the bundle. It does not contain the strategy.

A numeric threshold is the same inversion in miniature. A procedure that blocks a transaction when $\mathcal{P}(\hat{y} \mid x) \lt 0.85$ treats an epistemic state as an axiological permission and locates the permission in source code. If leadership adopts a threshold, the threshold is a versioned clause in $\mathcal{K}_{\mathrm{policy}}$. The axiological check does not receive $\mathcal{P}(\hat{y} \mid x)$. Confidence never overrides a deny. This is a gating design. It does not prove alignment. Auditability means the decision records the policy snapshot identifier and the gate results. Cryptographic signing is future work.

The model may integrate evidence with graded confidence. Commitment to an entity, an authorized transition, or a non-compensatory constraint is a separate decision procedure. Tagging a passage with a MOEPA layer does not implement that procedure. A schema check, a graph lookup, and a policy evaluation can. MOEPA and Marr answer different questions. This prospectus does not cross them into one model.

## Chapters

| Chapter | File |
|---|---|
| 1. Introduction and the Organizational Design Impasse | [docs/thesis-chapter-1-organizational-design.md](docs/thesis-chapter-1-organizational-design.md) |
| 2. Theoretical Foundations | [docs/thesis-chapter-2-marr-moepa.md](docs/thesis-chapter-2-marr-moepa.md) |
| 3. The MOEPA Dual-Domain Cognitive Framework | [docs/thesis-chapter-3-dual-domain.md](docs/thesis-chapter-3-dual-domain.md) |
| 4. Unified Data Substrate and Specialized Compute Projections | [docs/thesis-chapter-4-substrate.md](docs/thesis-chapter-4-substrate.md) |
| 5. Reference Implementation and System Orchestration | [docs/thesis-chapter-5-reference-implementation.md](docs/thesis-chapter-5-reference-implementation.md) |
| 6. Empirical Evaluation and Validation | [docs/thesis-chapter-6-evaluation.md](docs/thesis-chapter-6-evaluation.md) |
| 7. Systems Governance, Sovereign Infrastructure, and Deployment Patterns | [docs/thesis-chapter-7-governance.md](docs/thesis-chapter-7-governance.md) |
| 8. Conclusion and Future Research Directions | [docs/thesis-chapter-8-conclusion.md](docs/thesis-chapter-8-conclusion.md) |

## Repository

The architecture specification stays in [moepa-cognitive-architecture](https://github.com/PhilipAsiala/moepa-cognitive-architecture). The running stack stays in [moepa-lab](https://github.com/PhilipAsiala/moepa-lab). This repository holds the thesis argument.

| Repo | Role |
|---|---|
| [moepa-cognitive-architecture](https://github.com/PhilipAsiala/moepa-cognitive-architecture) | Reference architecture: the technical specification (`catalog/ARCHITECTURE.md`) and the enterprise capability catalog (`DS1`–`DS8`, `AG1`–`AG8`) |
| [moepa-profile](https://github.com/PhilipAsiala/moepa-profile) | Normative shape of the MOEPA record: JSON-LD 1.1 context, vocabulary, SHACL shapes (formerly `spop-profile`) |
| [moepa-lab](https://github.com/PhilipAsiala/moepa-lab) | Runnable stack built to that catalog, one deployable unit per capability, with a check per unit |
| **This repo** | Thesis draft |

The four repositories are cloned side by side:

```
~/source/thesis/
  moepa-cognitive-architecture/   specification and catalog
  moepa-profile/                  the record: context, vocabulary, shapes
  moepa-lab/                      running stack
  moepa-thesis/                   this repo
```

`moepa-lab` replaces the earlier `philosophical-ai-lab`. The lab was a scaffold of intended labs, one per layer, that were never filled in. The stack is the implementation: a lakehouse system of record, rebuildable graph and vector projections, a policy engine, and one policy-enforcing gateway, running on the host **nitro** and verified by per-capability checks. `moepa-cognitive-architecture` is the renamed `philosophical-ai-architecture`; the old name redirects. `moepa-profile` is the renamed `spop-profile`: the record moved from N-Quads to JSON-LD, and the profile moved with it.

This repository is the public remote. `main` holds the working draft. [draft/thesis.md](draft/thesis.md) is the source of the argument: the eight-chapter outline, the commitment function, and the three-phase plan. Benchmarks in that file are proposed, not reported. Where the draft describes the substrate, the gateway, or the reference implementation, it describes the specification at v3.1 and the stack as built; nothing the stack's checks prove is reported as a thesis result. Chapter drafts in [docs/](docs/) develop that file and defer to it. The development plan stays in the draft.

```
README.md                                               this page: abstract, central thesis, chapter index
draft/thesis.md                                         working draft (source of the argument)
docs/thesis-chapter-1-organizational-design.md          Chapter 1
docs/thesis-chapter-2-marr-moepa.md                     Chapter 2
docs/thesis-chapter-3-dual-domain.md                    Chapter 3, including the commitment function
docs/thesis-chapter-4-substrate.md                      Chapter 4
docs/thesis-chapter-5-reference-implementation.md       Chapter 5
docs/thesis-chapter-6-evaluation.md                     Chapter 6 (benchmarks proposed, not run)
docs/thesis-chapter-7-governance.md                     Chapter 7
docs/thesis-chapter-8-conclusion.md                     Chapter 8
AGENTS.md                                               how agents should treat this repo
```
