# A Dual-Domain Cognitive Architecture for Enterprise AI Governance: Decoupling Probabilistic Epistemic Inference from Deterministic Axiological Arbitration

Working draft. Author text, received 2026-10-03.

## 1. Central Thesis Statement

The reliability, alignment, and hallucination failure modes of autonomous machine learning systems stem from a category error: treating state representation and normative commitment as probabilistic distributions. By partitioning cognition into a Probabilistic Epistemic Domain (managing continuous evidence weighting, similarity search, and latent hypothesis generation) and a Deterministic Axiological Domain (enforcing discrete ontological state, operational physics, and binary normative constraints), an artificial cognitive architecture can achieve provable policy enforcement and complete auditability without suppressing the generative reasoning capabilities of large language models.

## 2. Dissertation Structure and Chapter Outline

### Chapter 1: Introduction and the Problem of Unconstrained Inference

1.1 **The Enterprise Alignment and Reliability Impasse.** Why prompt engineering, reinforcement learning from human feedback (RLHF), and raw token-probabilistic systems inevitably hallucinate certainty or violate hard boundaries.

1.2 **The Dual-Nature Category Error.** Conflating the implementation level (noisy, stochastic signal processing) with the governance level (discrete legal, operational, and ethical rules).

1.3 **Architectural Scope and Contributions.**

- Formalization of the MOEPA (Metrology, Ontology, Epistemology, Praxeology, Axiology) cognitive stack.
- The mathematical and operational separation of epistemic belief from ontological existence.
- Implementation of an immutable data substrate projecting into specialized execution engines.

### Chapter 2: Theoretical Foundations and Related Work

2.1 **Marr’s Tri-Level Hypothesis Revisited.** Analyzing neural computation at implementation, algorithmic, and computational/personal levels; why physical noise does not imply that computation must be a pure probability calculus.

2.2 **Neuro-Symbolic AI Architectures.** Historical divide between symbolic logic systems (brittle under real-world noise) and connectionist/deep models (incapable of absolute constraint enforcement).

2.3 **Epistemic Logic vs. Ontological Realism.** Why a statement such as \(P(\text{entity } E \text{ exists}) = 0.4\) corrupts state models, and why uncertainty must attach strictly to the epistemic claim rather than the entity schema.

2.4 **Non-Probabilistic Axiology.** Proving that normative commitments, compliance baselines, and safety bounds are fundamentally non-compensatory and binary (\(C \in \{0, 1\}\)).

### Chapter 3: The MOEPA Dual-Domain Cognitive Framework

3.1 **The Probabilistic Domain ("Continuous Evidence Integration").**

- **Metrology:** Telemetry, confidence scoring, uncertainty calibration, calibration error bounds (\(\mathbb{E}[|P - Y|]\)), and empirical disagreement tracking.
- **Epistemology:** The LLM as an uncommitted advisor; handling partial beliefs, defaults, defeaters, and maintaining an explicit \(\bot\) ("I don't know") state distinct from a uniform prior distribution.

3.2 **The Deterministic Domain ("Discrete Systemic Commitment").**

- **Ontology:** Ground-truth schemas, discrete identifiers, and RDF Subject-Predicate-Object semantic assertions.
- **Praxeology:** The physics of action; state transition preconditions, resource availability, and allowable action spaces.
- **Axiology (The Final Arbiter):** Organizational mandates, statutory constraints, compliance policies, and ethical limits operating as hard invariants.

3.3 **The State Collapse Engine.** Computational formalization of the transition where continuous epistemic distributions collapse into discrete, auditable system commitments.

### Chapter 4: Unified Data Substrate and Specialized Compute Projections

4.1 **The Single Source of Truth.** Utilizing Apache Iceberg on object storage (S3) as the version-controlled, append-only, time-travel-enabled ledger of record.

4.2 **Specialized Engine Projections.**

- **Metrology Projection:** Direct analytical SQL (Trino/Athena) over Iceberg tables for continuous drift and calibration monitoring.
- **Epistemic Projection:** Vector index synchronization (Qdrant) representing latent embeddings and high-dimensional semantic spaces.
- **Ontological Projection:** Graph database virtualization (reading Iceberg tabular state into discrete knowledge graphs) for entity-relationship validation.
- **Praxeological and Axiological Projection:** Automated synchronization of rule tables into declarative Open Policy Agent (OPA) bundles compiled into high-speed in-memory evaluation environments.

4.3 **Provenance and Cryptographic Traceability.** Ensuring every decision links back to a specific, immutable Iceberg snapshot metadata ID.

### Chapter 5: Reference Implementation (`moepa_guard`) and System Orchestration

5.1 **Schema Firewalls.** Formal verification of schemas preventing epistemic fields (confidence, model_id, p_value) from leaking into ontological entity tables.

5.2 **The Sequential Enforcement Pipeline.**

- **Candidate Generation:** Probabilistic payload generated by the foundation model via Amazon Bedrock.
- **Ontological Verification:** Validating that all referenced entities exist in the knowledge graph.
- **Praxeological Gating:** Evaluating operational validity using OPA Rego rules.
- **Axiological Arbitration:** Evaluating compliance, statutory mandates, and safety constraints using OPA Rego policies.

5.3 **Handling Rejection and Fallbacks.** Safe refusal states, automated feedback loops for re-prompting/re-sampling, and human-in-the-loop escalation patterns.

### Chapter 6: Empirical Evaluation and Validation

6.1 **Benchmark 1 — High-Confidence Boundary Violations.** Demonstrating scenarios where LLMs output \(0.99+\) probability hallucinatory or non-compliant decisions, and verifying deterministic rejection by the Axiology Agent without latency degradation.

6.2 **Benchmark 2 — Enterprise and Public Sector Workflows.**

- Statutory benefits eligibility determination.
- Income verification and programmatic audits.
- Strict separation of "taxpayer claim" vs. "taxpayer entity record."

6.3 **Performance and Latency Overhead.** Quantifying the microsecond latency of in-memory OPA bundle evaluation versus the multi-second latency of foundation model sampling.

6.4 **Auditability and Compliance Metrics.** Verifying backward-replayability of decisions against historical Iceberg snapshots under simulated regulatory review.

### Chapter 7: Systems Governance, Sovereign Infrastructure, and Deployment Patterns

7.1 **Owned vs. Rented AI Paradigms.** The strategic risk of delegating organizational axiology to commercial API providers.

7.2 **Air-Gapped and High-Assurance Implementations.** Deploying the MOEPA stack on isolated infrastructure (e.g., AWS GovCloud / TCloud) using Amazon EKS, local vector indexes, and self-hosted policy engines.

7.3 **Regulatory and Standards Alignment.** Mapping the architecture to the NIST AI Risk Management Framework (AI RMF), ISO/IEC 42001, and federal AI safety directives.

### Chapter 8: Conclusion and Future Research Directions

8.1 **Summary of Findings.** Establishing that AI safety is fundamentally a systems engineering problem rather than an alignment-tuning problem.

8.2 **Extensions to Multi-Agent Swarms.** Applying MOEPA layers to distributed autonomous agent networks.

8.3 **Open Research Questions.** Automated axiological synthesis, formal verification of dynamic Rego generation from legal statutes, and hardware-accelerated policy evaluation.

## 3. Mathematical and Logical Formulation for Chapter 3

To establish theoretical rigor early in the dissertation draft, the boundary transitions can be formalized as follows.

### Epistemic Proposal Space

Let \(\mathcal{E}\) represent the epistemic state generated by the model over input \(x \in \mathcal{X}\):

\[
\mathcal{E}(x) = \langle \hat{y}, \mathcal{P}(\hat{y} \mid x), \mathcal{M}, \tau \rangle
\]

Where:

- \(\hat{y}\) is the proposed candidate output or action.
- \(\mathcal{P}(\hat{y} \mid x)\) is the probability distribution or graded confidence metric.
- \(\mathcal{M}\) represents the metrological metadata (epistemic uncertainty, calibration error, token log-probabilities).
- \(\tau\) is the provenance trace (retrieval context, snapshot IDs).

### Deterministic State Verification and Gatekeeping

Let the deterministic domain consist of three sequential verification operators.

**Ontological Validator (\(\Omega\)):**

\[
\Omega(\hat{y}, \mathcal{G}_{\text{Iceberg}}) \in \{0, 1\}
\]

Asserts whether all entities, relationships, and identities referenced in \(\hat{y}\) are valid, grounded nodes in the deterministic knowledge graph \(\mathcal{G}\).

**Praxeological Validator (\(\Pi\)):**

\[
\Pi(\hat{y}, \mathcal{S}_{\text{current}}, \mathcal{R}_{\text{physics}}) \in \{0, 1\}
\]

Asserts whether the state transition from current state \(\mathcal{S}_{\text{current}}\) via action \(\hat{y}\) satisfies operational preconditions and transition rules \(\mathcal{R}_{\text{physics}}\).

**Axiological Arbiter (\(\Lambda\)):**

\[
\Lambda(\hat{y}, \mathcal{C}_{\text{statute}}, \mathcal{K}_{\text{policy}}) \in \{0, 1\}
\]

Asserts whether \(\hat{y}\) violates any invariant, ethical constraint, or statutory restriction encoded in the active policy snapshot \(\mathcal{K}_{\text{policy}}\), independent of \(\mathcal{P}(\hat{y} \mid x)\).

### The Commitment Function (State Collapse)

The final system commitment \(\mathcal{A}_{\text{commit}}\) is strictly non-probabilistic:

\[
\mathcal{A}_{\text{commit}} =
\begin{cases}
\text{Commit}(\hat{y}), & \text{if } \Omega(\hat{y}) \land \Pi(\hat{y}) \land \Lambda(\hat{y}) = 1 \\
\text{Refuse}(\text{reason}), & \text{if } \Omega(\hat{y}) \land \Pi(\hat{y}) \land \Lambda(\hat{y}) = 0
\end{cases}
\]

Under this formulation, regardless of the value of \(\mathcal{P}(\hat{y} \mid x) \to 1.0\), if \(\Lambda(\hat{y}) = 0\), execution is blocked.

## 4. Immediate Development Plan

### Phase 1: Formal Proposal and Chapter 1/2 Draft

- Formalize Chapter 1: Introduction and Problem Formulation
- Refine Chapter 2: Literature Review (Marr, Neuro-symbolic systems, AI Safety)
- Produce Chapter 3: Theoretical MOEPA Specification with formal proofs

### Phase 2: Empirical Validation and Test Data

- Extract test suites from `philosophical-ai-architecture` `reference/tests/`
- Benchmark latency: Bedrock inference vs. OPA Rego evaluation
- Run failure-injection tests (forcing high-confidence boundary violations)

### Phase 3: Substrate Architecture and Systems Writing

- Document Iceberg metadata schema and bundle-export pipeline
- Detail GraphDB and Qdrant projection synchronization patterns
- Assemble Chapter 6 empirical findings into publication-ready graphs/tables
