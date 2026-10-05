# Chapter 2. Theoretical Foundations

Working chapter for the prospectus. The argument, the eight-chapter outline, and the commitment function remain in [draft/thesis.md](../draft/thesis.md). This file develops outline §§2.1–2.4. It does not replace the prospectus, and it does not cross Marr’s levels with the MOEPA domains into one model.

Specification cited for layer names only: Philip Asiala, *Philosophical AI Architecture — Technical Specification* (MOEPA Cognitive Architecture, v2.4, 2 October 2026), in [philosophical-ai-architecture](https://github.com/PhilipAsiala/philosophical-ai-architecture) `ARCHITECTURE.md`. Where that specification and this prospectus disagree, this prospectus governs. In particular, this chapter does not use “quantum” or “Newtonian” as domain labels, does not treat a Marr-by-MOEPA grid as a model of cognition, and does not call the handoff a state collapse.

## 2.1 Marr’s Tri-Level Hypothesis Revisited

David Marr argued that an information-processing system is understood only when three questions are answered separately (*Vision*, 1982).

1. **Computational level.** What is the goal of the computation, why is it appropriate, and what is the logic of the strategy by which it can be carried out?
2. **Algorithmic and representational level.** What representations are used for the input and the output, and what algorithm transforms one into the other?
3. **Implementational level.** How are that representation and that algorithm realized physically?

The personal level is not one of Marr’s levels. It was a later way of talking about explicit reasoning. This prospectus does not add it to the triad.

The claim these levels support is narrow. Noise at the implementational level does not force the computational goal, or the rule used at the algorithmic level, to be a probability calculus. A deterministic procedure can run on noisy hardware. A probabilistic procedure can be approximated by deterministic circuits. Governance is not a fourth Marr level. Legal, operational, and ethical admission rules are a separate decision procedure. They may be analyzed at all three of Marr’s levels, but that analysis does not make them a level.

Revisits to cite when this section is expanded, without page quotations in this draft: McClamrock, “Marr’s three levels: A re-evaluation” (1991), which separates grain of description from contextual function; the 2015 *Topics in Cognitive Science* issue introduced by Peebles, including Love on the algorithmic level as the site of integration and Hardcastle and Stewart on failure modes; Pillow (2024) as the opposing view, that the triad is a poor partition of neuroscience and overweights the computational level. Those sources are not used here as authority for a combined Marr–MOEPA model. MOEPA and Marr answer different questions. Marr asks how a process is explained. MOEPA names the kinds of knowledge and admission the system must keep apart.

The error this architecture is aimed at is the reading of an implementational fact back onto the goal. Because a foundation model is a sampler, a high token probability is treated as warrant for a committed fact, entity, or permission. Prompting does not supply that warrant. Layer tags in the prompt were tried and did not enforce constraints, because the model treated the tags as additional tokens. That is an author observation, not a completed experiment.

## 2.2 Neuro-Symbolic AI Architectures

The relevant history is the split between symbolic systems and connectionist systems, not a claim that one side has solved constraint enforcement.

Symbolic systems can state discrete entities, preconditions, and non-compensatory rules, and they can refuse when a rule fails. They are brittle when the input is incomplete, noisy, or not already in the symbol vocabulary. Connectionist and deep models can integrate that kind of evidence and propose a candidate. They do not, by the form of next-token prediction, guarantee that a named entity is grounded, that a transition is allowed, or that a statutory prohibition is respected. Reinforcement learning from human feedback changes the sampling distribution. It does not install an admission check that confidence cannot override.

Neuro-symbolic work tries to keep both. The usual failure mode is to put the symbolic constraint back inside the same procedure that proposes: a tag, a prompt, a fine-tune, or a classifier score. The prospectus takes a narrower route. The model remains an uncommitted advisor. Grounding, preconditions, and the policy-encoded hard gate are separate checks. A hosted or self-hosted foundation model is an example epistemic engine, not part of the architecture. A vendor classifier or guardrail, if used, is an optional pre-filter on the proposal. It is not the axiological check.

## 2.3 Epistemic Claim and Ontological Record

Inscribing a probability emitted by a learning procedure directly upon an entity record is a category mistake. The probability is an epistemic state: the system’s uncertainty about a proposition, graded by the warrant it can presently cite. Instantiation, in the ontological record, is the presence of a discrete identifier and of the relations asserted of that identifier in a snapshot. A statement such as \(P(\text{entity } E \text{ exists}) = 0.4\) is a confidence on a claim. Stored as the entity’s existence, it places that confidence in the category reserved for the individual, and the identifier then denotes a degree of credence. The entity table therefore holds discrete identifiers and the relations asserted in the snapshot. Epistemic fields — confidence, model id, \(p\)-value — remain on the proposal and on the decision record. They are excluded from the entity table as columns, predicates, and existence conditions.

That separation is the architecture’s enforcement of epistemic humility. Humility here is a constraint on what may be written. The graded part of a proposal is a confidence on a candidate, accompanied by metrological metadata such as calibration error. The proposal may also carry defaults, defeaters, source pointers, and an explicit unknown. An explicit unknown records the absence of a warrant. A uniform prior manufactures a distribution in that same absence, and the two remain distinct. A defeater is a reason the claim does not stand: a separate proposition, distinct from a reduced probability assigned to the original claim. Confidence, default, defeater, source, and unknown stay on the claim. None of them is a permission, and none of them is transcribed onto the entity as a property of its instantiation.

The same mistake appears one layer up, at the point of action. A confidence score copied onto an entity column corrupts the ontological record. A confidence cutoff compiled into a service corrupts the axiological record: the organization’s permission is stored as a literal in the epistemic engine’s caller. Epistemic humility is enforced in both places by the schema firewall. The entity table admits discrete identifiers and the relations asserted in the snapshot. The policy bundle admits the non-compensatory constraints leadership has encoded. Neither artifact accepts \(\mathcal{P}(\hat{y} \mid x)\) as a column, a predicate, or an existence condition. A defeater remains a separate proposition on the claim. It is not a reduced probability written back onto the individual, and it is not a hidden branch in the sampler.

Data sovereignty requires that the system preserve this cognitive history together with the rows it has admitted. A bare export of Parquet files can transmit the extensional rows while leaving behind the epistemology of their assertion and the praxeological rules by which a candidate was refined and admitted. Without that lineage and those rules, the rows no longer bear the warrant on which their validity as committed records depends. MOEPA writes the history into an open serialization. An ontological assertion is recorded as an N-Quad: a subject–predicate–object triple extended by a graph name, the fourth component, which identifies the context in which the triple is instantiated. That named graph is the provenance locus of the assertion — the snapshot, the source, and the decision under which it was admitted. The quads and the versioned refinement rules are stored in Apache Iceberg. Cognitive history is then a property of the open ledger, and the logic of admission is recoverable from the record rather than held only inside a vendor procedure.

Exporting the extensional rows — the ordinary lakehouse handoff that writes Parquet and drops the quads, the epistemic claims, and the refinement rules — moves the ontological record’s extension and abandons its warrant. The recipient inherits entities without the epistemic claims under which they were proposed, without the named graph in which they were admitted, and without the refinement rules that authorized the transition. Strategy must then be rewritten in the next program that reads the files. That is sovereignty over bytes, and a second inscription of the anti-pattern.

The contrasting failure is vendor logic lock-in. A monolithic platform in which the ontology and the action rules are recoverable only inside the vendor runtime can preserve a cognitive history that the customer cannot replay on an open stack. MOEPA refuses both failures. Replay cites the snapshot identifier and the bundle version already stored with the quads and the versioned rules. The policy engine evaluates the exported bundle and does not consult a vendor procedure for the rule.

Because the architecture is open and vendor-agnostic, the world beyond a given snapshot is not a closed domain the check may assume. The ontological check therefore enforces a strict closed-world convention against one frozen snapshot. It reads the graph synced from that snapshot: a referenced entity or relation is grounded in the graph, or it is not. Open-world identity and temporal validity may remain uncertain, but they remain claims, and they are withheld from the entity record. The check does not prove that the snapshot is the right closed world. It proves only that the candidate is grounded in the snapshot it was given. The frozen boundary keeps open-world probabilistic noise from being admitted as an instantiation.

## 2.4 Non-Compensatory Constraints

This section does not prove that axiology is binary. Values include tradeoffs. A tradeoff is not a pass/fail gate, and this architecture does not force it into one.

The hard gate is the subset of constraints that are non-compensatory and that have been encoded as policy: a statutory prohibition, a safety interlock. For that subset the check returns pass or fail. A high confidence does not compensate for a failed check. \(\Lambda\) does not take \(\mathcal{P}(\hat{y} \mid x)\) as an input. Constraints that have not been encoded are outside the gate. Encoding is a human decision about the snapshot. The gate does not discover the statute, and it does not certify that the encoding is complete.

Praxeology is the same kind of check at a different question. It asks whether the transition from the current state by the candidate meets the preconditions and lies in the allowable transitions. Graded measurements may be inputs. The result is pass or fail. It is not a physics. The rule set is the exported bundle, not a live query of the ledger.

Both checks are how the architecture keeps strategy out of the probabilistic procedure. A praxeological precondition such as “income verified” may consume a graded measurement. The definition of verification is \(\mathcal{R}_{\mathrm{pre}}\) in the exported bundle. An axiological interlock such as “this statutory class of payment is prohibited” is \(\mathcal{K}_{\mathrm{policy}}\). Neither definition is recovered by inspecting the model weights or the service that called the model. The handoff is admission of a candidate under a named policy snapshot. Tradeoff values that leadership has not encoded remain outside the gate. The gate does not invent them, and a high confidence does not compensate for their absence or for a failed check.

## 2.5 What This Chapter Does Not Claim

The handoff is admission, not collapse. The model emits an uncommitted candidate. Three checks run in order: ontological grounding, praxeological preconditions, axiological non-compensatory constraints. Commit only if all three pass. Otherwise refuse, and record the first failed gate. The formula is the commitment function in the prospectus, §3. It is repeated here so this chapter cannot drift from it.

\[
\mathcal{A}_{\mathrm{commit}} =
\begin{cases}
\mathrm{Commit}(\hat{y}) & \text{if } \Omega = 1 \land \Pi = 1 \land \Lambda = 1 \\
\mathrm{Refuse}(\mathrm{reason}) & \text{otherwise}
\end{cases}
\]

\(\mathrm{reason}\) is the first failed gate, in order \(\Omega\), then \(\Pi\), then \(\Lambda\). A later gate is not consulted after an earlier failure. \(\Omega\), \(\Pi\), and \(\Lambda\) are deterministic given the snapshot they read. They are not a proof that the snapshot is correct or complete, and they are not a proof of alignment.

Iceberg is the ledger. The vector index, the graph, and the policy engine are projections or syncs from a snapshot. The policy engine evaluates an exported bundle. It does not query the ledger at decision time. A decision stores the snapshot id, the bundle version, and the gate results. Signing is future work. No cloud product is a theoretical requirement.

Chapter 3 states the domains in full: Metrology and the graded part of Epistemology on the proposal side; ontology, praxeology, and the policy-encoded hard gate on the admission side. This chapter only fixes the distinctions those sections are not allowed to blur.
