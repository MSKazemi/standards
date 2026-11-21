# KubeIntellect — standards-to-architecture and verification matrix

**Date:** 2026-11-21 (Europe/Rome). **Status:** proposed research and engineering mapping, not implemented control assurance or certification.

**Public source:** [KubeIntellect](https://github.com/MSKazemi/kubeintellect), with public-facing documentation including [README](https://github.com/MSKazemi/kubeintellect/blob/main/README.md), [security policy](https://github.com/MSKazemi/kubeintellect/blob/main/SECURITY.md), and [v4 data handling](https://github.com/MSKazemi/kubeintellect/blob/main/v4/docs/data-handling.md). Implementation status must be rechecked on the correct branch when used. This register intentionally contains no private repository links, private design file paths or unpublished security vulnerabilities.

## Interpretation

- These are **engineering experiments and standards applicability hypotheses**, not a compliance status report.
- Priority **Now** is a gate to validate before exposing additional agent endpoints. **Next** means high-value short-term work. **Research** means future, feature-dependent work.
- All test outcomes below are **proposed**; none of the tests are asserted to have been executed by writing this document.
- The owner must confirm deployment scope, regulatory role, and edition before deciding that an external requirement is mandatory.

## Standards-to-system traceability

| System boundary / concern | Candidate standards or guidance | Evidence to capture | Suggested verification | Phase |
| --- | --- | --- | --- | --- |
| AI supervisor and delegation | ISO/IEC 42001, 23894, 42005; NIST AI RMF, AI 600-1; OWASP Agentic Top 10 | Versioned tool roster, model selection policy, threat scenarios, risk owners | Reproducible scenario suite; adversarial tool description and data-injection probes | Now |
| Tool-call authorization | Kubernetes RBAC, NIST 800-207, RFC 8693/8707, SPIFFE | Actor, audience, role, cluster, namespace, operation and expiry | Cross-tenant denial, wrong-audience denial, expired-token refusal | Now |
| Human approval of effects | ISO/IEC TS 8200, OWASP Agent Control Standard, ISO/IEC 25059 | Exact action parameters, before/after diff, human approval decision, effect scope | Wrong resource/parameter substitution; replayed approvals; denial behavior | Now |
| Kubernetes API mutations | CIS Kubernetes Benchmark, Kubernetes PSS and ValidatingAdmissionPolicy, NIST 800-190 | Server-side policy decision, dry-run evidence, immutable action ID | Allow/deny Kubernetes admission tests; unexpected resource changes forbidden | Now |
| Incident ingestion and external events | CloudEvents, AsyncAPI, RFC 9562, JSON Schema | Event schema ID, source, subject, event ID, correlation ID | Duplicated or reordered alerts; schema rejection; idempotent event processing | Next |
| Multi-agent protocol integration | MCP, A2A, OpenAPI, OAuth Security BCP | Capability descriptions, authorized tool calls, input and output schema | Deny untrusted servers, mismatched grants, forged tool results and unauthorized action | Next |
| Agent execution continuity | RFC 8785, JSON Schema, RFC 7009/7662, OAuth 2.0 token exchange; Kubernetes coordination leases | Execution epoch, ownership changes, lease expiry and external effect receipts | Stale worker after reassignment; network partition; double execution | Next |
| Diagnostic grounding and provenance | W3C PROV-DM/PROV-O, W3C Trace Context, OpenTelemetry | Provenance graph linking query, observations, hypotheses, verified action and outcomes | Missing evidence, contradictory observations and unsupported diagnoses | Next |
| Cryptographically verifiable evidence | RFC 8785, RFC 9052, RFC 9942, RFC 9943, Sigstore/in-toto | Canonical signed envelopes, digest, actor, verifier, receipt and ledger checkpoint | Forged/modified evidence; offline signature verification; missing record detection limits | Next |
| Agent memory and lessons | ISO/IEC 5259 series, 25059, 23894; OWASP agent security | Origin labeling, trust level, temporal relevance, invalidation and source citations | Injected incident artifacts cannot become higher-trust instructions | Next |
| Human-facing incident experience | WCAG 2.2, EN 301 549, ISO 9241-210, AG-UI | Accessible decision cards, meaningful labels, risk explanation, keyboard handling | Keyboard-only and screen reader approval flows; comprehension tests | Next |
| Monitoring, cost and SRE | OTel/OTLP, OpenCost, ISO/IEC 19086, SLO/error budget guidance | SLI definition, measured incident duration, action cost and outcome | Objective service-health window; metric provenance; cost attribution | Next |
| Multi-cloud and on-prem installation | OCI Image/Distribution, Kubernetes API, Helm, ISO/IEC 5140, 19941 | Image digests, chart tests, RBAC profiles, portability matrix | Kind and one managed-cloud smoke test; failure and rollback exercise | Next |
| Release and supply chain | NIST 800-218, SLSA, SPDX, CycloneDX, Sigstore, OpenSSF OSPS | SBOM for each image, signed build provenance, dependency gates, reproducibility evidence | Attestation verification and artifact-to-source linkage; compare release tags | Now |
| Privacy and sensitive log handling | GDPR scope review, ISO/IEC 27701/27018/29134; NIST SP 800-53 | Data inventories, LLM egress policy, retention and deletion controls | Data minimization/redaction tests before provider submission; retention tests | Now |
| Security incident and recoverability | NIST SP 800-61, ISO/IEC 27035, ISO 22301 | Incident records, audit chain, recovery procedures, key rotation | Interrupted execution and recorder consistency; independent restoration test | Next |
| Regulatory classification | GDPR, EU AI Act, Cyber Resilience Act, NIS2 (conditional) | Documented scope decision by legal/product owner | Jurisdictional and intended-use review; reassessment after deployment changes | Research |

## Specific cross-project research packages

### Package KI-STD-01 — Secure agent authorization and execution fencing

**Goal:** establish that only the currently authorized, explicitly approved executor can create a Kubernetes effect.

**Scope:** baseline permissions, one-use action authorization, per-session ownership, worker fencing, denial under partitions, bounded retries, and explicit unknown outcomes. Reuse existing implementation and tests where present.

**Standards anchors:** Kubernetes RBAC and admission policy, NIST Zero Trust, OAuth RFC 8693, 8707, 8705, 9449, and RFC 7009/7662.

**Acceptance evidence (proposed):**
1. Wrong principal, wrong resource, expired approval, and wrong audience are denied.
2. Stale executor cannot commit a mutation through covered enforcement points after its epoch changes.
3. A lost acknowledgment cannot be mistaken for demonstrated nonexecution; external effects have deduplication or reconciliation semantics.
4. Authorization decisions and rejections are recorded with trace and action IDs.
5. Cluster impact is bounded and assessed in an isolated test environment.

**Non-guarantee:** revoking a token does not prove that already-dispatched or unmediated effects were canceled.

### Package KI-STD-02 — Evidence-carrying Kubernetes remediation

**Goal:** make each human-approved Kubernetes action independently reviewable through a portable evidence envelope.

**Standards anchors:** W3C PROV, Trace Context, RFC 8785, COSE structures RFC 9052, COSE Receipts RFC 9942 and SCITT RFC 9943.

**Proposed envelope fields:** `schema_version`, `incident_id`, `action_id`, `requester_id`, `executor_id`, `cluster_target`, `effect_spec_digest`, `approval_digest`, `policy_decision_digest`, `observations`, `postcondition_result`, `evidence_hashes`, `signature`, `transparency_receipt`, `outcome_status`.

**Acceptance evidence (proposed):**
1. Canonical serialization is deterministic under field ordering variation.
2. Modified payload or incorrect signer fails verification.
3. Independently verified receipt matches the signed statement.
4. External verifier can distinguish authenticated evidence from verified action correctness.
5. Missing evidence, stale observations and unverifiable effects are represented as unknown/inconclusive rather than success.

**Non-guarantee:** integrity proofs do not establish completeness of observation or absence of side effects.

### Package KI-STD-03 — Agent and event interoperability

**Goal:** interoperable integration with agent tooling and event sources without broadening authority accidentally.

**Standards anchors:** MCP, A2A, AG-UI, OpenAPI, JSON Schema, CloudEvents, AsyncAPI, OAuth Security BCP and OpenTelemetry.

**Acceptance evidence (proposed):**
1. Read-only tools are exposed separately from elevated operations.
2. Tool authorization is independently enforced, not inferred from caller authentication alone.
3. All event schemas are versioned; duplicates, missing fields and unsupported event types fail predictably.
4. Human approvals remain explicitly tied to the proposed action and cluster target.
5. Protocol-version compatibility is demonstrated against pinned test clients and servers.
6. External tool output is handled as untrusted data.

## Proposed staged adoption

| Gate | Delivery target | Owner decision |
| --- | --- | --- |
| Gate 0 — inventory correctness | Reviewed edition, primary source, risk level and legal scope for adopted references | Confirm actual normative baseline |
| Gate 1 — security and privacy | Evidence of action authority, approved effect binding, Kubernetes RBAC/admission and LLM data boundary tests | Approve exposure of agent interfaces |
| Gate 2 — provenance demonstrator | Signed action evidence, external verification and unknown-outcome handling | Decide whether to adopt SCITT-compatible receipt path |
| Gate 3 — interop | MCP/A2A/AG-UI and event contract interoperability tests | Approve supported adapters |
| Gate 4 — research quality | Failure injection, benchmarking and independent repeatability | Decide on publication or conformance statements |

## Engineering handoff and change-control

For each feature-sized implementation ticket, provide: affected repository and branch, existing code or issue links, exact API and cluster scope, risk classification, test fixtures, failure cases, policy proof boundary, negative tests, performance/cost budget, reviewer, CI artifacts, and approval gate.

Only changes to the public **standards research catalogue** are authorized by this document; no KubeIntellect source code, deployment configuration, cloud resources, production clusters or private research material are changed here. Use the original project to track implementation tasks; avoid duplicate issues in this standards repository.
