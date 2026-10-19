# MOEPA Thesis — agent notes

Thesis draft companion to
[`moepa-cognitive-architecture`](../moepa-cognitive-architecture/) (specification and catalog)
and [`moepa`](../moepa/) (the running stack).
Theory and the catalog stay in the first. What has been built and verified stays in the second.
The argument of the thesis lives here.

The three repositories sit side by side in `~/source/thesis/`. Open Cursor on that
folder to work across them. `moepa` replaces the retired `philosophical-ai-lab`;
`moepa-cognitive-architecture` is the renamed `philosophical-ai-architecture`.

## Role

- Hold the thesis draft and later revisions.
- Cite the architecture repo for the specification and the catalog. Do not copy the leader guides into the thesis.
- Cite the stack repo for what runs: capability units, checks, and the decision ledger as implemented. Do not report a passing check as a thesis result; Chapter 6 benchmarks are proposed until run.
- Treat [draft/thesis.md](draft/thesis.md) as the author's text. Do not invent chapters, claims, or citations.

## Working rules

1. [draft/thesis.md](draft/thesis.md) is the source of truth for the argument.
2. Keep the architecture repo, the stack repo, and this repo distinct. Where the thesis describes the architecture, it describes `catalog/ARCHITECTURE.md` at the version it cites; where the two disagree on the argument, the thesis governs.
3. No secrets in the tree.
4. Sovereignty contrasts name architectural patterns (a lakehouse export of rows, a vendor runtime). Do not name Databricks or Palantir.
