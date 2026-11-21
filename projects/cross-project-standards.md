# Cross-project standards reuse — KubeIntellect, Agent Movement, NovaFabric and YazSes

**Prepared:** 2026-11-21 (Europe/Rome). **Purpose:** a public, neutral standards mapping that supports design discussion and controlled reuse across repositories, without publishing private implementation material.

## Project catalogue status

| Project | Register in this repository | Status as of research date |
| --- | --- | --- |
| [KubeIntellect](https://github.com/MSKazemi/kubeintellect) | [KubeIntellect register](kubeintellect.md) and [traceability](kubeintellect-traceability.md) | Research proposal on a review branch |
| [Agent Movement](https://github.com/MSKazemi/agent-movement) | [284-entry draft register](https://github.com/MSKazemi/standards/pull/2) | Unmerged draft PR with 42 historical + 242 unverified discovery candidates |
| [NovaFabric](https://github.com/MSKazemi/novafabric) | [227-entry draft register](https://github.com/MSKazemi/standards/pull/1) | Unmerged draft PR |
| [YazSes](https://github.com/MSKazemi/yazses) | [YazSes register](yazses.md) | 98-entry register on main |

The PR links are status snapshots, not guarantees about future merges. Do not copy private code, internal findings, or unpublished documents into this public catalogue.

## Reuse matrix

| Standard or family | KubeIntellect | Agent Movement | NovaFabric | YazSes |
| --- | --- | --- | --- | --- |
| ISO/IEC 42001 and NIST AI RMF | Model/operator governance | Agent-governance research | Evidence mapping | Optional AI governance |
| ISO/IEC 27001/27090 | Tool and Kubernetes threat treatment | Delegated execution security | Evidence infrastructure security | Local application and model security |
| OAuth RFC 8693/8707/9449; SPIFFE | Scoped tools and agent worker identities | Authority transfer experiments | Evidence producer / verifier identity | Optional connected-agent access |
| SCITT RFC 9943, COSE Receipts RFC 9942 | Independently checkable remediation records | Handoff and decision-chain receipts | Transparency and provenance infrastructure | Optional signed release or audit evidence |
| RFC 8785 canonical JSON, JSON Schema | Stable action/approval digests | Versioned handoff envelopes | Reproducible evidence bundles | Export and metadata consistency |
| W3C PROV, Trace Context, OTel | Diagnosis-to-operation lineage | Task continuity and cross-executor correlation | Run capture and provenance graph | Traceability for opt-in workflows |
| MCP, A2A, AG-UI | Agent/tool integrations and HITL | Inter-agent task communication | Run capture and tool instrumentation | Optional local agent interaction |
| CloudEvents and AsyncAPI | Incidents, alerts, reconciliation | Transfer/revocation event grammar | Event ingestion | Optional external event integration |
| SLSA, in-toto, SPDX, CycloneDX | Build and image provenance | Executor software supply chain | Evidence and packaging provenance | Open-source release and dependencies |
| Kubernetes PSS, CIS Benchmark | Core controlled infrastructure | Executor container deployment | Optional deployment security | Usually not applicable |
| OWASP Agentic Top 10 / ACS | Native agent action risk | Delegated agent risks | Agent evidence provenance | Opt-in agent capabilities |
| GDPR and CRA | Scope-dependent data handling and software supply | Deployment-specific risk | Data governance and software release | Local privacy and software distribution |

## Highest-return engineering research intersections

### 1. Evidence-carrying actions (KubeIntellect + NovaFabric)

Use the same publicly defined statement semantics for a requested action, authorized effect plan, decision records, observed Kubernetes changes and postconditions. A NovaFabric-style recorder may provide independent verification or capture, but the integration requires a distinct trust and completeness threat model.

**Question to falsify:** can a verifier reject altered or omitted action evidence and explicitly report what is unknown?

### 2. Exclusive executor safety (KubeIntellect + Agent Movement)

Study execution epochs, single-use approvals and independently mediated effects. Moving the task or resuming a checkpoint must not authorize a prior worker to continue creating effects.

**Question to falsify:** after a crash/restart, split-brain leader or network partition, can a stale agent mutate the cluster despite an ownership change?

### 3. Interoperability without authority inflation (all applicable projects)

Tool schemas and protocol transport must remain distinct from access control. A2A delegates task messages; MCP exposes tools; OAuth/SPIFFE identify and constrain actors; a policy enforcement point decides effects.

**Question to falsify:** can copied credentials, misleading tool metadata, injected outputs or stale approvals authorize a forbidden effect?

## Protocol boundaries that must remain explicit

1. **A2A is not agent runtime checkpoint migration.** It transfers tasks and artifacts, not automatic exclusive execution ownership.
2. **OAuth and SPIFFE identity are not end-to-end operation authorization.** Resource/verb/argument scopes and independent enforcement remain necessary.
3. **SCITT, COSE, W3C PROV and OTel provide different evidence properties.** Signed statements are not proof that no unrecorded side effects occurred.
4. **OCI images and serialized checkpoints are not semantic continuity guarantees.** Versioned state and compatible tools/models are needed.
5. **A delivered message does not imply exactly-once effect execution.** External sinks need idempotency, fencing or reconciliation.
6. **Safety and legal applicability depend on actual deployment.** Standards may guide experiments without making a product certified.

## Prioritized shared research backlog (not issues yet)

| ID | Work package | Target | Evidence gate |
| --- | --- | --- | --- |
| STD-X-01 | Verify normative references and de-duplicate cross-project aliases | Standards repository | Stable IDs, official URLs, dated reviews, type taxonomy |
| STD-X-02 | Draft a portable agent-action evidence envelope and conformance examples | KubeIntellect + NovaFabric | Cross-language canonicalization and independent signature verification |
| STD-X-03 | Test stale-executor fencing and uncertainty after lost acknowledgments | KubeIntellect + Agent Movement | Adversarial partition and retry suite |
| STD-X-04 | Define scoped agent authority and policy-decision interoperability profile | KubeIntellect + Agent Movement | Deny by wrong audience, expired grant and elevated operation |
| STD-X-05 | Evaluate MCP/A2A/CloudEvents contracts for controlled handoffs | KubeIntellect + Agent Movement | Tool authority, version negotiation and failure matrices |

These are proposed work packages, not approved milestones or evidence that the functionality ships. Projects retain their own code, issues, roadmap, and security disclosure procedures.
