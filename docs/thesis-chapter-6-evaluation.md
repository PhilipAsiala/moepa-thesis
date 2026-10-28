# Chapter 6. Empirical Evaluation and Validation

Working chapter. The argument, the eight-chapter outline, and the commitment function remain in [draft/thesis.md](../draft/thesis.md). This file develops outline §§6.1–6.4. It does not replace the prospectus. Where this chapter and the prospectus differ, the prospectus governs.

The benchmarks in this chapter are proposed. None has been run for this prospectus. A passing check in the reference implementation is a contract check. It is not a result reported here.

## 6.1 Proposed Benchmark 1 — High-Confidence Boundary Violations

The scenario is one in which a model assigns high confidence, including \(0.99\) and above, to a hallucinated or non-compliant candidate. The expected observation is refusal at the first failed gate, in the order \(\Omega\), then \(\Pi\), then \(\Lambda\).

This is a test to design, not a result. The development plan runs these failure-injection tests through the gateway, so that a refusal is recorded in `moepa.decisions`. Until that run exists, this section states the expected observation and reports nothing observed.

## 6.2 Proposed Benchmark 2 — Enterprise and Public Sector Workflows

Three workflows are proposed. None has been executed for this prospectus.

- Statutory benefits eligibility determination.
- Income verification and programmatic audits.
- Separation of a claim about a person from that person’s entity record.

The third item is the category distinction of §2.3, exercised as a workflow: the claim stays on the proposal, and the entity record stays a discrete identifier plus the relations asserted of it.

## 6.3 Proposed Measurement — Latency

Compare evaluation of an exported OPA bundle with foundation-model sampling, hosted or self-hosted, on the `moepa-lab` stack. Latency is a measurement to make. This draft reports no latency figure, and it does not assume one in advance.

## 6.4 Proposed Check — Snapshot-linked Replay

Replay a recorded decision against the stored Iceberg snapshot id and bundle version under a simulated review. Chapter 4 records that the snapshot id is specified for the decision record and is not yet written by the reference implementation. Signing is out of scope until it is specified.

The per-capability checks under `deploy/capabilities/*/check.sh`, and the unit tests under `src/assembly/tests/`, are the contract checks from which these benchmarks are to be built. Gateway refusal that never reaches the model proxy, a policy hash matching the loaded bundle, and a projection rebuild from the ledger are examples of those checks. Chapter 6 is assembled from benchmark results after the benchmarks have been run. It is not assembled from the checks themselves.
