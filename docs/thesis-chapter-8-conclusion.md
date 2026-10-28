# Chapter 8. Conclusion and Future Research Directions

Working chapter. The argument, the eight-chapter outline, and the commitment function remain in [draft/thesis.md](../draft/thesis.md). This file develops outline §§8.1–8.3. It does not replace the prospectus. Where this chapter and the prospectus differ, the prospectus governs.

## 8.1 Summary of the Claim

A model proposes. It does not commit.

AI safety here is treated as an engineering gating problem in addition to training-time alignment. The gate is also where strategy is stored as policy data and executed by the runtime, after the epistemic claim has been refused entry into the ontological record. The ledger holds the rules. The runtime evaluates the exported bundle. Leadership amends strategy by snapshot rather than by patching inference code.

The gating design does not replace alignment work, and it does not prove alignment. \(\Omega\), \(\Pi\), and \(\Lambda\) are deterministic given the gold snapshot they read. They are not a proof that the snapshot is correct or complete. Confidence is not an input to the axiological check, and it never overrides a deny.

## 8.2 Extensions to Multi-Agent Swarms

Applying the same proposal-and-admission split to distributed agent networks is future work. This prospectus does not specify a swarm, a protocol among agents, or a result about one. The split it would carry is the one Chapter 3 already states: each agent proposes, and commitment remains the three checks against one snapshot.

## 8.3 Open Research Questions

Four questions are open. None is answered here.

- Automated synthesis of candidate encodings of the policy-encoded hard gate, for human review and promotion. A model may draft the encoding. Chapter 3 already withholds promotion from the model.
- Checking generated Rego against the statute it came from.
- Hardware-accelerated policy evaluation.
- Signing of snapshot-linked decision records. Chapter 4 records that the Iceberg snapshot id is specified for the decision and is not yet written. Signing waits on that record, and on a specification of the signature. Auditability, until then, means the decision records the policy snapshot identifier and the gate results.
