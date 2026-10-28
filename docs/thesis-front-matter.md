# A Dual-Domain Cognitive Architecture for Enterprise AI Governance: Decoupling Probabilistic Epistemic Inference from Deterministic Axiological Arbitration

A model proposes. It does not commit.

Working front matter, drawn from [draft/thesis.md](../draft/thesis.md). The eight-chapter outline, the commitment function, and the development plan remain there. This file does not replace the prospectus. Where the two differ, the prospectus governs.

Specification cited: Philip Asiala, *The MOEPA Cognitive Architecture — Technical Specification* (v3.1, 18 October 2026), in [moepa-cognitive-architecture](https://github.com/PhilipAsiala/moepa-cognitive-architecture) `catalog/ARCHITECTURE.md`. The reference implementation is the [moepa-lab](https://github.com/PhilipAsiala/moepa-lab) stack. The record is JSON-LD against an owned context, normatively shaped by [moepa-profile](https://github.com/PhilipAsiala/moepa-profile).

## Abstract

Enterprise AI fails first as organizational design. Eligibility rules, safety interlocks, and the thresholds that authorize or block a transaction are written into application code and into the sampling procedure. An engineer who blocks a transaction whenever a model’s confidence falls below \(0.85\) has inscribed a strategic decision in an implementation artifact. The threshold is then invisible to the leadership that owns the constraint, unauditable as policy, and fused with the epistemic state that occasioned it. Prompt engineering, reinforcement learning from human feedback, and raw token probability do not restore the separation.

This prospectus proposes MOEPA (Metrology, Ontology, Epistemology, Praxeology, Axiology) as the architecture that reverses that anti-pattern. The ledger stores the business logic. The technology implements it. A foundation model remains an uncommitted advisor: its output is an epistemic proposal, a tuple of candidate, graded confidence, metrological metadata (how each value was measured, and how far it can be trusted), evidence pointers, defeaters (facts or cues that reduce confidence or rebut the claim), and an explicit unknown. Commitment is a separate decision procedure. The candidate is admitted only when three deterministic checks pass against one snapshot: ontological grounding in discrete identifiers, praxeological preconditions and allowable transitions, and axiological non-compensatory constraints encoded as policy. Confidence is not an input to the axiological check, and it never overrides a deny. Inscribing a probability on an entity record is a category mistake. Uncertainty stays attached to the claim.

A decision is auditable when it records the policy snapshot identifier and the gate results. Data sovereignty, on this account, is retention of that cognitive history — lineage, refinement rules, and epistemic claims — in an open serialization: the MOEPA record, one triple with its epistemic, metrological, axiological, and praxeological envelopes as JSON-LD against an organization-owned context, stored in Apache Iceberg. A bare export of extensional rows does not preserve it. The prospectus formalizes the commitment function, specifies a reference implementation, and proposes an evaluation of the gating design. The gating design does not prove alignment, and it does not prove that the snapshot is correct or complete.

## Central Thesis Statement

A model proposes. It does not commit. The prevailing failure of enterprise AI is an inversion of authority. Business strategy is implemented as control flow: a confidence cutoff, an eligibility branch, a block-or-allow literal in service code. The organization then cannot inspect, version, or amend the rule except by changing the program. Leadership has lost the steering wheel to the codebase.

MOEPA reverses the inversion. An epistemic proposal carries a graded confidence and does not commit a fact, an entity, or a permission. Three deterministic admission checks follow, in order: ontological grounding, praxeological preconditions, and axiological non-compensatory constraints. Commit only if all three pass. The rules those checks apply are stored in the ledger and exported as a policy bundle. The runtime evaluates the bundle. It does not contain the strategy.

A numeric threshold is the same inversion in miniature. A procedure that blocks a transaction when \(\mathcal{P}(\hat{y} \mid x) < 0.85\) treats an epistemic state as an axiological permission and locates the permission in source code. If leadership adopts a threshold, the threshold is a versioned clause in \(\mathcal{K}_{\mathrm{policy}}\). The axiological check does not receive \(\mathcal{P}(\hat{y} \mid x)\). Confidence never overrides a deny. This is a gating design. It does not prove alignment. Auditability means the decision records the policy snapshot identifier and the gate results. Cryptographic signing is future work.

The model may integrate evidence with graded confidence. Commitment to an entity, an authorized transition, or a non-compensatory constraint is a separate decision procedure. Tagging a passage with a MOEPA layer does not implement that procedure. A schema check, a graph lookup, and a policy evaluation can. MOEPA and Marr answer different questions. This prospectus does not cross them into one model.

## Chapters

| Chapter | File |
|---|---|
| 1. Introduction and the Organizational Design Impasse | [thesis-chapter-1-organizational-design.md](thesis-chapter-1-organizational-design.md) |
| 2. Theoretical Foundations | [thesis-chapter-2-marr-moepa.md](thesis-chapter-2-marr-moepa.md) |
| 3. The MOEPA Dual-Domain Cognitive Framework | [thesis-chapter-3-dual-domain.md](thesis-chapter-3-dual-domain.md) |
| 4. Unified Data Substrate and Specialized Compute Projections | [thesis-chapter-4-substrate.md](thesis-chapter-4-substrate.md) |
| 5. Reference Implementation and System Orchestration | [thesis-chapter-5-reference-implementation.md](thesis-chapter-5-reference-implementation.md) |
| 6. Empirical Evaluation and Validation | [thesis-chapter-6-evaluation.md](thesis-chapter-6-evaluation.md) |
| 7. Systems Governance, Sovereign Infrastructure, and Deployment Patterns | [thesis-chapter-7-governance.md](thesis-chapter-7-governance.md) |
| 8. Conclusion and Future Research Directions | [thesis-chapter-8-conclusion.md](thesis-chapter-8-conclusion.md) |
