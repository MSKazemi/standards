# How to use standards in engineering projects

**Research and operating guide:** 2026-11-21 (Europe/Rome) · **Scope:** public, reusable across the project registers in this repository.

A standards register is **a discovery and decision tool**, not a feature checklist, a purchase list, a certification, or a substitute for legal advice. The goal is to turn a **small, applicable subset** of external references into verifiable engineering contracts and truthful product documentation.

## 1. Treat these four concepts separately

| Dimension | Question | Possible states |
|---|---|---|
| **Publication maturity** | Is this a ratified standard, a final specification, a community draft, a guidance document, or a law? | final standard, committee specification, draft, voluntary guidance, law/regulation, historical/withdrawn |
| **Applicability** | Does it apply to this product, deployment, use case and jurisdiction? | unassessed, applicable, conditional, informative, not applicable; provide reasoning |
| **Implementation** | What actually exists in a specific version/branch? | unverified, not implemented, planned, experimental, works today, deprecated; require a source |
| **Verification** | What does independent evidence establish? | not tested, test failed, internal tests only, independently reproduced, externally assessed; scope must be explicit |

Never collapse these four into a single “compliant” checkbox. A law may be legally applicable even when its supporting software format is not implemented. A product may fully implement a format without satisfying a broader regulatory regime. A vendor's claim is not an independent conformance test.

**Research priorities in project registers (P0–P3) express potential technical relevance.** They do not assign GitHub issue severity, legal obligations, delivery dates, or approval to implement a new feature.

## 2. Adoption workflow: reference → profile → evidence

1. **Discover and deduplicate.** Find the issuer's official landing page, exact identifier, edition, publication stage, update/supersession notice, and license terms. Check project registers and existing local references first. One standard can support multiple projects; do not create duplicate product work.
2. **Screen applicability.** State the precise capability (e.g., agent tool-call evidence), deployment mode (offline CLI, self-hosted collector, enterprise server), affected jurisdiction/customer, asset and threat. Record **not applicable** or **defer** when justified. Do not make all 264 NovaFabric entries mandatory.
3. **Choose an explicit profile.** Record which section, object type, algorithm, message flow, optional feature and supported edition matter; document a narrow claim. If the specification text is licensed, link to official metadata and reference clause numbers rather than copying protected wording.
4. **Check what already ships.** Inspect the authoritative code repository, docs, tests, implementation version and real fixtures. Mark an existing claim as *reported* until independently reproduced. Do not use this standards repository as a substitute for source code or test logs.
5. **Write a requirement-to-evidence mapping.** For each selected requirement define the relevant emitted artifact, exact command/API, test name, expected assertions, version, signer/trust context, and what the artifact **cannot** prove. Use the [adoption record template](../templates/standard-adoption-record.md).
6. **Implement only the verified gap.** Prepare an issue or RFC in the owning product repository; describe the compatibility impact, resource needs, security/privacy boundaries and rollback. Reject speculative new file formats, always-on network services, or new dependencies merely because they exist in a standard.
7. **Prove interoperability and failure behavior.** Combine positive, negative, compatibility, independent-tool, offline and tamper/attack tests. Keep actual commands, exit codes, input hashes and raw logs in the owning repo or build artifacts. Do not substitute snapshots or mocks for all evidence.
8. **Publish precise claims.** Say “exports PROV-N for this profile, tested with X at commit Y,” not “W3C certified.” Say “produces evidence useful for an EU AI Act technical file,” not “EU AI Act compliant.” Preserve explicit limitations and maturity labels.
9. **Review on change.** Trigger reassessment on release, format changes, standards updates, security incidents, new jurisdiction or new deployment mode. Recommended calendar hygiene: quarterly edition/link checks and a larger pre-release evidence review; these are suggestions, not assumed commitments.

## 3. A useful evidence record

A reviewable record should tie one claim to a repeatable check:

| Field | Example (illustrative; not a test result) |
|---|---|
| Claim | “Sealed Evidence Bundle signature can be verified offline” |
| Reference and profile | in-toto Statement v1 + DSSE; selected signature algorithms and payload types |
| Scope | Local capture and exported bundle; no network requirement |
| Implementation reference | Owning repository path, release and commit (fill after inspection) |
| Positive test | Verify an unmodified signed fixture with an **independent** DSSE implementation |
| Negative test | Mutate a byte, replace the key, omit an attachment, rotate the trust root; each must fail closed |
| Compatibility test | Verify earlier supported bundle versions without changing their format |
| Evidence | Test runner, command, inputs, stdout/stderr, exit code, checksums, output manifest and reviewer |
| Explicit limitation | Signature verifies integrity and selected signer key; it does not establish agent intent, lawful processing or a regulatory verdict |

**Trust, integrity, provenance and replay are different propositions.** A digest establishes equality of bytes to a given digest; a signature binds data to a key; a certificate chain provides identity evidence only under a chosen trust policy; a trusted timestamp adds a time assertion under TSA validation; a replay checks selected execution properties under a stated environment. A structural or semantic replay cannot promise byte-identical results from a changing remote model.

## 4. Product-specific worked example: NovaFabric

NovaFabric's public [conformance reference](https://github.com/MSKazemi/novafabric/blob/main/docs/standards-conformance.md) is the **source for documented capability/maturity claims**; this catalogue is for *candidate discovery and applicability assessment*.

| Lane | Start from | Typical evidence and acceptance test | Key non-claim |
|---|---|---|---|
| **Trusted evidence and sealing** | DSSE, in-toto, RFC 3161, Merkle RFC 6962/9162, RFC 8785 | Run `nova verify <capsule-dir>`; export evidence; use an independent verifier; corrupt signed payload, timestamp, leaf hash and redaction proof separately; cover air-gapped verification | A DSSE signature is not a qualified electronic signature, and configured TSA access does not itself imply qualified timestamps |
| **Agent and model interoperability** | MCP, A2A, OTel GenAI, OpenLineage, W3C PROV | Use supported `nova mcp conformance` and `nova lineage export-prov` commands where available; compare to a version-pinned external parser and inspect missing/unknown fields | Recording a tool call does not prove permission, correct authorization or successful execution |
| **Privacy and data minimization** | GDPR, ISO/IEC 20889, NIST 800-88 Rev. 2, ISO/IEC 27701 | Threat-model prompt/tool-output leaks; inject representative PII/secrets; verify redaction, access policy and retention/deletion limits; check negative paths and backups | A redaction proof is not guaranteed irreversible anonymization or complete erasure of all copies |
| **Server-mode delegated access** | OAuth Security BCP, RFC 8693/8707/9396/9728, AuthZEN, ABAC | Test token audience isolation, scoped tool permissions, expired/revoked credentials, cross-tenant access, missing approvals and audit evidence | Local offline mode need not implement enterprise SSO/federation |
| **Regulatory evidence export** | EU AI Act, ISO/IEC 42001, NIST AI RMF, ISO 19011 | Verify factual data lineage, timestamps, missing-field explanations and mapping-version pinning; route obligation interpretations to qualified owners | An evidence export is neither certification nor legal compliance |
| **Release and research assurance** | SLSA, CycloneDX, OpenSSF OSPS Baseline, ISO/IEC 25023, IEEE 1012, CFF | Audit release attestations, independent build/source references, repeatability metrics and negative regression cases | A build badge or mock-only test suite does not validate a real storage/remote model environment |

**Architecture constraints:** NovaFabric should preserve its two existing top-level artifacts (Run Capsule and Evidence Bundle), default-off sensitive capture, offline verification, redaction boundaries, additive schema evolution and “never block the workload” capture rule. Treat SCITT/COSE, signed HTTP exchange and advanced authorization as **optional interoperability profiles subject to a product RFC** — not automatic migrations.

Example commands above are **workplan examples derived from product documentation**, not evidence that this review executed them. Run and archive actual output before marking any record independently verified.

## 5. Quality gate before publishing a conformance statement

A claim is ready for review only when it has:

- A precise standard/version/profile and product version/commit;
- Applicability and exclusions, separately from priority and implementation maturity;
- Traceable requirement IDs, source URLs and a human-readable test plan;
- Positive, negative, legacy-format, redaction and offline cases as relevant;
- Independent verifier, parser or implementation where realistically available;
- Real reproducible test evidence, with unedited command output and hashes;
- Threat-model and compatibility assessment where applicable;
- Reviewer approval and a short list of things **not** established by the evidence.

**Regulatory or certified status** must be established by the appropriate qualified authority and cannot be conferred by product code, a crosswalk, a test pass, or this repository.

## 6. Ownership, changes and cost control

- **This public repository** owns per-project discovery lists, reference identifiers, public edition links, review methodology, applicability hypotheses and cross-project indexing.
- **Each project repository** owns actual requirement mappings, architecture decisions, source code, conformance suites, build logs, issue priorities and release claims. Keep confidential roadmaps, customer evidence, security findings and internal architecture outside this public index.
- **Standard bodies/publishers** own normative texts and edition status; do not republish licensed ISO/IEC/IEEE/AICPA/CIS material.
- **No paid API or certification needed to begin.** Start with freely accessible IETF/W3C/OpenID/CNCF/OpenSSF materials and local tests. Paid publisher copies or external accreditation are separate decisions, not prerequisites for maintaining the research catalogue.
- **No auto-created engineering issue for each standard.** A single engineering issue may satisfy several related references. File an issue only for a verified gap with acceptance tests; don't confuse reference count with deliverable count.

## 7. Register and machine-readable inventory

- Human review: [NovaFabric catalogue](../projects/novafabric.md).
- CSV for filtering, prioritization and reconciliation: [NovaFabric standards data](../data/novafabric-standards.csv).
- Product-specific work packets: [NovaFabric standards adoption plan](../projects/novafabric-standards-adoption-plan.md).
- Fill this template for a concrete adoption decision: [standard adoption record](../templates/standard-adoption-record.md).

The CSV is a **discovery snapshot**, not a conformance database: a product report of “works today” in an inventory row is not independently verified evidence; the only correct default for an unassessed standard is “applicability not yet evaluated.” CSV identifiers are intended to remain stable after publication; add future entries without renumbering prior IDs.
