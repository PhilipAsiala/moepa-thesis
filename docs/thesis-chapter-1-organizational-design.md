# Chapter 1. Introduction and the Organizational Design Impasse

Working chapter. The argument, the eight-chapter outline, and the commitment function remain in [draft/thesis.md](../draft/thesis.md). This file develops outline §§1.1–1.3. It does not replace the prospectus. Where this chapter and the prospectus differ, the prospectus governs.

The abstract and the central thesis statement are in [thesis-front-matter.md](thesis-front-matter.md). This chapter states the problem those pages name, and the contributions the later chapters have to make good.

## 1.1 The Organizational Design Impasse

The enterprise alignment problem, on this account, is the displacement of strategy into black-box code. Engineers write business rules as branches, thresholds, and guard clauses. A hosted model’s token probability is then read as warrant for the same commitment. The organization cannot inspect, version, or amend the rule except by changing the program. Leadership has lost the steering wheel to the codebase.

Prompt engineering, reinforcement learning from human feedback, and layer tags in the prompt do not install an admission check. Scope note, an author observation and not a completed experiment: layer tags in the prompt were tried and did not enforce constraints, because the model treated the tags as additional tokens. A second author observation, not a completed study: production services commonly encode a confidence cutoff, illustratively a block below \(0.85\), as application logic. That cutoff is policy wearing the syntax of a program. The threshold is invisible to the leadership that owns the constraint, unauditable as policy, and fused with the epistemic state that occasioned it.

MOEPA reverses the inversion. The ledger stores the business logic. The runtime implements it. If leadership adopts a threshold, the threshold is a versioned clause in \(\mathcal{K}_{\mathrm{policy}}\). It is not a literal in the service that calls the model.

## 1.2 The Dual-Nature Category Error

Implementation noise does not force the goal, or the rule used at the algorithmic level, to be a probability calculus. Stochastic signal processing is a fact about realization. Legal, operational, and ethical admission rules are a separate decision procedure, stored as policy and interpreted by the runtime. Governance is not a Marr level. Chapter 2 states Marr’s three levels and does not add a fourth.

Writing a machine-learning probability onto an entity record is a further category mistake, developed in §2.3. The probability is an epistemic state about a claim. The ontological record is a discrete identifier plus the relations asserted of it. A statement such as \(P(\text{entity } E \text{ exists}) = 0.4\), stored as the entity’s existence, places a degree of credence in the category reserved for the individual. Uncertainty stays attached to the claim. It is not a property of instantiation.

The same mistake appears one step later, at the point of action. A confidence cutoff compiled into a service stores the organization’s permission as a literal in the caller. Chapter 2 calls the remedy a schema firewall. This chapter only fixes the error the firewall is there to refuse.

## 1.3 Architectural Scope and Contributions

The prospectus claims four contributions. Later chapters carry them. None of them is a proof of alignment, and none of them is a proof that the snapshot is correct or complete.

- Formalization of the MOEPA cognitive stack as a gating design in which the ledger holds the rules and the technology implements them. Chapter 3 states the two domains and the commitment function.
- The operational separation of an epistemic claim from an ontological entity record, so that uncertainty is never stored as a property of instantiation. Chapter 2 states the category mistake. Chapter 3 keeps graded confidence on the proposal.
- Praxeological and axiological constraints as a versioned policy bundle, evaluated outside the model, so that leadership amends strategy by snapshot rather than by patching inference code. Chapter 3 states the checks. Chapter 5 states the pipeline that runs them.
- An Iceberg ledger of MOEPA records, JSON-LD against an owned context, and of refinement rules, with a vector index, a graph database, and a policy engine fed by snapshot sync or export. Sovereignty is retention of that cognitive history, not possession of a row export. Chapter 4 states the substrate. Chapter 7 states what counts as sovereignty.

Chapter 6 proposes an evaluation of the gating design. The benchmarks there have not been run. The checks of the reference implementation are contract checks. They are not those benchmarks.
