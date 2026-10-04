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

Uncertainty attaches to a claim about an entity, not as an existence probability on the entity record. A statement such as \(P(\text{entity } E \text{ exists}) = 0.4\) corrupts the record if it is stored as the entity’s existence. The entity table holds discrete identifiers and the relations asserted in the snapshot. Epistemic fields — confidence, model id, \(p\)-value — stay on the proposal and on the decision record. They do not appear as columns on the entity table.

The ontological check reads the graph synced from the snapshot under a closed-world convention: a referenced entity or relation is grounded in that graph, or it is not. Open-world identity and temporal validity can remain uncertain, but they remain claims. They are not written back as fuzzy existence on the record. The check does not prove that the snapshot is the right closed world. It proves only that the candidate is grounded in the snapshot it was given.

Epistemology is not only a probability. The graded part of a proposal is a confidence on a candidate, with metrological metadata such as calibration error. The proposal may also carry defaults, defeaters, source pointers, and an explicit unknown. Unknown is distinct from a uniform prior. A uniform prior manufactures a distribution where the system has no warrant. A defeater is a reason a claim does not stand, not a lower probability of the same claim. None of these is a permission.

## 2.4 Non-Compensatory Constraints

This section does not prove that axiology is binary. Values include tradeoffs. A tradeoff is not a pass/fail gate, and this architecture does not force it into one.

The hard gate is the subset of constraints that are non-compensatory and that have been encoded as policy: a statutory prohibition, a safety interlock. For that subset the check returns pass or fail. A high confidence does not compensate for a failed check. \(\Lambda\) does not take \(\mathcal{P}(\hat{y} \mid x)\) as an input. Constraints that have not been encoded are outside the gate. Encoding is a human decision about the snapshot. The gate does not discover the statute, and it does not certify that the encoding is complete.

Praxeology is the same kind of check at a different question. It asks whether the transition from the current state by the candidate meets the preconditions and lies in the allowable transitions. Graded measurements may be inputs. The result is pass or fail. It is not a physics. The rule set is the exported bundle, not a live query of the ledger.

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
