# Chapter 7. Systems Governance, Sovereign Infrastructure, and Deployment Patterns

Working chapter. The argument, the eight-chapter outline, and the commitment function remain in [draft/thesis.md](../draft/thesis.md). This file develops outline §§7.1–7.3. It does not replace the prospectus. Where this chapter and the prospectus differ, the prospectus governs.

Sovereignty contrasts in this chapter name architectural patterns: a lakehouse export of rows, a vendor runtime, a commercial policy API. They do not name a vendor.

## 7.1 Sovereignty of Cognitive History, and Owned versus Rented Gates

Possession of raw tables is not data sovereignty. Sovereignty is the ability to recover, on infrastructure the organization controls, the epistemic claims, the lineage of each admitted assertion, and the praxeological and axiological rules that governed commitment.

MOEPA records in an open Iceberg ledger provide that recovery: the triple and its four envelopes in one row, in an open serialization the organization’s own context defines. A bare row export fails that test. It moves the ontological record’s extension and abandons its warrant. The recipient inherits entities without the epistemic claims under which they were proposed, without the envelopes under which they were admitted, and without the refinement rules that authorized the transition. Strategy must then be rewritten in the next program that reads the files.

A monolithic platform whose ontology and action rules are recoverable only inside a vendor runtime also fails the test. It can preserve a cognitive history that the customer cannot replay on an open stack. It keeps the steering wheel inside the platform. Delegating the policy gate to a commercial API provider is the same failure at deployment time.

Hosting the epistemic engine is a deployment choice. The admission checks and the rules they read remain outside that engine. Replay cites the snapshot identifier and the bundle hash stored with the records and the versioned rules. The policy engine evaluates the exported bundle and does not consult a vendor procedure for the rule.

The reference implementation makes the owned-versus-rented line a packaging rule. The ledger, the policy baseline, the gate, and the gateway are owned units. The graph store, the vector index, and the model host are units that can be swapped. A swap is proven by the unit’s own check and by the projection rebuild passing with no other unit restarted. That proof is a contract check. It is not a Chapter 6 result.

## 7.2 Air-Gapped and High-Assurance Implementations

The deployment pattern for isolated infrastructure is a self-hosted model, a local vector index, and a self-hosted policy engine evaluating an exported bundle. A particular cloud partition is an example, not a theoretical requirement. No cloud product is a theoretical requirement of the architecture.

The pattern does not change the commitment function. The model still proposes. The three checks still admit or refuse against one snapshot. Isolation changes where the engines run. It does not move the strategy back into the sampler.

## 7.3 Regulatory and Standards Alignment

The gating design is to be mapped to the NIST AI Risk Management Framework (AI RMF), to ISO/IEC 42001, and to federal AI safety directives. Mapping is not certification. This chapter does not perform the mapping, and it does not claim conformance to any of the three.

What the mapping has to preserve, when it is written, is the separation this prospectus already fixes. Graded confidence stays on the proposal. Non-compensatory constraints stay in the exported bundle. A decision records the policy snapshot identifier and the gate results. The gating design does not prove alignment.
