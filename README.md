# MOEPA Thesis

Working repository for the thesis draft.

The architecture specification stays in
[moepa-cognitive-architecture](https://github.com/PhilipAsiala/moepa-cognitive-architecture).
The running stack stays in [moepa-lab](https://github.com/PhilipAsiala/moepa-lab).
This repository holds the thesis argument. It does not replace the architecture docs or the stack.

| Repo | Role |
|---|---|
| [moepa-cognitive-architecture](https://github.com/PhilipAsiala/moepa-cognitive-architecture) | Reference architecture: the technical specification (`catalog/ARCHITECTURE.md`) and the enterprise capability catalog (`DS1`–`DS8`, `AG1`–`AG8`) |
| [moepa-profile](https://github.com/PhilipAsiala/moepa-profile) | Normative shape of the MOEPA record: JSON-LD 1.1 context, vocabulary, SHACL shapes (formerly `spop-profile`) |
| [moepa-lab](https://github.com/PhilipAsiala/moepa-lab) | Runnable stack built to that catalog, one deployable unit per capability, with a check per unit |
| **This repo** | Thesis draft |

The four repositories are cloned side by side:

```
~/source/thesis/
  moepa-cognitive-architecture/   specification and catalog
  moepa-profile/                  the record: context, vocabulary, shapes
  moepa-lab/                      running stack
  moepa-thesis/                   this repo
```

`moepa-lab` replaces the earlier `philosophical-ai-lab`. The lab was a scaffold of intended labs, one per layer, that were never filled in. The stack is the implementation: a lakehouse system of record, rebuildable graph and vector projections, a policy engine, and one policy-enforcing gateway, running on the host **nitro** and verified by per-capability checks. `moepa-cognitive-architecture` is the renamed `philosophical-ai-architecture`; the old name redirects. `moepa-profile` is the renamed `spop-profile`: the record moved from N-Quads to JSON-LD, and the profile moved with it.

## Status

This repository is the public remote. `main` holds the working draft.

The working draft is [draft/thesis.md](draft/thesis.md): the ledger stores the business logic and the runtime implements it; an epistemic proposal is then admitted only by three checks. The file also holds the eight-chapter outline, the commitment function, and the three-phase plan. Benchmarks in that file are proposed, not reported. Where the draft describes the substrate, the gateway, or the reference implementation, it describes the specification at v3.1 and the stack as built; nothing the stack's checks prove is reported as a thesis result.

Chapter drafts developed from that file are in [docs/](docs/). [docs/thesis-front-matter.md](docs/thesis-front-matter.md) holds the abstract and the central thesis statement and links the eight chapters. Each chapter develops its outline section and defers to `draft/thesis.md` where the two differ. `draft/thesis.md` remains the source of the argument. The development plan stays in the draft.

## Layout

```
draft/thesis.md                                         working draft (source of the argument)
docs/thesis-front-matter.md                             abstract, central thesis, chapter index
docs/thesis-chapter-1-organizational-design.md          Chapter 1
docs/thesis-chapter-2-marr-moepa.md                     Chapter 2
docs/thesis-chapter-3-dual-domain.md                    Chapter 3, including the commitment function
docs/thesis-chapter-4-substrate.md                      Chapter 4
docs/thesis-chapter-5-reference-implementation.md       Chapter 5
docs/thesis-chapter-6-evaluation.md                     Chapter 6 (benchmarks proposed, not run)
docs/thesis-chapter-7-governance.md                     Chapter 7
docs/thesis-chapter-8-conclusion.md                     Chapter 8
AGENTS.md                                               how agents should treat this repo
```
