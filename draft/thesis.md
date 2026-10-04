# A Dual-Domain Cognitive Architecture for Enterprise AI Governance: Decoupling Probabilistic Epistemic Inference from Deterministic Axiological Arbitration

Working draft. Claim correction of the prospectus received 2026-10-03.

## 1. Central Thesis Statement

Reliability failures of LLM agents include treating a graded proposal as a committed fact, entity, or permission. The proposed architecture separates an epistemic proposal (candidate output, confidence, evidence pointers, explicit unknown) from three deterministic admission checks: ontological grounding, praxeological preconditions, and axiological non-compensatory constraints. Commit only if all three pass. This is a gating design. It does not prove alignment. Auditability means the decision records the policy snapshot id and the gate results, not cryptographic provenance unless signing is later specified.

The model may integrate evidence with graded confidence. Commitment to an entity, an authorized transition, or a non-compensatory constraint is a separate decision procedure. Tagging a passage with a MOEPA layer does not implement that procedure. A schema check, a graph lookup, and a policy evaluation can. Confidence never overrides a deny.

MOEPA and Marr answer different questions. This prospectus does not cross them into one model.

## 2. Dissertation Structure and Chapter Outline

### Chapter 1: Introduction and the Problem of Unconstrained Inference

1.1 **The Enterprise Alignment and Reliability Impasse.** Why prompt engineering, reinforcement learning from human feedback (RLHF), and raw token-probabilistic systems can hallucinate or violate constraints, and prompting does not supply a guarantee.

Scope note, author observation, not a completed experiment: layer tags in the prompt were tried and did not enforce constraints, because the model treated the tags as additional tokens.

1.2 **The Dual-Nature Category Error.** Implementation noise does not force the goal or the rule layer to be a probability calculus. Stochastic signal processing is a fact about realization. Legal, operational, and ethical admission rules are a separate decision procedure. Governance is not a Marr level.

1.3 **Architectural Scope and Contributions.**

- Formalization of the MOEPA (Metrology, Ontology, Epistemology, Praxeology, Axiology) cognitive stack as a gating design.
- The operational separation of an epistemic claim from an ontological entity record.
- An Iceberg ledger, with a vector index, a graph database, and a policy engine fed by snapshot sync or export rather than by a live query at decision time.

### Chapter 2: Theoretical Foundations and Related Work

2.1 **Marr’s Tri-Level Hypothesis Revisited.** Marr’s levels are computational, algorithmic/representational, and implementational (Marr, *Vision*, 1982). The personal level is not Marr’s. Physical noise at the implementational level does not imply that the computational goal, or the rule used at the algorithmic level, must be a probability calculus. Revisits to cite later, without page quotations: McClamrock 1991; *Topics in Cognitive Science* 2015 (Peebles; Love; Hardcastle and Stewart); Pillow 2024 as the opposing view.

2.2 **Neuro-Symbolic AI Architectures.** Historical divide between symbolic logic systems (brittle under real-world noise) and connectionist/deep models (incapable of absolute constraint enforcement).

2.3 **Epistemic Logic vs. Ontological Realism.** A schema firewall: uncertainty attaches to a claim about an entity, not as an existence probability on the entity record. A statement such as $P(\text{entity } E \text{ exists}) = 0.4$ corrupts the entity record if it is stored as the entity’s existence. The firewall assumes a closed world for the records it checks. Open-world identity and temporal validity can remain uncertain as claims.

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

3.3 **The Commitment Function.** Commit the candidate only when ontological grounding, praxeological preconditions, and the axiological hard gate all pass. Otherwise refuse, and record which gate failed. The formula is stated in §3 below.

### Chapter 4: Unified Data Substrate and Specialized Compute Projections

4.1 **The Ledger.** Apache Iceberg is the versioned, append-only ledger of record. Snapshot history supports replay. Object storage is the medium; no particular cloud vendor is a theoretical requirement.

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
- **Axiological gate:** Non-compensatory constraints encoded in that same bundle are evaluated with OPA Rego. The check does not receive the proposal’s confidence.

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

7.1 **Owned vs. Rented AI Paradigms.** The strategic risk of delegating the organization’s policy gate to a commercial API provider. Hosting the epistemic engine is a deployment choice. The admission checks remain outside that engine.

7.2 **Air-Gapped and High-Assurance Implementations.** Deployment patterns for isolated infrastructure, including self-hosted models, a local vector index, and a self-hosted policy engine evaluating an exported bundle. A particular cloud partition is an example, not a theoretical requirement.

7.3 **Regulatory and Standards Alignment.** Mapping the gating design to the NIST AI Risk Management Framework (AI RMF), ISO/IEC 42001, and federal AI safety directives. Mapping is not certification.

### Chapter 8: Conclusion and Future Research Directions

8.1 **Summary of the Claim.** AI safety here is treated as an engineering gating problem in addition to training-time alignment. The gating design does not replace alignment work, and it does not prove alignment.

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

$\mathcal{K}_{\mathrm{policy}}$ is the policy-encoded subset of non-compensatory constraints (statutory prohibition, safety interlock) in the exported bundle. $\Lambda = 1$ when $\hat{y}$ satisfies that subset. $\Lambda$ does not take $\mathcal{P}(\hat{y} \mid x)$ as an input. Tradeoff values are not part of $\mathcal{K}_{\mathrm{policy}}$.

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
