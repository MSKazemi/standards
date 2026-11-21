# Agent Movement — standards applicability register

**Purpose:** a broad, cross-domain, research-oriented list of standards, protocols, drafts, frameworks and regulations related to **AI-agent delegation and controlled movement of work across executors**.

**Catalog date:** 2026-11-21 (Europe/Rome). **Public register status:** research inventory; **not** a certification, conformance claim, legal interpretation, or production/safety assurance. **Scope:** 284 entries (**42 earlier version-tracked references** plus **242 discovery candidates**). **Machine-readable record:** [data/agent-movement-standards.csv](../data/agent-movement-standards.csv).

This register intentionally contains **only standards-related research content**. It does not reproduce private project implementation documents, research source code, confidential tests, user/partner data, or internally held decisions.

## How to interpret this register

- **Formal normative standards** (e.g., ISO/IEC, IEC, IEEE, W3C Recommendations, finalized RFCs) are different from **community protocols**, **vendor-led specifications**, **IETF Internet-Drafts**, **research methods** and **laws/regulations**.
- A standard appears because it **may** support a research question, not because it is mandatory, currently implemented, or certified.
- `Core` means central to studying independently authorized agent continuity; `Conditional` depends on a platform, deployment or product scope; `Watch` is adjacent or emerging. These labels are **research priorities**, not compliance obligations.
- **Version validity:** the first 42 records preserve earlier source-reported versions and access dates. The 242 expansion records explicitly say `not individually version-verified`. **No blanket November 2026 current-edition claim is made.**
- An official landing page does not guarantee the cited exact edition is still available; catalog-level links and ISO/IEC part numbers require item-level verification.
- `C1` foundations; `C2` continuity; `C3` compatibility; `C4` trust/safety; `C5` fault-tolerant migration; `C6` provenance; `C7` intelligent mobility. The C1–C7 tags in the CSV are **research lenses**, not compliance standards.
- Individual standards can be repeated in related groups or appear both in a dated version tracker and in the expansion; treat the total as **catalog entries**, not distinct standardization documents.

## High-leverage standards and protocols to examine first

| Reference family | Why it matters |
| --- | --- |
| **Agent2Agent (A2A)** | Cross-agent task messaging and delegation; not checkpoint relocation |
| **Model Context Protocol (MCP)** | Tool/resource access and controlled capabilities; not task ownership transfer |
| **RFC 8693 / OAuth 2.0** | Downscoped actor/audience grants with an independent enforcement boundary |
| **SPIFFE / SPIRE** | Workload identity for executor and service admission |
| **SCITT / COSE Receipts** | Signed evidence and audit trails; omission remains possible |
| **W3C PROV and OpenTelemetry** | Causal relationships and diagnostics; not complete forensic truth |
| **CloudEvents and JSON Schema** | Portable versioned control messages and event envelopes |
| **OCI and Kubernetes** | Image, runtime and scheduling infrastructure; not logical-state migration |
| **ISO/IEC 42001 and 23894** | AI governance and risk assessment |
| **ISO/IEC 5338 and TS 8200** | AI lifecycle, controllability, suspension and stop behavior |
| **IEEE 7001 and 7009** | Transparency and fail-safe autonomy |
| **DDS Security and IEC 62443** | Robotics and industrial interfaces with independent policy/safety layers |

## Scientific boundaries

Agent delegation is not ownership relocation. Moving task requests, text, serialized checkpoints, credentials, containers or TCP/QUIC connections does not by itself prove one authorized task owner, semantic continuity, independent policy enforcement or absence of stale effects. Likewise, a signed receipt authenticates a claim but cannot prove complete observation; a transport ACK is not an atomic external effect; and a simulated robot gateway is not certification for physical actuation.

### Research questions connected to the standards inventory

| Theme | Example falsifiable test |
| --- | --- |
| Identity and authority | Can a stale worker commit a controlled effect after authority moves? |
| State and compatibility | Can a syntactically valid checkpoint still fail semantic reconstruction? |
| Failure recovery | Does a lost ACK, network partition or retry create unresolved effects? |
| Provenance | Can a verifier distinguish missing, contradictory and forged statements? |
| Deployment and robotics | Can a test route enforce independent safety gates before side effects? |
| Decision quality | Can staying, restarting, delegating and relocating be compared fairly under bounded risk and cost? |

## Previously version-tracked protocols and technologies (42)

These entries come from an **earlier dated research snapshot**. Their versions, stewardship and maturity labels are recorded in the canonical CSV; they were **not freshly reverified for this publication**.

| Reference and source | Layer | Reported version | Why it may matter |
| --- | --- | --- | --- |
| [Agent2Agent Protocol (A2A)](https://a2a-protocol.org/latest/specification/) | agent-to-agent | v1.0.1 (spec site labels 1.0.0 as latest released version) | Standard interface for delegating a task to an independently hosted agent; it moves task requests and artifacts, not runtime checkpoints. |
| [Model Context Protocol (MCP)](https://modelcontextprotocol.io/specification/2026-07-28) | agent-to-tool | 2026-07-28 (current revision) | Lets a delegated or relocated agent reach eligible tools through a uniform interface; 2026-07-28 removes protocol-level sessions and the initialize handshake, so per-connection server state no longer has to follow the client. |
| [Agent-User Interaction Protocol (AG-UI)](https://docs.ag-ui.com/introduction) | agent-to-user | AG-UI 1.0 (@ag-ui/core 1.0.2 on npm) | Carries the user-facing event stream and approvals, so a move can stay visible to the user; it does not transfer execution between runtimes. |
| [Agent Communication Protocol (ACP; IBM / BeeAI)](https://lfaidata.foundation/communityblog/2025/08/29/acp-joins-forces-with-a2a-under-the-linux-foundations-lf-ai-data/) | agent-to-agent | v1.0.3 (final) | Do not target for new work; ACP users are directed to A2A, so A2A is the single delegation interface to track. |
| [Agent Network Protocol (ANP)](https://github.com/agent-network-protocol/AgentNetworkProtocol) | agent-to-agent | ANP 1.2 (specification set) | Decentralised alternative to A2A built on W3C DIDs (did:wba / did:web), relevant if agent identity must be portable without a central registry. |
| [AGNTCY Open Agentic Schema Framework (OASF)](https://github.com/agntcy/oasf) | agent-to-agent (discovery / description) | v1.1.0 | Schema for describing agent capabilities and metadata, a candidate input for compatibility negotiation before a handoff. |
| [Agent Payments Protocol (AP2)](https://ap2-protocol.org/) | identity/authz (payments mandates) | v0.2.0 | Signed checkout/payment mandates show how user authority for a side-effecting action can travel with a delegated task as verifiable credentials. |
| [Agentic Commerce Protocol (OpenAI and Stripe)](https://agenticcommerce.dev/) | agent-to-agent (agent-to-merchant) | 2026-04-17 (latest dated spec; 'unreleased' directory in progress) | Example of a vendor-maintained interop spec for one side-effecting action class (checkout); relevant to idempotency and authority, not to general movement. |
| [AGENTS.md](https://github.com/agentsmd/agents.md) | agent configuration (coding agents) | unversioned format | Portable, repository-level instructions for coding agents; it moves guidance, not state or authority. |
| [Agent Skills](https://agentskills.io/specification) | agent configuration (procedural packaging) | unversioned format (no tags or releases) | Portable procedure (instructions, references and executable scripts) that can be installed at a destination; it moves code but not state or authority, so treat it as software supply chain. |
| [WebMCP](https://webmachinelearning.github.io/webmcp/) | agent-to-web (browser tools) | Draft Community Group Report | Web pages expose JavaScript tools to agents via document.modelContext.registerTool(); tools run in the page with the user's logged-in session, so authority stays with the browser and does not move with the agent. |
| [WebDriver BiDi](https://www.w3.org/TR/webdriver-bidi/) | browser automation | W3C Working Draft | Standards-track bidirectional remote control of browsers; its storage module can read and set cookies, so a controller can copy a logged-in session, an authority-transfer path that needs policy. |
| [LangGraph persistence (langgraph-checkpoint + savers)](https://docs.langchain.com/oss/python/langgraph/persistence) | durability | langgraph-checkpoint 4.3.1; langgraph 1.2.18; langgraph-checkpoint-postgres 3.2.0 | Checkpoints let a graph resume on another worker that runs compatible LangGraph code and the same saver backend; they are not a cross-framework format. |
| [Temporal Server](https://docs.temporal.io/workflow-execution) | durability | v1.32.1 | Durable execution means a workflow can continue on any worker polling the same task queue, provided workflow code stays deterministic and activities are idempotent. |
| [Temporal SDKs (Go and Python)](https://github.com/temporalio/sdk-go/releases/tag/v1.50.0) | durability | Go v1.50.0; Python 1.35.0 | Worker-side SDK version pinning matters for replay compatibility when a workflow resumes on a different worker. |
| [OCI Image Format Specification](https://specs.opencontainers.org/image-spec/) | deployment | v1.1.1 | Makes the agent's code and runtime portable as an image; carries no live agent state. |
| [OCI Runtime Specification](https://github.com/opencontainers/runtime-spec) | deployment | v1.3.0 | Defines how a container is run consistently across hosts; process checkpoint/restore (e.g. CRIU) is outside this spec. |
| [OCI Distribution Specification](https://github.com/opencontainers/distribution-spec) | deployment | v1.1.1 | Registry API used to pull the same agent image at a destination; v1.1 referrers can attach signatures or SBOMs to that image. |
| [Kubernetes](https://kubernetes.io/releases/) | deployment | v1.37.2 (latest patch of newest minor 1.37) | Reschedules pods and Jobs after failure, which is restart, not migration; application-level checkpointing is still required. |
| [OAuth 2.0 Token Exchange (RFC 8693)](https://www.rfc-editor.org/rfc/rfc8693) | identity/authz | RFC 8693 | Standard way to exchange a token for a narrower, audience-bound token with actor (act) claims, the base pattern for delegated agent credentials. |
| [Transaction Tokens (draft-ietf-oauth-transaction-tokens)](https://datatracker.ietf.org/doc/draft-ietf-oauth-transaction-tokens/) | identity/authz | -11 | Short-lived tokens that carry user and request context through a chain of internal workloads, a candidate for propagating authority inside a multi-agent call chain. |
| [OAuth Identity and Authorization Chaining Across Domains (draft-ietf-oauth-identity-chaining)](https://datatracker.ietf.org/doc/draft-ietf-oauth-identity-chaining/) | identity/authz | -17 | Combines token exchange with JWT grants to carry identity across trust domains, the closest IETF pattern for cross-organisation agent handoff. |
| [WIMSE Architecture (draft-ietf-wimse-arch)](https://datatracker.ietf.org/doc/draft-ietf-wimse-arch/) | identity/authz | -08 | Architecture for workload identity across systems; agents are workloads, so this frames how a destination proves who it is. |
| [AI Identity Management System (draft-ietf-wimse-aims)](https://datatracker.ietf.org/doc/draft-ietf-wimse-aims/) | identity/authz | -00 | First WG-adopted IETF draft specifically on AI-agent identity; content may change substantially. |
| [OAuth 2.0 Extension: On-Behalf-Of User Authorization for AI Agents (draft-oauth-ai-agents-on-behalf-of-user)](https://datatracker.ietf.org/doc/draft-oauth-ai-agents-on-behalf-of-user/) | identity/authz | -02 | Shows proposed on-behalf-of semantics for agents but carries no standards status; cite only as a proposal. |
| [SPIFFE / SPIRE](https://spiffe.io/docs/latest/spiffe-about/overview/) | identity/authz | SPIRE v1.15.5 (SPIFFE spec: unversioned living spec) | Issues short-lived workload identities (SVIDs) to the process actually running, so identity is re-attested at the destination instead of copied. |
| [Open Policy Agent (OPA)](https://www.openpolicyagent.org/docs) | policy | v1.22.0 | Policy-as-code engine that can gate whether a handoff, tool call or destination is allowed. |
| [OpenTelemetry GenAI semantic conventions (incl. agent spans and MCP)](https://github.com/open-telemetry/semantic-conventions-genai/blob/main/docs/gen-ai/README.md) | observability | no tagged release in the new repository (main branch) | Defines agent, model, tool and MCP span attributes for correlating a task across agents, but names may still change. |
| [OpenTelemetry semantic conventions (core)](https://opentelemetry.io/docs/specs/semconv/) | observability | v1.44.0 | Core conventions (HTTP, RPC, Kubernetes) used to correlate the infrastructure side of a move. |
| [W3C Verifiable Credentials Data Model v2.0](https://www.w3.org/TR/vc-data-model-2.0/) | identity/authz | v2.0 | Format for signed, verifiable claims (e.g. delegated authority or attestation) that could travel with a task envelope. |
| [W3C Decentralized Identifiers (DIDs) v1.0 / v1.1](https://www.w3.org/TR/did-1.1/) | identity/authz | v1.0 (Recommendation); v1.1 (Candidate Recommendation Snapshot) | Identifier scheme for agents that is not tied to one provider; used by ANP (did:wba / did:web). |
| [Open Responses](https://www.openresponses.org/) | agent-to-model (API format) | no tagged release (main branch; last commit 2026-10-29) | Open multi-provider request/response format for model calls; it can reduce adapter work when a task changes model provider, but it carries no execution checkpoint, task ownership or authority. |
| [OpenEnv](https://huggingface.co/docs/openenv/index) | agent environments (training/evaluation) | v0.11.0 | Standard interface for agent environments; environment portability is not task-state continuity, but it is a candidate harness for a pinned, reproducible benchmark environment. |
| [OpenSandbox](https://github.com/opensandbox-group/OpenSandbox) | isolated execution | 1.2.0 (tag release-1.2.0) | Isolated execution environment for agents; a candidate destination sandbox, but sandbox isolation does not by itself fence effects or transfer authority. |
| [Kubernetes container checkpoint/restore (KEP-2008, KEP-5823)](https://github.com/kubernetes/enhancements/tree/master/keps/sig-node/5823-pod-level-checkpoint-restore) | deployment (process checkpoint) | KEP-2008 Forensic Container Checkpointing: beta since v1.30; KEP-5823 Pod-level Checkpoint/Restore: alpha targeted at v1.38 | First upstream Kubernetes restore path; process-level and same-runtime, so it moves bytes, not authorization or external effects. A baseline for, not a replacement of, application-level relocation. |
| [CRIU (Checkpoint/Restore In Userspace)](https://github.com/checkpoint-restore/criu) | deployment (process checkpoint) | v4.3 | Process-level checkpoint/restore baseline (same ISA and compatible kernel); carries no task authority, effect ledger or semantic state contract. |
| [SCITT architecture (RFC 9943) and COSE Receipts (RFC 9942)](https://www.rfc-editor.org/rfc/rfc9943) | provenance / transparency | RFC 9943; RFC 9942; SCRAPI draft-ietf-scitt-scrapi-11 | Standards-track substrate for signed statements and transparency receipts; a candidate profile for movement receipts, but a receipt still proves only what a signer registered, not that the statement is true. |
| [in-toto Attestation Framework](https://github.com/in-toto/attestation) | provenance / supply chain | v1.2.0 | DSSE-enveloped attestation format; a supply-chain-native alternative for signing movement evidence. |
| [Sigstore Rekor transparency log](https://blog.sigstore.dev/rekor-evolution/) | provenance / transparency | Rekor v1.5.5; rekor-tiles (Rekor v2) v2.4.0 | Witnessing/transparency reference for receipt chains; designs must not assume Rekor v2 tile proofs on the public-good instance. |
| [Restate](https://docs.restate.dev/concepts/durable_execution) | durability | v1.8.1 | Journaled invocations may be retried on another service instance of the same engine; recovery stays inside one engine, so it is not cross-runtime relocation. |
| [DBOS Transact (Python)](https://docs.dbos.dev/architecture) | durability | dbos 3.4.0 | Recovers an interrupted workflow 'to another healthy executor' of the same application; steps are retried until checkpointed, so external effects still need idempotency. |
| [IETF individual drafts on agent receipts and delegation chains](https://datatracker.ietf.org/doc/draft-nelson-agent-delegation-receipts/) | provenance / identity-authz | draft-nelson-agent-delegation-receipts-15; draft-niyikiza-oauth-attenuating-agent-tokens-02; draft-emirdag-scitt-ai-agent-execution-01; draft-mih-scitt-agent-action-capsule-05; draft-birkholz-verifiable-agent-conversations-01 | Closest proposals to this project's receipt and attenuated-delegation claims; compare against them explicitly, cite them as proposals, not standards. |

## Additional research candidates (242)

The next 16 categories cover a deliberately **broad discovery list**, with edition/status validation still required. A priority tier is a research classification, not a standard's maturity.


### Agent and application interoperability (14)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [JSON-RPC 2.0](https://www.jsonrpc.org/specification) | Core | Common typed request and error grammar | C2 C3 C4 C5 |
| [OpenAPI Specification 3.2.1](https://spec.openapis.org/oas/v3.2.1.html) | Core | Interoperable HTTP and tool interface descriptions | C2 C3 C4 C5 |
| [OpenAPI Arazzo](https://spec.openapis.org/arazzo/) | Conditional | Explicit API sequence and workflow descriptions | C2 C3 C4 C5 |
| [OpenAPI Overlay](https://spec.openapis.org/overlay/) | Watch | Annotate capability contracts without forking specifications | C2 C3 C4 C5 |
| [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest) | Conditional | Describe asynchronous sink and handoff messaging | C2 C3 C4 C5 |
| [CloudEvents](https://cloudevents.io/) | Core | Typed and transport-neutral transfer and withdrawal events | C2 C3 C4 C5 |
| [Protocol Buffers](https://protobuf.dev/programming-guides/proto3/) | Conditional | Portable schema-typed messages between runtime languages | C2 C3 C4 C5 |
| [gRPC](https://grpc.io/docs/what-is-grpc/introduction/) | Conditional | Typed service interfaces and remote invocation | C2 C3 C4 C5 |
| [GraphQL Specification](https://spec.graphql.org/) | Watch | Optional capability registry querying | C2 C3 C4 C5 |
| [Agent Client Protocol (Zed ACP)](https://agentclientprotocol.com/protocol/overview) | Watch | Editor to coding agent interface; different from archived IBM ACP | C2 C3 C4 C5 |
| [ActivityStreams 2.0](https://www.w3.org/TR/activitystreams-core/) | Watch | Federated activity representation for comparative research | C2 C3 C4 C5 |
| [ODRL Information Model 2.2](https://www.w3.org/TR/odrl-model/) | Conditional | Machine-readable policy expression candidate; needs separate enforcement | C2 C3 C4 C5 |
| [W3C Web of Things Thing Description 1.1](https://www.w3.org/TR/wot-thing-description11/) | Conditional | Describe device capabilities without conferring permission | C2 C3 C4 C5 |
| [W3C Web of Things Scripting API](https://www.w3.org/TR/wot-scripting-api/) | Watch | Emerging device gateway interface | C2 C3 C4 C5 |

### State encoding, portable contracts and data formats (17)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [JSON Schema 2020-12](https://json-schema.org/specification) | Core | Versioned and machine-validated handoff and capability envelopes | C1 C2 C3 C6 |
| [RFC 8259 JSON](https://www.rfc-editor.org/rfc/rfc8259) | Core | Syntax and interoperability boundaries of JSON documents | C1 C2 C3 C6 |
| [RFC 8785 JSON Canonicalization Scheme](https://www.rfc-editor.org/rfc/rfc8785) | Core | Stable bytes for cryptographic state and receipt signing | C1 C2 C3 C6 |
| [RFC 8949 CBOR](https://www.rfc-editor.org/rfc/rfc8949) | Conditional | Compact structured state and receipt representation | C1 C2 C3 C6 |
| [RFC 8610 CDDL](https://www.rfc-editor.org/rfc/rfc8610) | Conditional | Schema validation for CBOR transport profiles | C1 C2 C3 C6 |
| [RFC 6901 JSON Pointer](https://www.rfc-editor.org/rfc/rfc6901) | Conditional | Address fields in state and compatibility reports | C1 C2 C3 C6 |
| [RFC 6902 JSON Patch](https://www.rfc-editor.org/rfc/rfc6902) | Conditional | Express explicit, verifiable checkpoint updates | C1 C2 C3 C6 |
| [RFC 7396 JSON Merge Patch](https://www.rfc-editor.org/rfc/rfc7396) | Watch | Alternative merge semantics with deletion edge cases | C1 C2 C3 C6 |
| [RFC 9562 UUIDs](https://www.rfc-editor.org/rfc/rfc9562) | Core | Distinct persistent task and execution identifiers | C1 C2 C3 C6 |
| [RFC 3986 URI Generic Syntax](https://www.rfc-editor.org/rfc/rfc3986) | Core | Unique artifact and destination resource addressing | C1 C2 C3 C6 |
| [RFC 4648 Base-N Encodings](https://www.rfc-editor.org/rfc/rfc4648) | Conditional | Portable transport of binary digest material | C1 C2 C3 C6 |
| [RFC 7464 JSON Text Sequences](https://www.rfc-editor.org/rfc/rfc7464) | Watch | Stream append-only evidence records | C1 C2 C3 C6 |
| [JSON-LD 1.1](https://www.w3.org/TR/json-ld11/) | Conditional | Linked context for semantic evidence models | C1 C2 C3 C6 |
| [Apache Arrow Columnar Format](https://arrow.apache.org/docs/format/Columnar.html) | Watch | Tabular state artifact exchange for analytical tasks | C1 C2 C3 C6 |
| [Apache Parquet Format](https://parquet.apache.org/docs/file-format/) | Watch | Portable larger analytical data artifacts | C1 C2 C3 C6 |
| [Apache Avro](https://avro.apache.org/docs/current/specification/) | Watch | Schema-evolved durable event records | C1 C2 C3 C6 |
| [Semantic Versioning 2.0.0](https://semver.org/spec/v2.0.0.html) | Conditional | Version compatibility signaling for adapters | C1 C2 C3 C6 |

### Authentication, authorization, delegated authority (24)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [RFC 6749 OAuth 2.0 Authorization Framework](https://www.rfc-editor.org/rfc/rfc6749) | Core | Delegated API access and permission scoping | C1 C3 C4 C5 |
| [RFC 6750 OAuth 2.0 Bearer Token Usage](https://www.rfc-editor.org/rfc/rfc6750) | Core | Credential replay and copied bearer token risks | C1 C3 C4 C5 |
| [RFC 7009 OAuth Token Revocation](https://www.rfc-editor.org/rfc/rfc7009) | Core | Compare token revocation with independently observed sink closure | C1 C3 C4 C5 |
| [RFC 7662 OAuth Token Introspection](https://www.rfc-editor.org/rfc/rfc7662) | Core | Admission checks for current delegated access | C1 C3 C4 C5 |
| [RFC 7636 OAuth PKCE](https://www.rfc-editor.org/rfc/rfc7636) | Conditional | Secure authorization code exchange for interactive actors | C1 C3 C4 C5 |
| [RFC 8414 OAuth Authorization Server Metadata](https://www.rfc-editor.org/rfc/rfc8414) | Core | Identify and validate the grant issuer | C1 C3 C4 C5 |
| [RFC 8707 OAuth Resource Indicators](https://www.rfc-editor.org/rfc/rfc8707) | Core | Audience-bound tokens for tool sink and destination | C1 C3 C4 C5 |
| [RFC 8705 OAuth Mutual-TLS Client Authentication](https://www.rfc-editor.org/rfc/rfc8705) | Core | Sender-constrained workload grants | C1 C3 C4 C5 |
| [RFC 9449 OAuth DPoP](https://www.rfc-editor.org/rfc/rfc9449) | Core | Proof of possession limits replay at new executors | C1 C3 C4 C5 |
| [RFC 9700 OAuth 2.0 Security Best Current Practice](https://www.rfc-editor.org/rfc/rfc9700) | Core | Baseline authorization threat mitigations | C1 C3 C4 C5 |
| [RFC 9728 OAuth Protected Resource Metadata](https://www.rfc-editor.org/rfc/rfc9728) | Core | Secure discovery of protected tool resources | C1 C3 C4 C5 |
| [RFC 9207 OAuth Issuer Identification](https://www.rfc-editor.org/rfc/rfc9207) | Core | Issuer binding during multitenant or cross-domain handoff | C1 C3 C4 C5 |
| [RFC 9068 OAuth JWT Access Token Profile](https://www.rfc-editor.org/rfc/rfc9068) | Conditional | Interoperable audience and scope-bearing access tokens | C1 C3 C4 C5 |
| [RFC 8725 JWT Best Current Practices](https://www.rfc-editor.org/rfc/rfc8725) | Core | Prevent token-type and signing algorithm confusion | C1 C3 C4 C5 |
| [RFC 9126 OAuth Pushed Authorization Requests](https://www.rfc-editor.org/rfc/rfc9126) | Conditional | Protect interactive grant parameters | C1 C3 C4 C5 |
| [RFC 9101 JWT-Secured Authorization Requests](https://www.rfc-editor.org/rfc/rfc9101) | Conditional | Bound authentication request parameters | C1 C3 C4 C5 |
| [RFC 8628 OAuth Device Authorization Grant](https://www.rfc-editor.org/rfc/rfc8628) | Conditional | User-approved grants on devices with limited interfaces | C1 C3 C4 C5 |
| [RFC 8693 OAuth Token Exchange](https://www.rfc-editor.org/rfc/rfc8693) | Core | Exchange a credential for narrower downstream audience or actor | C1 C3 C4 C5 |
| [OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html) | Conditional | Federated human identity; not agent ownership semantics | C1 C3 C4 C5 |
| [OpenID Federation 1.0](https://openid.net/specs/openid-federation-1_0.html) | Watch | Federation and trust anchor metadata | C1 C3 C4 C5 |
| [SAML 2.0](https://docs.oasis-open.org/security/saml/v2.0/) | Watch | Enterprise federation; assertion not execution fencing | C1 C3 C4 C5 |
| [RFC 7643 SCIM Core Schema](https://www.rfc-editor.org/rfc/rfc7643) | Conditional | Provision identities for nonhuman service principals | C1 C3 C4 C5 |
| [RFC 7644 SCIM Protocol](https://www.rfc-editor.org/rfc/rfc7644) | Conditional | Identity deprovisioning and lifecycle management | C1 C3 C4 C5 |
| [NIST SP 800-162 ABAC](https://csrc.nist.gov/pubs/sp/800/162/upd2/final) | Conditional | Attribute-driven movement admission and effect policy | C1 C3 C4 C5 |

### Cryptographic protection and verifiable credentials (18)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [RFC 7515 JSON Web Signature](https://www.rfc-editor.org/rfc/rfc7515) | Core | Signed grants, handoff statements and receipts | C4 C5 C6 |
| [RFC 7516 JSON Web Encryption](https://www.rfc-editor.org/rfc/rfc7516) | Conditional | Protect sensitive task context sent to a destination | C4 C5 C6 |
| [RFC 7517 JSON Web Key](https://www.rfc-editor.org/rfc/rfc7517) | Core | Represent verification keys and key identifiers | C4 C5 C6 |
| [RFC 7519 JSON Web Token](https://www.rfc-editor.org/rfc/rfc7519) | Core | Signed attribute-carrying claims | C4 C5 C6 |
| [RFC 8392 CBOR Web Token](https://www.rfc-editor.org/rfc/rfc8392) | Conditional | Compact constrained-device claims | C4 C5 C6 |
| [RFC 9052 COSE Structures and Process](https://www.rfc-editor.org/rfc/rfc9052) | Core | Compact machine-verifiable evidence objects | C4 C5 C6 |
| [RFC 9053 COSE Initial Algorithms](https://www.rfc-editor.org/rfc/rfc9053) | Conditional | Interoperable signatures and encrypted envelopes | C4 C5 C6 |
| [RFC 9180 Hybrid Public Key Encryption](https://www.rfc-editor.org/rfc/rfc9180) | Conditional | Destination-key encrypted handoff artifacts | C4 C5 C6 |
| [RFC 8446 TLS 1.3](https://www.rfc-editor.org/rfc/rfc8446) | Core | Secure authenticated cross-runtime transport | C4 C5 C6 |
| [RFC 5280 X.509 PKI Certificate Profile](https://www.rfc-editor.org/rfc/rfc5280) | Core | Certificate chain validation for peer identities | C4 C5 C6 |
| [RFC 3161 Time-Stamp Protocol](https://www.rfc-editor.org/rfc/rfc3161) | Conditional | Trusted timestamps for evidence sequencing | C4 C5 C6 |
| [RFC 6960 Online Certificate Status Protocol](https://www.rfc-editor.org/rfc/rfc6960) | Conditional | Certificate status and revocation information | C4 C5 C6 |
| [RFC 9162 Certificate Transparency v2](https://www.rfc-editor.org/rfc/rfc9162) | Conditional | Append-only transparency and equivocation threats | C4 C5 C6 |
| [W3C Verifiable Credential Data Integrity 1.0](https://www.w3.org/TR/vc-data-integrity/) | Conditional | Credential integrity and controller proofs | C4 C5 C6 |
| [W3C Bitstring Status List 1.0](https://www.w3.org/TR/vc-bitstring-status-list/) | Conditional | Credential revocation/suspension signals | C4 C5 C6 |
| [W3C Controlled Identifiers 1.0](https://www.w3.org/TR/cid-1.0/) | Conditional | Verification-method and key controller relationship | C4 C5 C6 |
| [NIST FIPS 186-5 Digital Signature Standard](https://csrc.nist.gov/pubs/fips/186-5/final) | Conditional | Signature algorithm assurance baseline | C4 C5 C6 |
| [NIST SP 800-57 Key Management](https://csrc.nist.gov/pubs/sp/800/57/pt1/r5/final) | Conditional | Key rotation and compromise recovery | C4 C5 C6 |

### Network transport, event messaging and discovery (15)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [RFC 9110 HTTP Semantics](https://www.rfc-editor.org/rfc/rfc9110) | Core | Separate successful request processing from external effect commitment | C2 C3 C5 C7 |
| [RFC 9112 HTTP/1.1](https://www.rfc-editor.org/rfc/rfc9112) | Conditional | Base interoperable peer messaging transport | C2 C3 C5 C7 |
| [RFC 9113 HTTP/2](https://www.rfc-editor.org/rfc/rfc9113) | Conditional | Multiplexing and transport framing for remote services | C2 C3 C5 C7 |
| [RFC 9114 HTTP/3](https://www.rfc-editor.org/rfc/rfc9114) | Watch | Transport network migration is not ownership migration | C2 C3 C5 C7 |
| [RFC 9000 QUIC](https://www.rfc-editor.org/rfc/rfc9000) | Conditional | Resilient connection movement across network paths | C2 C3 C5 C7 |
| [RFC 6455 WebSocket](https://www.rfc-editor.org/rfc/rfc6455) | Conditional | Bidirectional agent progress and control channel | C2 C3 C5 C7 |
| [HTML Server-Sent Events](https://html.spec.whatwg.org/multipage/server-sent-events.html) | Conditional | Server-to-client progress stream; replay needs application durability | C2 C3 C5 C7 |
| [RFC 9293 TCP](https://www.rfc-editor.org/rfc/rfc9293) | Watch | Transport failure and connection lifecycle assumptions | C2 C3 C5 C7 |
| [RFC 1034 DNS](https://www.rfc-editor.org/rfc/rfc1034) | Watch | Resource and destination naming | C2 C3 C5 C7 |
| [RFC 6763 DNS-SD](https://www.rfc-editor.org/rfc/rfc6763) | Conditional | Endpoint discovery without security claims | C2 C3 C5 C7 |
| [RFC 6762 mDNS](https://www.rfc-editor.org/rfc/rfc6762) | Watch | LAN local discovery with identity caveats | C2 C3 C5 C7 |
| [MQTT 5.0](https://mqtt.org/mqtt-specification/) | Conditional | Edge gateway messaging and QoS fault model | C2 C3 C5 C7 |
| [AMQP 1.0](https://www.oasis-open.org/standard/amqp/) | Conditional | Durable brokered event routing | C2 C3 C5 C7 |
| [RFC 7252 CoAP](https://www.rfc-editor.org/rfc/rfc7252) | Conditional | Constrained read-only device gateway interface | C2 C3 C5 C7 |
| [WebRTC 1.0](https://www.w3.org/TR/webrtc/) | Watch | Optional browser-edge peer data channels | C2 C3 C5 C7 |

### Provenance, attestation and supply-chain evidence (12)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [W3C PROV-DM](https://www.w3.org/TR/prov-dm/) | Core | Structure task and agent causal lineage | C2 C4 C6 |
| [W3C PROV-O](https://www.w3.org/TR/prov-o/) | Core | Interoperable machine-readable provenance relationships | C2 C4 C6 |
| [W3C Trace Context](https://www.w3.org/TR/trace-context/) | Core | Correlate operations across services; not an independent proof | C2 C4 C6 |
| [W3C Baggage](https://www.w3.org/TR/baggage/) | Conditional | Propagate diagnostic context with strict privacy constraints | C2 C4 C6 |
| [SLSA v1.2](https://slsa.dev/spec/v1.2/) | Conditional | Assure provenance of software packages and containers | C2 C4 C6 |
| [SPDX Specification](https://spdx.github.io/spdx-spec/) | Conditional | Component licenses and software bill of materials | C2 C4 C6 |
| [CycloneDX Specification](https://cyclonedx.org/specification/overview/) | Conditional | Portable software component inventory | C2 C4 C6 |
| [NIST SP 800-218 SSDF](https://csrc.nist.gov/pubs/sp/800/218/final) | Conditional | Secure delivery practices for movable software components | C2 C4 C6 |
| [Sigstore Bundle Format](https://docs.sigstore.dev/about/bundle/) | Conditional | Offline verification of signing evidence | C2 C4 C6 |
| [OpenSSF Security Scorecard](https://securityscorecards.dev/) | Watch | Repository hygiene indicators; not certification | C2 C4 C6 |
| [RFC 9921 COSE Timestamping](https://www.rfc-editor.org/rfc/rfc9921) | Watch | Crypto timestamp evidence design | C2 C4 C6 |
| [RFC 9995 COSE Hash Envelope](https://www.rfc-editor.org/rfc/rfc9995) | Watch | Hash binding candidate for receipt payloads; verify RFC metadata | C2 C4 C6 |

### Published ISO/IEC artificial-intelligence standards (38)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [ISO/IEC 22989:2022 AI terminology](https://www.iso.org/committee/6794475/x/catalogue/) | Core | Common AI lifecycle and model terms | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 23053:2022 Framework for ML AI systems](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Decompose task and model/runtime state | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 23894:2023 AI risk management](https://www.iso.org/committee/6794475/x/catalogue/) | Core | Risk evaluation for relocation decisions | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 42001:2023 AI management systems](https://www.iso.org/standard/42001) | Core | Govern AI control responsibilities | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 42005:2025 AI impact assessment](https://www.iso.org/committee/6794475/x/catalogue/) | Core | Assess impact of autonomous movement decisions | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 42006:2025 Certification bodies for AI management systems](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Distinguish independent certification from prototype evidence | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 38507:2022 Governance implications of AI](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Enterprise accountability and oversight | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 5338:2023 AI system lifecycle processes](https://www.iso.org/standard/81118.html) | Core | Define lifecycle stages for movement and retirement | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 5339:2024 Guidance for AI applications](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Application-level documentation and boundaries | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 5392:2024 Knowledge engineering reference architecture](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Semantic knowledge-state interoperability | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TR 5469:2024 AI and functional safety](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Risk of AI integrated with industrial control | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TS 6254:2025 AI explainability](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Explain a decision to move or refuse | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 8183:2023 AI data lifecycle](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | State retention, consent and deletion | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TS 8200:2024 AI controllability](https://www.iso.org/committee/6794475/x/catalogue/) | Core | Intervention, stopping and authority withdrawal | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TS 12791:2024 ML bias treatment](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Destination-dependent bias analysis | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 12792:2025 AI transparency taxonomy](https://www.iso.org/committee/6794475/x/catalogue/) | Core | Specify evidence disclosure and limitation categories | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TR 17903:2024 Computing devices for ML](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Destination compute hardware compatibility | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TR 20226:2025 AI sustainability](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Energy and environmental placement impacts | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TR 21221:2025 Beneficial AI systems](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Human impact of autonomy decisions | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TR 24027:2021 AI bias](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Bias risk during delegation or placement | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TR 24028:2020 AI trustworthiness](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Trust assumptions and assurance boundaries | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TR 24029-1:2021 Neural network robustness](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Robustness evaluations for model-backed work | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 24029-2:2023 Neural network robustness formal methods](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Limit formal claims about learned models | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TR 24030:2024 AI use cases](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Document representative deployment scenarios | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TR 24368:2022 AI ethics and societal concerns](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Responsible agent autonomy research framing | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TR 24372:2021 AI computational approaches](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Classify computation and state portability | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 25059:2023 AI system quality model](https://www.iso.org/committee/6794475/x/catalogue/) | Core | System quality metrics beyond task success | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TS 25058:2024 AI quality evaluation](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Evaluation methodology and evidence reporting | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 42106:2026 AI system benchmarking](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Fair outcome-focused mobility comparisons; verify edition and title | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TS 42112:2026 ML training efficiency](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Resource tradeoff benchmark scope | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TS 42119-2:2025 AI system testing](https://www.iso.org/committee/6794475/x/catalogue/) | Core | Design testable quality and failure requirements | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 5259-1:2024 ML data quality terminology](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Quality of transported state and context | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 5259-2:2024 ML data quality measures](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Measure fidelity and loss after handoff | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 5259-3:2024 ML data quality management](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Data-quality management policy | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 5259-4:2024 ML data quality process](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Operationalize state data checks | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC 5259-5:2025 ML data quality governance](https://www.iso.org/committee/6794475/x/catalogue/) | Conditional | Govern state data ownership and lifecycle | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TR 5259-6:2026 Data quality visualization](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Analyze missing or altered transfer state | C1 C2 C3 C4 C6 C7 |
| [ISO/IEC TS 4213:2022 ML classification quality](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Optional classification assessment metrics | C1 C2 C3 C4 C6 C7 |

### Emerging ISO/IEC AI projects — NOT published standards (8)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [ISO/IEC FDIS 24970 AI system logging](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Monitor future agent event logging criteria | C2 C4 C6 C7 |
| [ISO/IEC FDIS 42105 Human oversight of AI](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Monitor human authorization guidance | C2 C4 C6 C7 |
| [ISO/IEC DTS 42119-3 AI verification and validation](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Monitor evolving verification methodology | C2 C4 C6 C7 |
| [ISO/IEC AWI TS 42119-7 AI red teaming](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Monitor systematic adverse-agent evaluation | C2 C4 C6 C7 |
| [ISO/IEC WD TS 25570 AI reliability](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Monitor resilient autonomy measures | C2 C4 C6 C7 |
| [ISO/IEC AWI TS 25864 AI resilience](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Monitor new recovery and resilience design | C2 C4 C6 C7 |
| [ISO/IEC CD 25589 Human-machine teaming](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Monitor division of human and agent authority | C2 C4 C6 C7 |
| [ISO/IEC AWI 25870 AI incident reporting](https://www.iso.org/committee/6794475/x/catalogue/) | Watch | Monitor incident evidence reporting rules | C2 C4 C6 C7 |

### NIST, IEEE, OWASP and security research frameworks (17)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [NIST AI Risk Management Framework 1.0](https://www.nist.gov/itl/ai-risk-management-framework) | Core | Risk governance of agent decision and effect authority | C1 C4 C6 C7 |
| [NIST AI 600-1 Generative AI Profile](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence) | Core | Generative model and agent-specific risk management | C1 C4 C6 C7 |
| [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework) | Conditional | Operational security management and recovery | C1 C4 C6 C7 |
| [NIST SP 800-207 Zero Trust Architecture](https://csrc.nist.gov/pubs/sp/800/207/final) | Core | Continuous revalidation at movement boundaries | C1 C4 C6 C7 |
| [NIST SP 800-53 Security and Privacy Controls](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) | Conditional | Controls for endpoints, secrets and audit stores | C1 C4 C6 C7 |
| [NIST SP 800-63-4 Digital Identity Guidelines](https://csrc.nist.gov/pubs/sp/800/63/4/final) | Core | Identity strength and authentication requirements | C1 C4 C6 C7 |
| [OWASP Top 10 for Agentic Applications 2026](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/) | Core | Threat classification for malicious agent collaboration | C1 C4 C6 C7 |
| [OWASP Top 10 for LLM Applications 2025](https://genai.owasp.org/llmrisk/) | Conditional | Model injection and excessive agency attack classes | C1 C4 C6 C7 |
| [MITRE ATLAS](https://atlas.mitre.org/) | Conditional | Adversarial machine learning threat mapping | C1 C4 C6 C7 |
| [MITRE ATT&CK](https://attack.mitre.org/) | Conditional | Host compromise and credential theft adversary patterns | C1 C4 C6 C7 |
| [IEEE 7000-2021 Ethical design process](https://standards.ieee.org/initiatives/autonomous-intelligence-systems/standards/) | Conditional | Ethical and stakeholder impact records | C1 C4 C6 C7 |
| [IEEE 7001-2021 Autonomous systems transparency](https://standards.ieee.org/initiatives/autonomous-intelligence-systems/standards/) | Core | Observable authorized movement disclosures | C1 C4 C6 C7 |
| [IEEE 7002-2022 Data privacy process](https://standards.ieee.org/initiatives/autonomous-intelligence-systems/standards/) | Conditional | Privacy of transmitted task context | C1 C4 C6 C7 |
| [IEEE 7003-2024 Algorithmic bias](https://standards.ieee.org/initiatives/autonomous-intelligence-systems/standards/) | Conditional | Unfair destination or agent selection | C1 C4 C6 C7 |
| [IEEE 7007-2021 Ontology for ethical robotics](https://standards.ieee.org/initiatives/autonomous-intelligence-systems/standards/) | Watch | Ethical interoperability with embodied agents | C1 C4 C6 C7 |
| [IEEE 7009-2024 Fail-safe autonomous systems](https://standards.ieee.org/initiatives/autonomous-intelligence-systems/standards/) | Core | Safe refusal and fail-closed behavior | C1 C4 C6 C7 |
| [IEEE 7010-2020 Human well-being impact assessment](https://standards.ieee.org/initiatives/autonomous-intelligence-systems/standards/) | Watch | Human and societal impact of autonomous movements | C1 C4 C6 C7 |

### ISO/IEC information security, identity and privacy (16)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [ISO/IEC 27001:2022 ISMS](https://www.iso.org/standard/27001) | Core | Govern security for hosts that run and move agents | C1 C3 C4 C6 |
| [ISO/IEC 27002 Security controls](https://www.iso.org/committee/45306/x/catalogue/) | Conditional | Reference controls for permissions and key custody | C1 C3 C4 C6 |
| [ISO/IEC 27005 Security risk management](https://www.iso.org/committee/45306/x/catalogue/) | Conditional | Assess movement-specific risks | C1 C3 C4 C6 |
| [ISO/IEC 27017 Cloud security controls](https://www.iso.org/committee/45306/x/catalogue/) | Conditional | Cloud executor isolation and provider responsibilities | C1 C3 C4 C6 |
| [ISO/IEC 27018 Cloud PII protection](https://www.iso.org/committee/45306/x/catalogue/) | Conditional | Protect personal data at remote executors | C1 C3 C4 C6 |
| [ISO/IEC 27701 Privacy information management](https://www.iso.org/committee/45306/x/catalogue/) | Conditional | Privacy process for transferred context | C1 C3 C4 C6 |
| [ISO/IEC 27035 Incident management](https://www.iso.org/committee/45306/x/catalogue/) | Conditional | Investigate unintended movement and effect incidents | C1 C3 C4 C6 |
| [ISO/IEC 27036 Supplier relationship security](https://www.iso.org/committee/45306/x/catalogue/) | Watch | Assess independent vendor executor trust | C1 C3 C4 C6 |
| [ISO/IEC 27034 Application security](https://www.iso.org/committee/45306/x/catalogue/) | Conditional | Secure development for agent ingress and egress | C1 C3 C4 C6 |
| [ISO/IEC 27090:2026 AI security threats](https://committee.iso.org/standard/27090) | Core | AI-specific attacks across system lifecycle | C1 C3 C4 C6 |
| [ISO/IEC FDIS 27091 AI privacy protection](https://www.iso.org/committee/45306/x/catalogue/) | Watch | Proposed AI privacy guidance; not final | C1 C3 C4 C6 |
| [ISO/IEC 29100 Privacy framework](https://www.iso.org/committee/45306/x/catalogue/) | Conditional | Data minimization and purpose limitation | C1 C3 C4 C6 |
| [ISO/IEC 24760-1:2025 Identity framework and terminology](https://www.iso.org/committee/45306/x/catalogue/) | Core | Distinguish principal and runtime identity | C1 C3 C4 C6 |
| [ISO/IEC 24760-2:2025 Identity architecture](https://www.iso.org/committee/45306/x/catalogue/) | Conditional | Model verification and enrollment of principals | C1 C3 C4 C6 |
| [ISO/IEC 15408 Common Criteria](https://www.iso.org/committee/45306/x/catalogue/) | Watch | Methodology for future assurance profiles | C1 C3 C4 C6 |
| [ISO/IEC 18045 IT security evaluation methodology](https://www.iso.org/committee/45306/x/catalogue/) | Watch | Evaluation methods for certified targets | C1 C3 C4 C6 |

### Software quality, lifecycle and assurance (12)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [ISO/IEC 25010 System and software quality model](https://www.iso.org/) | Core | Reliability and quality criteria for continuation | C1 C2 C3 C4 C6 |
| [ISO/IEC 25012 Data quality model](https://www.iso.org/) | Conditional | Measure meaning and completeness of moved state | C1 C2 C3 C4 C6 |
| [ISO/IEC/IEEE 12207 Software lifecycle processes](https://www.iso.org/) | Conditional | Maintain safe adapter development process | C1 C2 C3 C4 C6 |
| [ISO/IEC/IEEE 15288 System lifecycle processes](https://www.iso.org/) | Conditional | Model handoff as a system-of-systems transition | C1 C2 C3 C4 C6 |
| [ISO/IEC/IEEE 29119 Software testing series](https://www.iso.org/) | Conditional | Document repeatable adversarial test methods | C1 C2 C3 C4 C6 |
| [ISO/IEC/IEEE 29148 Requirements engineering](https://www.iso.org/) | Conditional | Falsifiable handoff acceptance criteria | C1 C2 C3 C4 C6 |
| [IEEE 1012 Verification and Validation](https://standards.ieee.org/) | Conditional | Independent validation discipline | C1 C2 C3 C4 C6 |
| [ISO 9001 Quality management systems](https://www.iso.org/) | Watch | Organizational quality process for later commercialization | C1 C2 C3 C4 C6 |
| [ISO/IEC 20000-1 IT service management](https://www.iso.org/) | Watch | Future operational service management | C1 C2 C3 C4 C6 |
| [ISO 22301 Business continuity](https://www.iso.org/) | Conditional | Recovery and service restoration objectives | C1 C2 C3 C4 C6 |
| [ISO 31000 Risk management](https://www.iso.org/) | Watch | High-level risk and tradeoff framework | C1 C2 C3 C4 C6 |
| [OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/) | Conditional | Web/API security controls for gateways | C1 C2 C3 C4 C6 |

### Cloud, edge, WebAssembly and hardware attestation (12)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [Container Storage Interface (CSI)](https://github.com/container-storage-interface/spec) | Conditional | Storage driver portability, not logical task continuity | C2 C3 C4 C5 C7 |
| [Container Network Interface (CNI)](https://github.com/containernetworking/cni) | Conditional | Network plugin contracts, not agent authorization | C2 C3 C4 C5 C7 |
| [WebAssembly Core Specification](https://webassembly.github.io/spec/core/) | Conditional | Portable code modules; checkpoint semantics remain separate | C2 C3 C4 C5 C7 |
| [WebAssembly Component Model](https://component-model.bytecodealliance.org/) | Conditional | Typed interface composition for portable agent tools | C2 C3 C4 C5 C7 |
| [WASI Preview 2](https://wasi.dev/) | Conditional | Sandboxed host capability interfaces | C2 C3 C4 C5 C7 |
| [WebAssembly Interface Types (WIT)](https://component-model.bytecodealliance.org/design/wit.html) | Conditional | Typed component interface and compatibility checks | C2 C3 C4 C5 C7 |
| [RFC 9334 RATS Architecture](https://www.rfc-editor.org/rfc/rfc9334) | Conditional | Verify remote host/device state before admitting authority | C2 C3 C4 C5 C7 |
| [Trusted Computing Group TPM 2.0 Library](https://trustedcomputinggroup.org/resource/tpm-library-specification/) | Conditional | Hardware-rooted measurement and signing key protection | C2 C3 C4 C5 C7 |
| [DMTF Redfish](https://www.dmtf.org/standards/redfish) | Watch | Device inventory, health and firmware management | C2 C3 C4 C5 C7 |
| [ETSI MEC 003 Edge Framework](https://www.etsi.org/technologies/multi-access-edge-computing) | Watch | Edge application placement and platform semantics | C2 C3 C4 C5 C7 |
| [ETSI MEC 011 Application Enablement](https://www.etsi.org/technologies/multi-access-edge-computing) | Watch | Edge service lifecycle and discovery candidate | C2 C3 C4 C5 C7 |
| [3GPP TS 23.548 Edge Computing](https://www.3gpp.org/technologies/edge-computing) | Watch | Mobile edge application mobility implications | C2 C3 C4 C5 C7 |

### Robotics, OT/ICS and functional safety (17)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [OMG DDS 1.4](https://www.omg.org/spec/DDS/) | Conditional | ROS 2 style middleware data distribution | C3 C4 C5 C7 |
| [OMG DDS Security 1.2](https://www.omg.org/spec/DDS-SECURITY/) | Core | Robot topic identity and access control | C3 C4 C5 C7 |
| [OMG DDSI-RTPS 2.5](https://www.omg.org/spec/DDSI-RTPS/) | Conditional | Wire compatibility for distributed robotic data | C3 C4 C5 C7 |
| [OMG DDS-XRCE 1.0](https://www.omg.org/spec/DDS-XRCE/) | Watch | Extremely constrained robot/microcontroller links | C3 C4 C5 C7 |
| [OMG DDS-TSN 1.0](https://www.omg.org/spec/DDS-TSN/) | Watch | Time-sensitive robot networking | C3 C4 C5 C7 |
| [IEC 62541 OPC UA](https://opcfoundation.org/about/opc-technologies/opc-ua/) | Conditional | Mediated industrial equipment interoperability | C3 C4 C5 C7 |
| [IEC 61508 Functional Safety](https://webstore.iec.ch/) | Core | Independent safe-state and hazard controls | C3 C4 C5 C7 |
| [ISA/IEC 62443 Industrial Automation Security](https://www.isa.org/standards-and-publications/isa-standards/isa-iec-62443-series-of-standards) | Core | OT network zones and least privilege | C3 C4 C5 C7 |
| [ISO 10218-1:2025 Industrial robot safety](https://www.iso.org/sectors/engineering/robotics) | Conditional | Safety constraints for robot hardware | C3 C4 C5 C7 |
| [ISO 10218-2:2025 Robot cell safety](https://www.iso.org/sectors/engineering/robotics) | Conditional | System integration requirements for robot cells | C3 C4 C5 C7 |
| [ISO/TS 15066 Collaborative robots](https://www.iso.org/sectors/engineering/robotics) | Conditional | Human robot interaction safety guidance | C3 C4 C5 C7 |
| [ISO 13482 Personal care robot safety](https://www.iso.org/sectors/engineering/robotics) | Conditional | Service robot user protection | C3 C4 C5 C7 |
| [ISO 3691-4 Driverless industrial trucks](https://www.iso.org/) | Conditional | Automated mobile vehicle safety | C3 C4 C5 C7 |
| [ISO 12100 Machinery risk assessment](https://www.iso.org/) | Core | Hazard analysis before physical actuation | C3 C4 C5 C7 |
| [ISO 13849-1 Safety-related controls](https://www.iso.org/) | Conditional | Separate safety control from AI decision code | C3 C4 C5 C7 |
| [IEC 62061 Machinery functional safety](https://webstore.iec.ch/) | Conditional | Electrical safety controller assurance | C3 C4 C5 C7 |
| [ROS 2 REP-2004 Package quality levels](https://www.ros.org/reps/rep-2004.html) | Conditional | ROS adapter dependency quality criteria | C3 C4 C5 C7 |

### European legal and regulatory instruments — NOT technical standards (9)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [EU AI Act Regulation 2024/1689](https://eur-lex.europa.eu/eli/reg/2024/1689) | Core | Applicability of AI governance, high-risk and transparency obligations | C4 C6 C7 |
| [EU GDPR Regulation 2016/679](https://eur-lex.europa.eu/eli/reg/2016/679/oj) | Core | Lawful processing and cross-organization personal data transfer | C4 C6 C7 |
| [EU NIS2 Directive 2022/2555](https://eur-lex.europa.eu/eli/dir/2022/2555/oj) | Conditional | Cybersecurity duties when provider/organization is in scope | C4 C6 C7 |
| [EU DORA Regulation 2022/2554](https://eur-lex.europa.eu/eli/reg/2022/2554/oj) | Watch | Digital operational resilience in financial-sector deployments | C4 C6 C7 |
| [EU eIDAS Regulation 910/2014 amended by 2024/1183](https://eur-lex.europa.eu/eli/reg/2024/1183/oj) | Conditional | Electronic identity and trust services | C4 C6 C7 |
| [EU Data Act Regulation 2023/2854](https://eur-lex.europa.eu/eli/reg/2023/2854/oj) | Watch | Data access and switching requirements if applicable | C4 C6 C7 |
| [EU Cyber Resilience Act Regulation 2024/2847](https://eur-lex.europa.eu/eli/reg/2024/2847/oj) | Conditional | Cybersecurity requirements for applicable commercial products | C4 C6 C7 |
| [EU Machinery Regulation 2023/1230](https://eur-lex.europa.eu/eli/reg/2023/1230/oj) | Conditional | Physical machinery integration and safety obligations | C4 C6 C7 |
| [EU Product Liability Directive 2024/2853](https://eur-lex.europa.eu/eli/dir/2024/2853/oj) | Watch | Liability for eligible products and software | C4 C6 C7 |

### Emerging agent attestations and IETF draft proposals (7)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [draft-bailey-scitt-agent-session-receipt](https://datatracker.ietf.org/doc/draft-bailey-scitt-agent-session-receipt/) | Watch | Candidate event-level agent receipt format | C4 C5 C6 |
| [draft-raskar-scitt-agent-provenance](https://datatracker.ietf.org/doc/draft-raskar-scitt-agent-provenance/) | Watch | Candidate portable agent provenance profile | C4 C5 C6 |
| [draft-emirdag-scitt-ai-agent-execution](https://datatracker.ietf.org/doc/draft-emirdag-scitt-ai-agent-execution/) | Watch | Candidate AI agent execution attestation profile | C4 C5 C6 |
| [draft-birkholz-verifiable-agent-conversations](https://datatracker.ietf.org/doc/draft-birkholz-verifiable-agent-conversations/) | Watch | Candidate verifiable conversation evidence | C4 C5 C6 |
| [draft-mih-sokolov-scitt-payload-binding](https://datatracker.ietf.org/doc/draft-mih-sokolov-scitt-payload-binding/) | Watch | Candidate statement payload canonicalization | C4 C5 C6 |
| [draft-ietf-scitt-scrapi](https://datatracker.ietf.org/doc/draft-ietf-scitt-scrapi/) | Watch | SCITT WG transparency service API draft | C4 C5 C6 |
| [draft-ietf-scitt-receipts-ccf-profile](https://datatracker.ietf.org/doc/draft-ietf-scitt-receipts-ccf-profile/) | Watch | SCITT WG receipt profile draft | C4 C5 C6 |

### Research rigor, reproducibility and benchmarking practices (6)

| Reference and source | Research priority | Relevance | Research tracks |
| --- | --- | --- | --- |
| [ACM Artifact Review and Badging](https://www.acm.org/publications/policies/artifact-review-and-badging-current) | Core | Reproducibility and independent artifact evaluation | C1 C2 C3 C6 C7 |
| [PRISMA 2020 Reporting Guideline](https://www.prisma-statement.org/prisma-2020) | Conditional | Transparent literature screening and synthesis | C1 C2 C3 C6 C7 |
| [FAIR Guiding Principles](https://www.go-fair.org/fair-principles/) | Conditional | Responsible shareable experiment and artifact metadata | C1 C2 C3 C6 C7 |
| [MLCommons MLPerf Inference](https://mlcommons.org/benchmarks/inference/) | Watch | Optional hardware and inference cost comparisons | C1 C2 C3 C6 C7 |
| [MLCommons MLPerf Training](https://mlcommons.org/benchmarks/training/) | Watch | Optional model training performance context | C1 C2 C3 C6 C7 |
| [NIST AI Test Evaluation Validation and Verification](https://www.nist.gov/artificial-intelligence) | Conditional | Experimental test and evaluation design | C1 C2 C3 C6 C7 |

## Verification and maintenance gates

Before using a reference in architecture decisions, academic claims, certification mappings or legal/compliance evaluations:

1. Follow the issuing body's **official** page. Confirm the **exact number, title, part, edition, amendments, publication or withdrawal status and current revision**, and record the checked date.
2. Identify whether it is a published standard/RFC, industry protocol, Internet-Draft, guidance, research practice or legislation; do not assign normative force to a draft.
3. Check official scope and applicability rather than assuming every AI project, industry or jurisdiction needs conformance.
4. De-duplicate references across categories **without erasing** historical provenance; use a crosswalk if merging IDs.
5. Map each selected reference to a precisely scoped requirement, implementation boundary, independent test and evidence artifact, including negative/unknown outcomes.
6. Avoid reproducing copyrighted ISO/IEC/IEEE specifications; link legitimate primary landing pages.
7. Keep private source work, unpublished results, secrets, commercial details and personal information out of this public repository.

For a full issue/verification checklist, see [verification backlog](agent-movement-verification.md). The register does **not** modify the source research project or imply it has adopted any new standard.

