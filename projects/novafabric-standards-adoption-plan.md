# NovaFabric — standards adoption and verification workplan

**Research baseline:** 2026-11-21 (Europe/Rome) · **Companion:** [264-reference register](novafabric.md) · **Method:** [How to use standards](../docs/how-to-use-standards.md).  
**Status:** **Proposal only**; engineering tasks are not approved, scheduled or implemented by this document. The canonical product implementation and conformance claims live in [MSKazemi/novafabric](https://github.com/MSKazemi/novafabric) and its [standards conformance documentation](https://github.com/MSKazemi/novafabric/blob/main/docs/standards-conformance.md).

## Strategic answer: what standards should do for NovaFabric

The objective is **not** to implement 264 independent features or obtain 264 certificates. The high-value outcome is:

> A third party receives a redacted, portable AI-agent run receipt; can understand what was captured and omitted; independently verify integrity, signature, timestamp and lineage; examine replay and tool-use claims under stated conditions; and consume the evidence through common interfaces **without trusting NovaFabric's own verifier**.

Apply standards in four roles:

1. **Data and protocol contracts** — DSSE, in-toto, JSON Schema, MCP, OTel, PROV, SCITT (candidate). These define syntax, bytes, signatures and interoperability obligations.
2. **Security engineering references** — NIST SP 800-88, 800-207, 800-218; RFC 8707/9396; ISO 20889; OWASP and OpenSSF. These inform threat models and tests.
3. **Evidence mapping and organizational guidance** — NIST AI RMF, ISO/IEC 42001/42005, ISO 19011, EU AI Act. They help people build structured audit evidence but must not be described as a compliance product.
4. **Conditional sector rules** — finance, healthcare and government retention obligations. Activate only for actual scoped deployments and qualified legal determinations.

A standard's `P0/P1` *relevance* in the register must not be confused with implementation urgency in the project's issue tracker.

## What to do now versus later

| Order | Lane | Why | Release gate |
|---|---|---|---|
| **Now: A. Trust and truthfulness** | Claims audit + independent Evidence Bundle verification + timestamp/trust-path failure cases | Core product trust and risk of incorrect claims | Reference version pinned, independent verifier reproduced, negatives fail closed |
| **Now: B. Redaction and replay limits** | Sensitive prompt/tool capture, privacy risk, replay determinism disclosures | A valid signature over a leaked or misleading record is still unsafe | Verified sanitization/retention boundaries; explicit replay-mode limitations |
| **Now: C. Interoperability** | OTel GenAI, MCP, OpenLineage, PROV-N/JSON conformance profiles | Customers need to export evidence and compare it externally | Portable fixtures pass external consumer and version-skew tests |
| **Next: D. Server access and operational assurance** | RFC 9421/9530; OAuth delegation, AuthZEN; OpenSSF; security disclosure procedures | Useful for multi-tenant deployment and shared evidence | Threat model, audience/tenant isolation, denied-action and revocation tests |
| **Later / demand-driven: E. New interchange profiles** | SCITT / COSE Receipts, signed RDF graphs, qualified trust service, finance/health profiles | Interop potential, but format/security costs and legal dependencies | RFC, independent ecosystem demonstration, compatibility and maintenance decision |

## Work packets for the technical repository

These packets are **proposed** input for the technical GitHub issues, not new issues in this reference repository. Check existing NovaFabric issues/PRs and ADRs before creating work. No dates or assignees are presumed.

### NF-STD-01 — Create an evidence-backed claim inventory

**Outcome:** For each public “works today” and “experimental” claim in the product's standards-conformance page, record exact command, artifact, schema/profile, product ref, real test and known limitation.

- **Input:** [public conformance map](https://github.com/MSKazemi/novafabric/blob/main/docs/standards-conformance.md), the product's existing tests, [register](novafabric.md), and the [assessment template](../templates/standard-adoption-record.md).
- **Deliverable:** One version-pinned source-of-truth table **in the product repo**; references here link to it but never override it.
- **Acceptance:** Zero claims without maturity label, version or “not independently verified” qualification. Distinguish format support vs governance crosswalk vs regulatory evidence.
- **Size/dependencies:** S–M; no prerequisite. Owner: maintainer/reviewer to assign.

### NF-STD-02 — Independent offline evidence verification

**Outcome:** Verify signed Evidence Bundles and sealed capsules using an independent verifier and auditable local fixtures.

- **References:** DSSE/in-toto, RFC 8785 (where actually used), RFC 3161, RFC 5280, Merkle RFC 6962/9162.
- **Negative cases:** Wrong signer key; modified byte; omitted artifact; swapped metadata; invalid timestamp chain; missing or expired trust anchor; revoked certificate under an appropriate trust policy; Merkle inclusion mismatch; old-format compatibility.
- **Acceptance:** Exact commands and raw outputs, with external verifier versions and positive/negative result matrix; fully offline verification documented where supported; time validation never presented as automatic legal qualification.
- **Size/dependencies:** M–L; depends on NF-STD-01; may require non-secret local test keys and pre-generated timestamp fixtures; do not require paid cloud/KMS.

### NF-STD-03 — Replay integrity and evidence-loss failure modes

**Outcome:** Define the properties proven by each replay mode and measure when replay diverges from captured tool/model interactions.

- **References:** JSON Schema 2020-12, W3C PROV, OTel GenAI, IEEE 1012-2024, ISO/IEC 25023.
- **Cases:** Tool call retained vs redacted; missing result; changed model; nondeterministic remote LLM; divergent side effect; broken lineage; incompatible historical capture.
- **Acceptance:** Fixture matrix and mode-specific expected outcomes; no unsupported byte-identical hosted-model claims; ordinary capture never blocked by sealing failures.
- **Size/dependencies:** M; NF-STD-01.

### NF-STD-04 — Privacy, retention and erasure proof boundaries

**Outcome:** Test what prompt redaction, secret scanning, PII handling, encryption scope and disposal actually accomplish.

- **References:** GDPR, ISO/IEC 20889, ISO/IEC 27701, NIST SP 800-88 Rev. 2.
- **Cases:** PII in prompt/tool response/metadata, hash-only references, backup copies, legal hold, removed keys, disabled network, false-negative redaction cases.
- **Acceptance:** Redaction-sensitive fixtures, actual deletion/retention limitations, clear `complete/partial/missing` evidence, and a statement of residual re-identification risk.
- **Size/dependencies:** M–L; NF-STD-01; legal counsel for regulatory interpretation.

### NF-STD-05 — Agent interoperability profiles

**Outcome:** Freeze conformance inputs/outputs for the product's supported MCP, OTel GenAI, OpenLineage and W3C PROV surfaces **per product release**.

- **Cases:** Tool-call order, missing fields, unknown extensions, timestamps, semantic convention changes, multipart traces, invalid PROV edges, third-party parser round-trip.
- **Acceptance:** Version-pinned external consumer or conformance test for each actually supported profile and explicit unsupported cases.
- **Size/dependencies:** M; NF-STD-01 and NF-STD-03.

### NF-STD-06 — Evaluate HTTP evidence transport integrity (not a default change)

**Outcome:** Decide whether the **optional server API** would benefit from RFC 9421 HTTP Message Signatures and RFC 9530 digest fields.

- **Cases:** Trusted and untrusted reverse proxies, signed headers vs bodies, replayed request, canonicalization mismatch, modified `Content-Digest`, clock skew, oversized object and nonce reuse.
- **Acceptance:** Feasibility RFC and threat model, plus a minimal spike if approved; compare to existing DSSE-on-bundle design. No duplicate signing layer or new requirement for local CLI.
- **Size/dependencies:** S–M RFC; NF-STD-02. Implementation requires separate approval.

### NF-STD-07 — Scoped delegation and server-mode authorization

**Outcome:** Compare current server authorization against OAuth 2.0 token-exchange, audience restrictions, Rich Authorization Requests, AuthZEN, ABAC and continuous-access concepts.

- **Cases:** Cross-tenant request, stale agent token, improper tool action scope, privilege escalation via delegation, revoked authorization during long-running execution, missing human approval.
- **Acceptance:** Document the authorization boundary and independently reproduced deny-path tests. Do **not** require OIDC/SSO for offline capture.
- **Size/dependencies:** M–L; server threat model, NF-STD-01; no silent switch to new identity provider.

### NF-STD-08 — Release provenance and vulnerability communication

**Outcome:** Decide what release claims should be backed by SLSA provenance, CycloneDX, OpenSSF OSPS Baseline and optionally VEX/CSAF.

- **Cases:** Signed releases, dependency inventory, introduced vulnerability with affected/unaffected status, coordinated disclosure, provenance verification by a second tool.
- **Acceptance:** Source and artifact digest binding, a version-pinned OSPS evidence checklist, a disclosure/handling workflow consistent with ISO/IEC 29147 and 30111; no claim that CSAF 2.1 committee approval equals an OASIS Standard.
- **Size/dependencies:** M; release/CI owners to assign.

### NF-STD-09 — Governance crosswalks as data, not verdicts

**Outcome:** Audit existing export surfaces against selected parts of EU AI Act, ISO/IEC 42001, ISO/IEC 42005 and NIST AI RMF.

- **Cases:** Unknown or missing evidence, stale standard edition, inconsistent legal classifications, expired policy versions, unsupported profile.
- **Acceptance:** Each mapped item records observed capsule fact, source/provenance, emitted artifact, `present/partial/missing`, review role and explicit legal non-claim.
- **Size/dependencies:** M; NF-STD-01 and NF-STD-04; qualified review for applicability.

### NF-STD-10 — Research reproducibility and measurement profile

**Outcome:** Make capture, replay and audit performance claims reproducible under pinned hardware/software/LLM environments.

- **References:** IEEE 1012, ISO/IEC 25023, ISO/IEC/IEEE 29148, SWHID, CFF, RO-Crate, FAIR4RS.
- **Acceptance:** Source/fixture identifiers, command, environment, absolute overhead and uncertainty, seed applicability, repetitions, adversarial fixtures and raw results; a reviewer can rerun locally without a paid service.
- **Size/dependencies:** M; NF-STD-03.

### NF-STD-11 — SCITT and COSE receipts as an optional profile

**Outcome:** Determine whether RFC 9943 / RFC 9942 offer interoperability value beyond existing DSSE/Merkle receipts.

- **Acceptance:** Compatibility RFC, trust model and independent verifier; demonstrable mapping without changing Run Capsule or Evidence Bundle as top-level formats; no new default network dependency.
- **Size/dependencies:** M RFC; NF-STD-02 and verified external consumer demand. **Defer implementation until approved.**

### NF-STD-12 — Provenance graph semantics and optional canonicalization

**Outcome:** Assess W3C PROV-CONSTRAINTS and RDF Dataset Canonicalization 1.0 for future graph-export validation/signing.

- **Acceptance:** A graph validation matrix against an independent PROV checker; only if signing is justified, record canonicalization/algorithm interoperability and blank-node edge cases.
- **Size/dependencies:** S–M study; NF-STD-05; no schema change without RFC.

## Gates and ownership

| Gate | Passing evidence | Decision maker |
|---|---|---|
| **G0 — Review** | Source/edition confirmed; applicability assessed; no duplicate issue; one narrow claim and cost range | Product maintainer |
| **G1 — Design** | Security/compatibility RFC when required; threat model; protected data boundary; default-off/offline plan | Maintainer + security reviewer |
| **G2 — Verify** | Executed positive/negative tests, legacy fixtures, independent external verifier, captured raw logs | Technical reviewer |
| **G3 — Release claim** | Source commit and test evidence attached; conformance wording limited to what was measured; legal interpretation separate | Release owner |
| **G4 — Maintenance** | Edition update watch, incident feedback, version pinning and documented deprecation path | Maintainer |

**Stop conditions:** a proposed change silently alters an existing Evidence Bundle contract, adds mandatory cloud traffic, leaks private data, copies copyrighted standard text, conflates draft/spec maturity with certification, or makes capture fail because evidence signing fails. Those require redesign or rejection.

## Practical first three steps

1. **Create no extra issues yet:** inventory the existing NovaFabric issue/ADR/test coverage for NF-STD-01 through 04, and document observed gaps before deduplication.
2. Build one small, fully **independently verifiable Evidence Bundle fixture** plus intentional mutation tests. Keep a cheap all-local path.
3. Produce a version-pinned redaction/replay claim matrix that clearly states where evidence is missing, where a test uses mocks, and what a remote model cannot reproduce.

## Claude Code handoff (first reviewable slice only)

Use this as an engineering handoff after checking existing issues and human authorization; it deliberately creates a *plan/fixture PR*, not a blind implementation of hundreds of standards.

```text
Repository: MSKazemi/novafabric (and only authorized supporting private context)
Task: Audit and, if a true gap exists, propose a minimal independent
Evidence Bundle verification fixture mapped to DSSE/in-toto, RFC 3161,
Merkle proofs and redaction integrity.

Read AGENTS.md, CLAUDE.md, security guidance, current standards-conformance
docs, ADRs, issues/PRs, source modules and tests first. Reconcile duplicates.
Do not merge or deploy. No schema migration, mandatory network access, new
top-level format, disabled redaction or unapproved runtime dependencies.

Deliver a concise mapping of claimed behavior versus actual code/test evidence;
one explicit set of positive and mutated-negative fixtures with a second
implementation/verifier where possible; exact executed commands, exit codes,
build dependencies and limitations; and an open draft PR only if the
repository's documented test and link gates are actually run. Otherwise
deliver a proposed issue/work packet and explain any verification block.
```

## Public/private boundary and total cost

All records here are intentionally public-safe research descriptions; customer/internal implementation findings stay in the authorized product repository. Begin with IETF/W3C/OSS specifications and offline fixtures. Licensed full texts, paid certification, paid remote-model calls, and external TSA/KMS accounts are **not presumed necessary** for the first audit and validation activities. A complete legal or independent certified audit would be a separate decision.
