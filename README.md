# MOEPA Thesis

Working repository for the thesis draft.

The architecture specification stays in
[moepa-cognitive-architecture](https://github.com/PhilipAsiala/moepa-cognitive-architecture).
The running stack stays in [moepa](https://github.com/PhilipAsiala/moepa).
This repository holds the thesis argument. It does not replace the architecture docs or the stack.

| Repo | Role |
|---|---|
| [moepa-cognitive-architecture](https://github.com/PhilipAsiala/moepa-cognitive-architecture) | Reference architecture: the technical specification (`catalog/ARCHITECTURE.md`) and the enterprise capability catalog (`DS1`–`DS8`, `AG1`–`AG8`) |
| [moepa-profile](https://github.com/PhilipAsiala/moepa-profile) | Normative shape of the MOEPA record: JSON-LD 1.1 context, vocabulary, SHACL shapes (formerly `spop-profile`) |
| [moepa](https://github.com/PhilipAsiala/moepa) | Runnable stack built to that catalog, one deployable unit per capability, with a check per unit |
| **This repo** | Thesis draft |

The four repositories are cloned side by side:

```
~/source/thesis/
  moepa-cognitive-architecture/   specification and catalog
  moepa-profile/                  the record: context, vocabulary, shapes
  moepa/                          running stack
  moepa-thesis/                   this repo
```

`moepa` replaces the earlier `philosophical-ai-lab`. The lab was a scaffold of intended labs, one per layer, that were never filled in. The stack is the implementation: a lakehouse system of record, rebuildable graph and vector projections, a policy engine, and one policy-enforcing gateway, running on the host **nitro** and verified by per-capability checks. `moepa-cognitive-architecture` is the renamed `philosophical-ai-architecture`; the old name redirects. `moepa-profile` is the renamed `spop-profile`: the record moved from N-Quads to JSON-LD, and the profile moved with it.

## Status

This repository is the public remote. `main` holds the working draft.

The working draft is [draft/thesis.md](draft/thesis.md): the ledger stores the business logic and the runtime implements it; an epistemic proposal is then admitted only by three checks. The file also holds the eight-chapter outline, the commitment function, and the three-phase plan. Benchmarks in that file are proposed, not reported. Where the draft describes the substrate, the gateway, or the reference implementation, it describes the specification at v3.1 and the stack as built; nothing the stack's checks prove is reported as a thesis result.

The Chapter 2 draft is [docs/thesis-chapter-2-marr-moepa.md](docs/thesis-chapter-2-marr-moepa.md). It develops outline §§2.1–2.4 and defers to `draft/thesis.md` where the two differ. `draft/thesis.md` remains the source of the argument.

## Layout

```
draft/thesis.md                         working draft
docs/thesis-chapter-2-marr-moepa.md     Chapter 2 draft (defers to draft/thesis.md)
AGENTS.md                               how agents should treat this repo
```
