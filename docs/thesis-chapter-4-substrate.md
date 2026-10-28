# Chapter 4. Unified Data Substrate and Specialized Compute Projections

Working chapter. The argument, the eight-chapter outline, and the commitment function remain in [draft/thesis.md](../draft/thesis.md). This file develops outline §§4.1–4.3. It does not replace the prospectus. Where this chapter and the prospectus differ, the prospectus governs.

Specification cited for the record and the ledger: Philip Asiala, *The MOEPA Cognitive Architecture — Technical Specification* (v3.1), §§5.0 and 5.0.1, in [moepa-cognitive-architecture](https://github.com/PhilipAsiala/moepa-cognitive-architecture) `catalog/ARCHITECTURE.md`. The normative shape of the record is [moepa-profile](https://github.com/PhilipAsiala/moepa-profile).

## 4.1 The Ledger

Apache Iceberg, under an open table catalog, is the versioned, append-only ledger of record and the only system of record (specification §5.0.1). Object storage is the medium. No particular cloud vendor is a theoretical requirement.

The unit of storage is the MOEPA record (specification §5.0). It is the ontological triple plus one envelope for each of the other four layers, on the same row, serialized as JSON-LD against an organization-owned context.

- **Epistemology:** generating agent, generation time, and the SHA-256 fingerprint of this version. The envelope is the warrant for that version. Chapter 3 states that promotion does not approve it.
- **Metrology:** measurement confidence and validity window.
- **Axiology:** the classification marking.
- **Praxeology:** the action classes allowed and denied.

The triple is the assertion. The envelopes are the context of its instantiation, and they travel with it in the same row. Because the record is JSON-LD it is also an RDF dataset, so a graph projection can hold the triple under the record identifier as a named graph without a second representation. The ledger row, not the graph, is the record.

A record is never updated in place. A change is a new row with the same identifier and a new fingerprint, and older rows remain readable. The ledger also stores the refinement rules that praxeology and axiology evaluate. Snapshot history supports replay of both the admitted world and the policy under which it was admitted.

A Parquet export of rows without the envelopes and without the bundle is not the ledger. Chapter 7 states what that export abandons.

## 4.2 Projections and Snapshot Syncs

The vector index, the graph database, and the policy engine’s loaded bundle are projections or syncs from snapshots. They are not live mounts, unless a virtualization path is later implemented and named. Each projection must be emptiable and rebuildable from the ledger. The specification makes that rebuild an acceptance test, and the reference implementation runs it as one (`AG6` check). That check is a contract check. It is not a Chapter 6 benchmark.

- **Metrology:** analytical SQL over Iceberg tables for drift and calibration monitoring.
- **Epistemic projection:** a vector index (Qdrant) loaded from a lakehouse table of embeddings keyed to the record identifier and fingerprint. Epistemology’s claims remain graded proposals. The gates receive them at request time and do not read them from the snapshot (§3.4).
- **Ontological projection:** a graph database, Apache Jena Fuseki in the reference implementation, loaded from a snapshot and used for entity-relationship checks.
- **Praxeological and axiological projection:** rules exported from a snapshot into an OPA bundle. OPA evaluates that exported bundle. It does not query Iceberg at decision time.

## 4.3 Snapshot-linked Replay

A decision stores the record identifiers it governed, the hash of the policy bundle in force, and the gate outcome. That is the `moepa.decisions` ledger (`DS5`) as implemented. The Iceberg snapshot id is specified for the same record and is not yet written by the reference implementation. Signing is future work.

Replay, once that snapshot id is written, cites the snapshot identifier and the bundle hash already stored with the records and the versioned rules. The policy engine evaluates the exported bundle and does not consult a vendor procedure for the rule.
