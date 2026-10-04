# Chapter 2 — Theoretical Foundations: The Marr × MOEPA Matrix

Working chapter for the prospectus. The argument, the eight-chapter outline, and the commitment function remain in [draft/thesis.md](../draft/thesis.md). This file develops outline §§2.1 and 2.4 together with the dual-domain partition that Chapter 3 will formalize. It cites the MOEPA Cognitive Architecture specification; it does not replace that specification.

Specification cited: Philip Asiala, *Philosophical AI Architecture — Technical Specification* (MOEPA Cognitive Architecture, v2.4, 2 October 2026), §§1.3–1.4 and the layer definitions in §2, in [philosophical-ai-architecture](https://github.com/PhilipAsiala/philosophical-ai-architecture) `ARCHITECTURE.md`. Marr’s tri-level hypothesis is the analysis already named in the outline at §2.1 (David Marr, *Vision*, 1982). Related-work sections on neuro-symbolic systems and epistemic logic (outline §§2.2–2.3) are not written here.

## 2.1 The Category Error in Modern AI

The central thesis holds that the reliability, alignment, and hallucination failures of autonomous learning systems arise from a category error: state representation and normative commitment are treated as if they were probability distributions. The error is visible once cognition is described at more than one level of analysis, and once those levels are crossed with the five MOEPA domains.

### Marr’s three levels

Marr’s tri-level hypothesis separates an information-processing system into three questions that must not be collapsed into one another.

1. **Computational level.** What is the goal of the computation, and what is the logic by which that goal is achieved? This level states the function to be computed: the mapping from inputs, and from the constraints that define success, to an admissible output.
2. **Algorithmic level.** What representations does the system use, and what rules transform those representations? This level states how the computational function is carried out: the data structures and the procedure.
3. **Implementational level.** How are the representation and the algorithm realized in a physical substrate? This level states the hardware, the runtime, and the storage medium.

A complete account of a cognitive faculty names all three. An account that answers only the third, and then reads that answer back onto the first, has changed the subject. Noise in a transistor, a weight, or a sampling step is a fact about realization. It does not decide what the computation is for.

### The LLM fallacy

Foundation-model practice commits that change of subject. Because the implementation — neural networks executed on GPUs — is stochastic and noisy, the computational goals of the system are treated as if they, too, must be probabilistic. Sampling, next-token likelihood, and reinforcement learning from human feedback are then asked to carry functions whose success condition is not a likelihood at all: whether a named entity exists, whether a transition is feasible, and whether a statute permits the act.

The outline names this the dual-nature category error: the implementation level (noisy signal processing) is conflated with the governance level (discrete legal, operational, and ethical rules). Under that conflation, a high token probability is received as warrant for a commitment. The architecture specification states the contrary control rule. A language model may propose. It may not commit. The external result of the guardrail is binary.

### Where current systems are actually strong

Crossing Marr’s three levels with the five MOEPA domains yields fifteen facets. Contemporary large language models are highly developed in two of them: **Epistemology at the algorithmic level** (high-dimensional latent vectors, stochastic token sampling, approximate Bayesian updating) and **Epistemology at the implementational level** (foundation models on GPU clusters, and a vector index such as Qdrant). Those two facets are the right instruments for integrating noisy evidence and proposing candidate actions.

The same instruments fail when they are stretched into Ontology or Axiology. Those domains require deterministic rule engines: discrete schemas and graph assertions for what exists, and non-compensatory Boolean policy for what may be done. A sampler has no native representation of either engine. Prompting it to “respect the ontology” or “follow policy” leaves both the representation and the rule inside the same stochastic procedure that the computational goal was supposed to constrain. The remaining thirteen facets are then either vacant or simulated inside the two epistemic cells.

## 2.2 Probabilistic and Deterministic as Domain Properties

“Probabilistic” and “deterministic” are not properties of the cognitive stack as a whole. They are algorithmic properties fixed by what each MOEPA domain must compute. The architecture specification marks the same cut with the labels “Quantum” (statistical inference) and “Newtonian” (discrete governance). Those labels name the character of the computation. They are not a claim about physical quantum mechanics.

The mind is probabilistic in handling evidence, and non-probabilistic in its commitments.

### Probabilistic domain

Metrology and Epistemology compute over continuous quantities and incomplete evidence. Their native state is a distribution, an interval, or an explicitly unwarranted claim.

- **Metrology** quantifies observational noise: telemetry, calibration, confidence, and error bounds such as expected calibration error, $\mathbb{E}[|P - Y|]$. A measurement may be uncertain. That uncertainty belongs to the observation.
- **Epistemology** integrates noisy evidence, infers latent causes, and proposes candidate actions. Its algorithmic objects are latent vectors, stochastic samples, and approximate belief updates. The specification requires three distinct epistemic states, which a single distribution does not supply: **Belief** (a partial claim with a confidence and a justification), **Defeater** (a reason the claim cannot stand), and **Ignorance** (no warranted claim). Ignorance is an explicit $\bot$, distinct from a uniform prior. A defeater is not a lower probability of the same claim.

This domain may measure, score, calibrate, and propose. It may not commit an entity, authorize an action, or emit a permission.

### Deterministic domain

Ontology, Praxeology, and Axiology compute over discrete facts, admissible transitions, and non-compensatory norms. Their native state is a categorical assertion or a Boolean gate, $C \in \{0, 1\}$.

- **Ontology** defines ground truth: which discrete entities and relations exist. A triple is written or it is not. A statement such as $P(\text{entity } E \text{ exists}) = 0.4$ corrupts the state model, because uncertainty has been written onto the entity rather than onto the epistemic claim.
- **Praxeology** enforces operational feasibility: valid state transitions, preconditions, and execution bounds. Viability is a discrete precondition, not a confidence band.
- **Axiology** enforces statutory mandates, safety invariants, and core values. Normative commitment is non-compensatory. A high confidence does not compensate for a violated invariant. At runtime the gate is Boolean. The specification further distinguishes the meaning of a failure inside the audit record: **Forbid** when the act is in the action space and violates a value or a rule, and **Refuse to Act** when the proposal is Ignorance or carries an unresolved defeater. **Commit** is the only verdict that authorizes a write or an external effect. The external result remains binary: committed, or blocked.

This domain may commit categorical state, admit or reject a transition, and issue a final verdict. It does not store uncertainty on an entity, and it does not turn a probability into a permission.

## 2.3 The Fifteen-Facet Matrix

Each cell is one Marr level applied to one MOEPA domain. The native domain state selects the kind of goal, the kind of representation, and the kind of substrate that cell may use. The matrix below follows the dual-domain grouping (probabilistic domains, then deterministic domains). The architecture numbers the layers bottom-up as Metrology, Ontology, Epistemology, Praxeology, Axiology; that numbering is the stack order, not a second matrix.

| MOEPA layer | Native domain state | 1. Computational level (goal and logic) | 2. Algorithmic level (representations and rules) | 3. Implementational level (substrate and hardware) |
| :--- | :--- | :--- | :--- | :--- |
| **Metrology** | **Probabilistic** | Quantify confidence, telemetry, calibration, and observational noise. | Continuous probability distributions, confidence intervals, error estimators. | Direct SQL / Trino over Iceberg metadata and telemetry logs. |
| **Epistemology** | **Probabilistic** | Integrate noisy evidence, infer latent causes, propose candidate actions. | High-dimensional latent vectors, stochastic token sampling, approximate Bayesian updating. | Amazon Bedrock / foundation models on GPU clusters; Qdrant vector index. |
| **Ontology** | **Deterministic** | Define ground truth: what discrete entities and relations exist. | Discrete schemas, RDF triples, relational graph assertions. | Graph database virtualized over Apache Iceberg. |
| **Praxeology** | **Deterministic** | Enforce valid state transitions, preconditions, and execution bounds. | Discrete state-machine logic, precondition/postcondition assertion trees. | Open Policy Agent (OPA) evaluating state payloads. |
| **Axiology** | **Deterministic** | Enforce non-negotiable statutory mandates, safety invariants, and core values. | Deterministic Boolean logic ($C \in \{0, 1\}$); non-compensatory policy-as-code. | In-memory OPA Rego bundles mounted from immutable Iceberg S3 snapshots. |

Read across a row, the three Marr levels stay inside one domain state. Metrology’s implementational cell is an analytical query over telemetry, not a permission. Epistemology’s implementational cell samples a proposal, not a commit. Ontology’s algorithmic cell asserts a triple, not a confidence. Praxeology’s algorithmic cell admits a transition, not a score. Axiology’s algorithmic cell returns a Boolean, not a utility.

Read down a column, the same Marr question receives different answers because the domains do not share a permission type. The computational column contains both “propose a candidate” and “enforce an invariant.” Those are different functions. Implementing both of them as next-token prediction is the category error of §2.1, localized to two cells and then generalized to fifteen.

On the deterministic side the execution engines are mounts over one ledger, not a second memory. Apache Iceberg on object storage is the versioned, append-only record. Ontology is a graph projection of those tables. Praxeology and Axiology are separate Rego packages in one OPA bundle synchronized from the same tables. Every decision links to a snapshot identifier. That substrate claim is specified in the architecture and scheduled for Chapter 4; it is assumed here so that the implementational column denotes an owned ledger rather than a vendor’s private state.

## 2.4 The State Collapse Mechanism

State collapse is the handoff that carries a continuous epistemic proposal into a discrete system commitment. It is a change of domain, not a further sample. The outline’s commitment function is the formal statement; the four steps below are the operational reading of that function. Numeric confidence is retained on the audit record. It is not an input to Ontology, Praxeology, or Axiology.

### The epistemic proposal

Let $\mathcal{E}$ be the epistemic state generated over an input $x \in \mathcal{X}$:

$$
\mathcal{E}(x) = \langle \hat{y},\ \mathcal{P}(\hat{y} \mid x),\ \mathcal{M},\ \tau \rangle
$$

$\hat{y}$ is the proposed candidate. $\mathcal{P}(\hat{y} \mid x)$ is the graded confidence. $\mathcal{M}$ is the metrological metadata, including calibration error and token log-probabilities. $\tau$ is the provenance trace, including retrieval context and snapshot identifiers.

### Step 1 — The language model as uncommitted advisor

The epistemic layer emits $\mathcal{E}(x)$ and stops. The candidate contains the proposed action, the confidence, and the evidence trace. It is not a system action. Belief, Defeater, and Ignorance remain distinct: Ignorance is not rewritten as a low probability, and a defeater is not smoothed into the same distribution. A provider adapter’s work ends when it has built this uncommitted candidate.

### Step 2 — The schema firewall

A rigid schema keeps probabilistic fields off the ontological record. Confidence, model identifier, and $p$-value may appear in the epistemic envelope and in the audit metadata. They may not appear as a column, a predicate, or an existence condition on an entity table. The firewall is what makes $P(\text{entity } E \text{ exists}) = 0.4$ unrepresentable in the state model. Uncertainty stays on the claim.

### Step 3 — Deterministic arbitration

Three operators then evaluate the discrete candidate. Each returns a value in $\{0, 1\}$, and none of them reads $\mathcal{P}(\hat{y} \mid x)$.

**Ontological validator.**

$$
\Omega(\hat{y}, \mathcal{G}_{\text{Iceberg}}) \in \{0, 1\}
$$

$\Omega$ asserts that every entity, relationship, and identity referenced in $\hat{y}$ is a grounded node in the knowledge graph $\mathcal{G}$. A missing entity is a hallucination at this gate.

**Praxeological validator.**

$$
\Pi(\hat{y}, \mathcal{S}_{\text{current}}, \mathcal{R}_{\text{physics}}) \in \{0, 1\}
$$

$\Pi$ asserts that the transition from the current state $\mathcal{S}_{\text{current}}$ by the action $\hat{y}$ satisfies the operational preconditions and the transition rules $\mathcal{R}_{\text{physics}}$.

**Axiological arbiter.**

$$
\Lambda(\hat{y}, \mathcal{C}_{\text{statute}}, \mathcal{K}_{\text{policy}}) \in \{0, 1\}
$$

$\Lambda$ asserts that $\hat{y}$ satisfies the invariants, ethical constraints, and statutory restrictions encoded in the active policy snapshot $\mathcal{K}_{\text{policy}}$. The assertion is independent of $\mathcal{P}(\hat{y} \mid x)$. In the architecture’s audit vocabulary, a zero at this gate is recorded either as Forbid or as Refuse to Act. Both are blocks.

### Step 4 — Collapse

The commitment $\mathcal{A}_{\text{commit}}$ is non-probabilistic:

$$
\mathcal{A}_{\text{commit}} =
\begin{cases}
\text{Commit}(\hat{y}), & \text{if } \Omega(\hat{y}) \land \Pi(\hat{y}) \land \Lambda(\hat{y}) = 1 \\
\text{Refuse}(\text{reason}), & \text{if } \Omega(\hat{y}) \land \Pi(\hat{y}) \land \Lambda(\hat{y}) = 0
\end{cases}
$$

If every deterministic gate returns $1$, the continuous proposal collapses into one discrete system commitment: the write, and the Iceberg snapshot metadata that records it. If any gate returns $0$, the proposal is blocked. In particular, $\mathcal{P}(\hat{y} \mid x) \to 1$ does not license execution when $\Lambda(\hat{y}) = 0$. A high-confidence hallucination that fails Ontology, and a high-confidence violation that fails Axiology, are both neutralized at the gate rather than averaged into the proposal.

Collapse is therefore the point at which fifteen facets become one control path. The two epistemic facets in which language models excel remain intact: they still integrate evidence and still propose. The ontological and axiological facets remain deterministic rule engines. Alignment, on this account, is the engineering of that handoff.
