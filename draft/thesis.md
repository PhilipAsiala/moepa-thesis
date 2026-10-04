# A Dual-Domain Cognitive Architecture for Enterprise AI Governance: Decoupling Probabilistic Epistemic Inference from Deterministic Axiological Arbitration

Working draft. Claim correction of the prospectus received 2026-10-03. Organizational-design hook added 2026-10-04: the ledger stores the business logic; the runtime implements it.

## Abstract

Enterprise AI fails first as organizational design. Eligibility rules, safety interlocks, and the thresholds that authorize or block a transaction are written into application code and into the sampling procedure. An engineer who blocks a transaction whenever a model’s confidence falls below \(0.85\) has inscribed a strategic decision in an implementation artifact. The threshold is then invisible to the leadership that owns the constraint, unauditable as policy, and fused with the epistemic state that occasioned it. Prompt engineering, reinforcement learning from human feedback, and raw token probability do not restore the separation.

This prospectus proposes MOEPA (Metrology, Ontology, Epistemology, Praxeology, Axiology) as the architecture that reverses that anti-pattern. The ledger stores the business logic. The technology implements it. A foundation model remains an uncommitted advisor: its output is an epistemic proposal, a tuple of candidate, graded confidence, metrological metadata, evidence pointers, defeaters, and an explicit unknown. Commitment is a separate decision procedure. The candidate is admitted only when three deterministic checks pass against one snapshot: ontological grounding in discrete identifiers, praxeological preconditions and allowable transitions, and axiological non-compensatory constraints encoded as policy. Confidence is not an input to the axiological check, and it never overrides a deny. Inscribing a probability on an entity record is a category mistake. Uncertainty stays attached to the claim.

A decision is auditable when it records the policy snapshot identifier and the gate results. Data sovereignty, on this account, is retention of that cognitive history — lineage, refinement rules, and epistemic claims — in an open serialization (N-Quads in Apache Iceberg). A bare export of extensional rows does not preserve it. The gating design does not prove alignment, and it does not prove that the snapshot is correct or complete.

## 1. Central Thesis Statement

The prevailing failure of enterprise AI is an inversion of authority. Business strategy is implemented as control flow: a confidence cutoff, an eligibility branch, a block-or-allow literal in service code. The organization then cannot inspect, version, or amend the rule except by changing the program. Leadership has lost the steering wheel to the codebase.

MOEPA reverses the inversion. An epistemic proposal carries a graded confidence and does not commit a fact, an entity, or a permission. Three deterministic admission checks follow, in order: ontological grounding, praxeological preconditions, and axiological non-compensatory constraints. Commit only if all three pass. The rules those checks apply are stored in the ledger and exported as a policy bundle. The runtime evaluates the bundle. It does not contain the strategy.

A numeric threshold is the same inversion in miniature. A procedure that blocks a transaction when \(\mathcal{P}(\hat{y} \mid x) < 0.85\) treats an epistemic state as an axiological permission and locates the permission in source code. If leadership adopts a threshold, the threshold is a versioned clause in \(\mathcal{K}_{\mathrm{policy}}\). The axiological check does not receive \(\mathcal{P}(\hat{y} \mid x)\). Confidence never overrides a deny. This is a gating design. It does not prove alignment. Auditability means the decision records the policy snapshot identifier and the gate results. Cryptographic signing is future work.

The model may integrate evidence with graded confidence. Commitment to an entity, an authorized transition, or a non-compensatory constraint is a separate decision procedure. Tagging a passage with a MOEPA layer does not implement that procedure. A schema check, a graph lookup, and a policy evaluation can. MOEPA and Marr answer different questions. This prospectus does not cross them into one model.

## 2. Dissertation Structure and Chapter Outline

### Chapter 1: Introduction and the Organizational Design Impasse

1.1 **The Organizational Design Impasse.** The enterprise alignment problem is the displacement of strategy into black-box code. Engineers write business rules as branches, thresholds, and guard clauses. A hosted model’s token probability is then read as warrant for the same commitment. Prompt engineering, reinforcement learning from human feedback, and layer tags in the prompt do not install an admission check. Scope note, author observation, not a completed experiment: layer tags in the prompt were tried and did not enforce constraints, because the model treated the tags as additional tokens. A second author observation, not a completed study: production services commonly encode a confidence cutoff (illustratively, block below \(0.85\)) as application logic. That cutoff is policy wearing the syntax of a program.

1.2 **The Dual-Nature Category Error.** Implementation noise does not force the goal or the rule layer to be a probability calculus. Stochastic signal processing is a fact about realization. Legal, operational, and ethical admission rules are a separate decision procedure, stored as policy and interpreted by the runtime. Governance is not a Marr level. Writing a machine-learning probability onto an entity record is a further category mistake, developed in §2.3: the probability is an epistemic state about a claim, and the ontological record is a discrete identifier plus the relations asserted of it.

1.3 **Architectural Scope and Contributions.**

- Formalization of the MOEPA (Metrology, Ontology, Epistemology, Praxeology, Axiology) cognitive stack as a gating design in which the ledger holds the rules and the technology implements them.
- The operational separation of an epistemic claim from an ontological entity record, so that uncertainty is never stored as a property of instantiation.
- Praxeological and axiological constraints as a versioned policy bundle, evaluated outside the model, so that leadership amends strategy by snapshot rather than by patching inference code.
- An Iceberg ledger of N-Quads and refinement rules, with a vector index, a graph database, and a policy engine fed by snapshot sync or export. Sovereignty is retention of that cognitive history, not possession of a row export.

### Chapter 2: Theoretical Foundations and Related Work

2.1 **Marr’s Tri-Level Hypothesis Revisited.** Marr’s levels are computational, algorithmic/representational, and implementational (Marr, *Vision*, 1982). The personal level is not Marr’s. Physical noise at the implementational level does not imply that the computational goal, or the rule used at the algorithmic level, must be a probability calculus. Revisits to cite later, without page quotations: McClamrock 1991; *Topics in Cognitive Science* 2015 (Peebles; Love; Hardcastle and Stewart); Pillow 2024 as the opposing view.

2.2 **Neuro-Symbolic AI Architectures.** Historical divide between symbolic logic systems (brittle under real-world noise) and connectionist/deep models (incapable of absolute constraint enforcement).

2.3 **Epistemic Logic vs. Ontological Realism.** A schema firewall: uncertainty attaches to a claim about an entity, not as an existence probability on the entity record. Inscribing \(P(\text{entity } E \text{ exists}) = 0.4\) as the entity’s existence is a category mistake. The identifier would then denote a degree of credence. The firewall assumes a closed world for the records it checks. Open-world identity and temporal validity remain claims. The same firewall withholds confidence from the action rule: a threshold that authorizes or blocks is policy, stored with the bundle, or it is not a rule of the architecture.

2.4 **Non-Compensatory Constraints.** This section does not prove that axiology is binary. Non-compensatory constraints (statutory prohibition, safety interlock) are boolean. Other values are tradeoffs and stay outside the hard gate. The hard gate is the subset encoded as policy.

### Chapter 3: The MOEPA Dual-Domain Cognitive Framework

3.1 **The Probabilistic Domain ("Continuous Evidence Integration").** This domain is Metrology and the graded part of Epistemology only.

- **Metrology:** Telemetry, confidence scoring, uncertainty calibration, calibration error bounds ($\mathbb{E}[|P - Y|]$), and empirical disagreement tracking.
- **Epistemology, graded part:** Evidence integration and a graded confidence on a candidate output. The model remains an uncommitted advisor.
- **Epistemology, beyond graded confidence:** Defaults, defeaters, source tracking, and an explicit unknown state, distinct from a uniform prior. These are part of the proposal. They are not a permission.

3.2 **The Deterministic Domain ("Discrete Admission").**

- **Ontology:** Ground-truth schemas, discrete identifiers, and RDF subject-predicate-object assertions checked against the snapshot’s graph.
- **Praxeology:** Preconditions and allowable transitions. Inputs to those checks may be graded. The check itself returns pass or fail.
- **Axiology:** The hard gate. Non-compensatory constraints encoded as policy. Tradeoff values are outside this gate.

Ontology answers what is instantiated. Praxeology answers which transitions the current state permits. Axiology answers which outcomes are forbidden regardless of benefit. All three answers are data. Preconditions, allowable transitions, and non-compensatory constraints are rows and rules in the snapshot, exported into the bundle the engine evaluates. Graded measurements may be inputs to a praxeological check; the check still returns pass or fail, and the criterion of passage is the rule, not the model’s confidence. The axiological check does not receive confidence at all. Amending a prohibition is a new snapshot. It is not a change to the sampler and not a patch to the service that merely invokes the engine. That is the return of the steering wheel: leadership edits \(\mathcal{R}_{\mathrm{pre}}\) and \(\mathcal{K}_{\mathrm{policy}}\); engineers maintain the interpreter.

3.3 **The Commitment Function.** Commit the candidate only when ontological grounding, praxeological preconditions, and the axiological hard gate all pass. Otherwise refuse, and record which gate failed. The formula is stated in §3 below.

### Chapter 4: Unified Data Substrate and Specialized Compute Projections

4.1 **The Ledger.** Apache Iceberg is the versioned, append-only ledger of record. It stores ontological assertions as N-Quads and stores the refinement rules that praxeology and axiology evaluate. Snapshot history supports replay of both the admitted world and the policy under which it was admitted. Object storage is the medium. No particular cloud vendor is a theoretical requirement. A Parquet export of rows without quads and without the bundle is not the ledger.

4.2 **Projections and Snapshot Syncs.** Qdrant, the graph database, and OPA are projections or syncs from snapshots. They are not live mounts, unless a virtualization path is later implemented and named.

- **Metrology:** Analytical SQL over Iceberg tables for drift and calibration monitoring.
- **Epistemic projection:** A vector index (Qdrant) synced from a snapshot, holding latent embeddings.
- **Ontological projection:** A graph database loaded from a snapshot, used for entity-relationship checks.
- **Praxeological and axiological projection:** Rules exported from a snapshot into an OPA bundle. OPA evaluates that exported bundle. It does not query Iceberg at decision time.

4.3 **Snapshot-linked Replay.** A decision stores the Iceberg snapshot id and the bundle version, together with the gate results. Signing is future work.

### Chapter 5: Reference Implementation (`moepa_guard`) and System Orchestration

5.1 **Schema Firewall.** Epistemic fields (confidence, model id, $p$-value) do not appear as columns on the entity table. They stay on the proposal and on the decision record.

5.2 **The Sequential Enforcement Pipeline.**

- **Candidate generation:** A foundation model, hosted or self-hosted, produces the epistemic proposal. A hosted service is an example epistemic engine, not part of the architecture.
- **Ontological verification:** Referenced entities and relations are checked in the graph synced from the snapshot.
- **Praxeological gating:** Preconditions and allowable transitions are evaluated with OPA Rego against the exported bundle. The check returns pass or fail.
- **Axiological gate:** Non-compensatory constraints in the exported bundle are evaluated with OPA Rego. The check does not receive the proposal’s confidence. Rego is the encoding of the business rule for that snapshot. The surrounding service is the interpreter. A confidence cutoff, if leadership has adopted one, appears as a clause in the bundle, versioned with the snapshot identifier, and is still not an input that can override a separate deny.

5.3 **Handling Rejection and Fallbacks.** Safe refusal states, feedback for re-prompting or re-sampling, and human-in-the-loop escalation. Refusal names the first failed gate.

### Chapter 6: Empirical Evaluation and Validation

The benchmarks in this chapter are proposed. None has been run for this prospectus.

6.1 **Proposed Benchmark 1 — High-Confidence Boundary Violations.** Scenarios in which a model assigns high confidence (including $0.99$ and above) to a hallucinated or non-compliant candidate. The expected observation is refusal at the first failed gate. This is a test to design, not a result.

6.2 **Proposed Benchmark 2 — Enterprise and Public Sector Workflows.**

- Statutory benefits eligibility determination.
- Income verification and programmatic audits.
- Separation of a taxpayer claim from a taxpayer entity record.

6.3 **Proposed Measurement — Latency.** Compare evaluation of an exported OPA bundle with foundation-model sampling. Latency is a measurement to make. This draft reports no latency figure.

6.4 **Proposed Check — Snapshot-linked Replay.** Replay a recorded decision against the stored Iceberg snapshot id and bundle version under a simulated review. Signing is out of scope until it is specified.

### Chapter 7: Systems Governance, Sovereign Infrastructure, and Deployment Patterns

7.1 **Sovereignty of Cognitive History, and Owned vs. Rented Gates.** Possession of raw tables is not data sovereignty. Sovereignty is the ability to recover, on infrastructure the organization controls, the epistemic claims, the lineage of each admitted assertion, and the praxeological and axiological rules that governed commitment. N-Quads in an open Iceberg ledger provide that recovery. A bare row export, and a monolithic platform whose ontology and action rules are recoverable only inside a vendor runtime, both fail that test: the first abandons the warrant, and the second keeps the steering wheel inside the platform. Delegating the policy gate to a commercial API provider is the same failure at deployment time. Hosting the epistemic engine is a deployment choice. The admission checks and the rules they read remain outside that engine.

7.2 **Air-Gapped and High-Assurance Implementations.** Deployment patterns for isolated infrastructure, including self-hosted models, a local vector index, and a self-hosted policy engine evaluating an exported bundle. A particular cloud partition is an example, not a theoretical requirement.

7.3 **Regulatory and Standards Alignment.** Mapping the gating design to the NIST AI Risk Management Framework (AI RMF), ISO/IEC 42001, and federal AI safety directives. Mapping is not certification.

### Chapter 8: Conclusion and Future Research Directions

8.1 **Summary of the Claim.** AI safety here is treated as an engineering gating problem in addition to training-time alignment. The gate is also where strategy is stored as policy data and executed by the runtime, after the epistemic claim has been refused entry into the ontological record. The gating design does not replace alignment work, and it does not prove alignment.

8.2 **Extensions to Multi-Agent Swarms.** Applying the same proposal-and-admission split to distributed agent networks. This is future work.

8.3 **Open Research Questions.** Automated synthesis of the policy-encoded hard gate, checking generated Rego against the statute it came from, hardware-accelerated policy evaluation, and signing of snapshot-linked decision records.

## 3. Mathematical and Logical Formulation for Chapter 3

The commitment function for the gating design is stated here so the outline and the formula match. It is not a proof of alignment, and it is not a proof that the snapshot is correct or complete.

### Epistemic Proposal

Let $\mathcal{E}$ represent the epistemic state generated by the model over input $x \in \mathcal{X}$:

```math
\mathcal{E}(x) = \langle \hat{y}, \mathcal{P}(\hat{y} \mid x), \mathcal{M}, \tau \rangle
```

Where:

- $\hat{y}$ is the proposed candidate output or action.
- $\mathcal{P}(\hat{y} \mid x)$ is the graded confidence on that candidate.
- $\mathcal{M}$ is metrological metadata (calibration error, token log-probabilities, and related uncertainty on the observation).
- $\tau$ holds evidence pointers (retrieval context) and identifies the snapshot the proposal was conditioned on.

An explicit unknown is part of the proposal and is distinct from a uniform prior. It is not an extra factor in $\mathcal{P}(\hat{y} \mid x)$.

### Admission Checks

Three checks run in order. Each returns pass or fail. Inputs to a check may be graded. The check result is boolean. Confidence never overrides a deny.

**Ontological check ($\Omega$):**

```math
\Omega(\hat{y}, \mathcal{G}) \in \{0, 1\}
```

$\mathcal{G}$ is the graph synced from the snapshot under review. $\Omega = 1$ when every entity and relation referenced in $\hat{y}$ is grounded in that graph. The check uses a closed-world reading of $\mathcal{G}$. It does not convert an open-world or temporal uncertainty into an existence probability on the entity record.

**Praxeological check ($\Pi$):**

```math
\Pi(\hat{y}, \mathcal{S}_{\mathrm{current}}, \mathcal{R}_{\mathrm{pre}}) \in \{0, 1\}
```

$\Pi = 1$ when the transition from the current state $\mathcal{S}_{\mathrm{current}}$ by $\hat{y}$ meets the preconditions and lies in the allowable transitions $\mathcal{R}_{\mathrm{pre}}$. Graded measurements may be among the inputs. The result is pass or fail.

**Axiological check ($\Lambda$):**

```math
\Lambda(\hat{y}, \mathcal{K}_{\mathrm{policy}}) \in \{0, 1\}
```

$\mathcal{K}_{\mathrm{policy}}$ is the policy-encoded subset of non-compensatory constraints (statutory prohibition, safety interlock) in the exported bundle. $\Lambda = 1$ when $\hat{y}$ satisfies that subset. $\Lambda$ does not take $\mathcal{P}(\hat{y} \mid x)$ as an input. $\mathcal{K}_{\mathrm{policy}}$ and $\mathcal{R}_{\mathrm{pre}}$ are artifacts of the snapshot. A threshold or a prohibition that exists only as a literal in application code is outside the commitment function, because no gate can record it. Tradeoff values are not part of $\mathcal{K}_{\mathrm{policy}}$.

### The Commitment Function

```math
\mathcal{A}_{\mathrm{commit}} =
\begin{cases}
\mathrm{Commit}(\hat{y}) & \text{if } \Omega = 1 \land \Pi = 1 \land \Lambda = 1 \\
\mathrm{Refuse}(\mathrm{reason}) & \text{otherwise}
\end{cases}
```

$\mathrm{reason}$ is the first failed gate, in order $\Omega$, then $\Pi$, then $\Lambda$. A later gate is not consulted after an earlier failure.

$\Omega$, $\Pi$, and $\Lambda$ are deterministic given the snapshot they read. They are not a proof that the snapshot is correct or complete.

## 4. Immediate Development Plan

### Phase 1: Formal Proposal and Chapter 1/2 Draft

- Formalize Chapter 1: Introduction and Problem Formulation
- Refine Chapter 2: Literature Review (Marr, including the revisits named in §2.1; neuro-symbolic systems; AI safety)
- Write Chapter 3 from the commitment function in §3, without treating the gates as a proof of snapshot correctness

### Phase 2: Empirical Validation and Test Data

- Extract test suites from `philosophical-ai-architecture` `reference/tests/`
- Measure latency of foundation-model sampling (hosted or self-hosted) against evaluation of an exported OPA bundle. Report the measurement; do not assume a figure in advance.
- Run the proposed failure-injection tests (high-confidence boundary violations)

### Phase 3: Substrate Architecture and Systems Writing

- Document the Iceberg snapshot schema and the bundle-export pipeline
- Detail graph and Qdrant sync from snapshots
- After the proposed benchmarks have been run, assemble Chapter 6 from those results
