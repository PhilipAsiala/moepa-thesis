# Chapter 5. Reference Implementation and System Orchestration

Working chapter. The argument, the eight-chapter outline, and the commitment function remain in [draft/thesis.md](../draft/thesis.md). This file develops outline §§5.1–5.3. It does not replace the prospectus. Where this chapter and the prospectus differ, the prospectus governs.

The reference implementation is the [moepa-lab](https://github.com/PhilipAsiala/moepa-lab) stack, built to the enterprise capability catalog of the specification. It replaces the earlier `philosophical-ai-lab` scaffold. Each catalog capability (`DS1`–`DS8`, `AG1`–`AG8`) is one deployable unit with a declared contract and its own check, so the engine behind a projection, the gateway, or the model proxy can be replaced without touching the ledger or the gates (specification §5.2, “Capabilities deploy as units”). The checks prove the contracts hold. They are not the benchmarks of Chapter 6.

## 5.1 Schema Firewall

Epistemic fields — confidence, model id, \(p\)-value — do not appear as columns on the entity table. They stay on the proposal and on the decision record. In the record of §4.1 they stay in the Epistemology and Metrology envelopes and are never written into the ontological triple.

The same firewall withholds confidence from the action rule. A threshold that authorizes or blocks is policy, stored with the bundle, or it is not a rule of the architecture.

## 5.2 The Sequential Enforcement Pipeline

**Enforcement point.** One policy-enforcing gateway (`AG7`; Envoy with external authorization in the reference implementation) fronts every model and tool endpoint. It holds the request while an authorizer loads the governing record, asks the policy engine, and writes the decision to the ledger. Only an allow is routed upstream. A denied request is an HTTP refusal the model process never sees. Any model or tool reachable by a path that skips the gateway is a side door, and the specification scores it as an automatic NO-GO unless covered by a dated, recorded exception.

**Candidate generation.** A foundation model, hosted or self-hosted, produces the epistemic proposal. It is reached only through the gateway and a model translation proxy (`AG8`) that makes the model a replaceable host. A hosted service is an example epistemic engine, not part of the architecture. The reference implementation has one such proxy.

**Ontological verification.** Referenced entities and relations are checked in the graph synced from the snapshot.

**Praxeological gating.** Preconditions and allowable transitions are evaluated with OPA Rego against the exported bundle. The check returns pass or fail.

**Axiological gate.** Non-compensatory constraints in the exported bundle are evaluated with OPA Rego. The specification places the caller’s clearance in the identity registry (`DS8`) as a stored fact, not a header the caller asserts. The reference implementation does not yet include that registry. Clearance still arrives as a header. The record’s classification marking is the Axiology envelope the rule reads. The check does not receive the proposal’s confidence. Rego is the encoding of the business rule for that snapshot. The surrounding service is the interpreter. A confidence cutoff, if leadership has adopted one, appears as a clause in the bundle, versioned with the snapshot identifier, and is still not an input that can override a separate deny.

## 5.3 Handling Rejection and Fallbacks

Refusal names the first failed gate, in the order Chapter 3 fixes: \(\Omega\), then \(\Pi\), then \(\Lambda\). A later gate is not consulted after an earlier failure. The refusal is written to the decision ledger with the policy hash, as an allow is.

Safe refusal states, feedback for re-prompting or re-sampling, and human-in-the-loop escalation are the handling this section requires. The prospectus names them. It does not report them as a completed study.
