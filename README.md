# MOEPA Thesis

Working repository for the thesis draft.

The architecture specification stays in
[philosophical-ai-architecture](https://github.com/PhilipAsiala/philosophical-ai-architecture).
This repository holds the thesis argument. It does not replace the architecture docs or the labs.

| Repo | Role |
|---|---|
| [philosophical-ai-architecture](https://github.com/PhilipAsiala/philosophical-ai-architecture) | Reference architecture |
| [philosophical-ai-lab](../philosophical-ai-lab/) | Runnable labs |
| **This repo** | Thesis draft |

## Status

Local git repository on `main`. No remote yet.

The working draft is [draft/thesis.md](draft/thesis.md): the ledger stores the business logic and the runtime implements it; an epistemic proposal is then admitted only by three checks. The file also holds the eight-chapter outline, the commitment function, and the three-phase plan. Benchmarks in that file are proposed, not reported.

The Chapter 2 draft is [docs/thesis-chapter-2-marr-moepa.md](docs/thesis-chapter-2-marr-moepa.md). It develops outline §§2.1–2.4 and defers to `draft/thesis.md` where the two differ. `draft/thesis.md` remains the source of the argument.

## Layout

```
draft/thesis.md                         working draft
docs/thesis-chapter-2-marr-moepa.md     Chapter 2 draft (defers to draft/thesis.md)
AGENTS.md                               how agents should treat this repo
```
