# KubeIntellect — comprehensive standards and applicability register

**Related project:** [MSKazemi/kubeintellect](https://github.com/MSKazemi/kubeintellect) (current published v4 platform).  
**Maintained in:** [MSKazemi/standards](https://github.com/MSKazemi/standards).  
**Researched:** 2026-11-21 (Europe/Rome).  
**Verification state:** discovery and applicability register; not a claim of certification, implementation or complete edition verification.  
**Inventory:** 239 references across 11 categories. [Machine-readable catalogue](../data/kubeintellect-standards.csv).

## How to use this inventory

References are grouped by **project research relevance**, not by a mandatory conformance obligation. A publisher link can lead to a search or catalogue page rather than an exact edition; the CSV labels that distinction. A standard cited with a reported year is not automatically the newest/current version. Only individually checked items have a verification date. ISO/IEC text and proprietary security benchmark text are *not* reproduced here.

- **Core**: directly useful to current KubeIntellect v4 security, agent governance, Kubernetes operations, evidence or release assurance.
- **Targeted**: valuable next for the current feature or integration roadmap.
- **Conditional**: applicable only if a feature, sector, deployment or contractual scope calls for it.
- **Watch**: draft, speculative or future/adjacent work.
- **Scope-check**: legal and regulatory applicability must be assessed by organization role, jurisdiction and intended use.

**Normative status matters:** an ISO/IEC published standard, IETF RFC, W3C Recommendation, community protocol, OWASP security guide, emerging draft, and EU law are not interchangeable. Listing a standard does not authorize a feature change or constitute certification. Regulatory dates or edition numbers must be checked against official issuing sources before external claims.

## Highest-leverage baseline

| Reference | Why it belongs in the baseline |
| --- | --- |
| ISO/IEC 42001, 23894, 42005 | AI management, impact and risk treatment |
| ISO/IEC 27001, 27002, 27090 | Information security and AI-specific security risks |
| NIST AI RMF 1.0, NIST AI 600-1 | Model- and agent-specific risk assessments |
| OWASP Agentic Top 10, OWASP LLM Top 10, OWASP ACS | Agent misuse, prompt injection and runtime policy |
| NIST SP 800-190, CIS Kubernetes, Pod Security Standards | Kubernetes/container security baseline |
| NIST SSDF, SLSA, SPDX/CycloneDX, Sigstore | Source, build, artifact and dependency evidence |
| RFC 8693, 8785, 9942, 9943, W3C PROV | Narrow authority, canonical actions, verifiable operation evidence |
| MCP, A2A, AG-UI, OpenAPI, OpenTelemetry | Tool interoperability, agent collaboration and human-operated control |
| GDPR, EU AI Act and CRA (scope dependent) | Privacy, AI governance and product security legal assessment |

## Product applicability

KubeIntellect provides conversational Kubernetes diagnosis, agent-managed reads and guarded human-approved changes. Potential control surfaces include the LLM planner, tool dispatch, authorization and approvals, Kubernetes API access, evidence and audit, memory, observability, deployment and CI/CD. Use [the traceability and research recommendations](kubeintellect-traceability.md) for implementation-level planning and test design. The actual KubeIntellect implementation and its tests remain authoritative in [its public repository](https://github.com/MSKazemi/kubeintellect). This document does **not** import private code or research.

---

## AI governance, quality and responsible automation (28)

| Reference (official publisher link) | Type | Reported edition | Relevance | KubeIntellect application |
| --- | --- | --- | --- | --- |
| [ISO/IEC 42001](https://www.iso.org/search.html?q=ISO%2FIEC%2042001) | international standard | 2023 | Core | AI management system responsibilities and lifecycle governance |
| [ISO/IEC 23894](https://www.iso.org/search.html?q=ISO%2FIEC%2023894) | international standard | 2023 | Core | Risk identification assessment and treatment for AI |
| [ISO/IEC 42005](https://www.iso.org/search.html?q=ISO%2FIEC%2042005) | international standard | 2025 | Core | Impact assessment for AI-enabled cluster operations |
| [ISO/IEC 27090](https://committee.iso.org/standard/27090) | international standard | 2026 | Core | AI-specific cybersecurity threats and compromises |
| [ISO/IEC 22989](https://www.iso.org/search.html?q=ISO%2FIEC%2022989) | international standard | 2022 | Targeted | Consistent AI terminology across documents and APIs |
| [ISO/IEC 23053](https://www.iso.org/search.html?q=ISO%2FIEC%2023053) | international standard | 2022 | Targeted | Framework for ML-enabled systems |
| [ISO/IEC 5338](https://www.iso.org/search.html?q=ISO%2FIEC%205338) | international standard | 2023 | Core | Lifecycle processes for AI systems |
| [ISO/IEC 38507](https://www.iso.org/search.html?q=ISO%2FIEC%2038507) | international standard | 2022 | Targeted | Governance implications of AI adoption |
| [ISO/IEC 12792](https://www.iso.org/search.html?q=ISO%2FIEC%2012792) | international standard | 2025 | Targeted | Transparency taxonomy for AI systems |
| [ISO/IEC TS 8200](https://www.iso.org/search.html?q=ISO%2FIEC%20TS%208200) | international standard | 2024 | Core | Controllability and human supervision of automated AI |
| [ISO/IEC 25059](https://www.iso.org/search.html?q=ISO%2FIEC%2025059) | international standard | 2023 | Core | AI-system quality characteristics and evaluation targets |
| [ISO/IEC TS 25058](https://www.iso.org/search.html?q=ISO%2FIEC%20TS%2025058) | international standard | 2024 | Targeted | Guidance on AI-system quality evaluation |
| [ISO/IEC 5259-1](https://www.iso.org/search.html?q=ISO%2FIEC%205259-1) | international standard | 2024 | Targeted | AI and ML data quality foundations |
| [ISO/IEC 5259-2](https://www.iso.org/search.html?q=ISO%2FIEC%205259-2) | international standard | 2024 | Targeted | Quality measures for AI and ML data |
| [ISO/IEC 5259-3](https://www.iso.org/search.html?q=ISO%2FIEC%205259-3) | international standard | 2024 | Targeted | Data quality management for AI and ML |
| [ISO/IEC 5259-4](https://www.iso.org/search.html?q=ISO%2FIEC%205259-4) | international standard | 2024 | Targeted | Process framework for managing ML data quality |
| [ISO/IEC 5259-5](https://www.iso.org/search.html?q=ISO%2FIEC%205259-5) | international standard | 2025 | Conditional | Data-quality governance for trained or predictive models |
| [ISO/IEC TR 5259-6](https://www.iso.org/standard/5259-6) | international standard | 2026 | Conditional | Visual reporting of ML data quality |
| [ISO/IEC TR 24027](https://www.iso.org/search.html?q=ISO%2FIEC%20TR%2024027) | international standard | 2021 | Targeted | Bias in AI systems and AI-aided decisions |
| [ISO/IEC TR 24028](https://www.iso.org/search.html?q=ISO%2FIEC%20TR%2024028) | international standard | 2020 | Targeted | Trustworthiness characteristics and pitfalls |
| [ISO/IEC TR 24029-1](https://www.iso.org/search.html?q=ISO%2FIEC%20TR%2024029-1) | international standard | 2021 | Conditional | Neural-network robustness assessment overview |
| [ISO/IEC 24029-2](https://www.iso.org/search.html?q=ISO%2FIEC%2024029-2) | international standard | 2023 | Conditional | Formal approaches for assessing neural-network robustness |
| [ISO/IEC TS 12791](https://www.iso.org/search.html?q=ISO%2FIEC%20TS%2012791) | international standard | 2024 | Conditional | Treatment of unwanted bias in ML |
| [ISO/IEC TR 24368](https://www.iso.org/search.html?q=ISO%2FIEC%20TR%2024368) | international standard | 2022 | Targeted | Ethical and societal considerations |
| [ISO/IEC 42006](https://www.iso.org/search.html?q=ISO%2FIEC%2042006) | international standard | 2025 | Conditional | Requirements for AI-management certification bodies |
| [NIST AI RMF 1.0](https://www.nist.gov/itl/ai-risk-management-framework) | framework guidance | 1.0 (2023) | Core | Govern map measure and manage AI risk |
| [NIST AI 600-1](https://www.nist.gov/itl/ai-risk-management-framework/generative-ai-profile) | framework guidance | 2024 | Core | Generative AI risk management profile |
| [ISO/IEC 24970](https://www.iso.org/search.html?q=ISO%2FIEC%2024970) | draft or emerging | development candidate | Watch | Monitor proposed AI system logging work without asserting publication |

## Information security, privacy and resilience (23)

| Reference (official publisher link) | Type | Reported edition | Relevance | KubeIntellect application |
| --- | --- | --- | --- | --- |
| [ISO/IEC 27001](https://www.iso.org/search.html?q=ISO%2FIEC%2027001) | international standard | 2022 | Core | Information security management system |
| [ISO/IEC 27002](https://www.iso.org/search.html?q=ISO%2FIEC%2027002) | international standard | 2022 | Core | Security control catalogue and implementation guidance |
| [ISO/IEC 27005](https://www.iso.org/search.html?q=ISO%2FIEC%2027005) | international standard | edition to verify | Core | Information security risk-management method |
| [ISO/IEC 27017](https://www.iso.org/search.html?q=ISO%2FIEC%2027017) | international standard | 2026 | Targeted | Cloud service-specific security controls |
| [ISO/IEC 27018](https://www.iso.org/search.html?q=ISO%2FIEC%2027018) | international standard | 2025 | Targeted | Protection of personal data in public clouds |
| [ISO/IEC 27701](https://www.iso.org/search.html?q=ISO%2FIEC%2027701) | international standard | 2025 | Targeted | Privacy information management system |
| [ISO/IEC 29100](https://www.iso.org/search.html?q=ISO%2FIEC%2029100) | international standard | 2024 | Targeted | Privacy framework principles and terminology |
| [ISO/IEC 29134](https://www.iso.org/search.html?q=ISO%2FIEC%2029134) | international standard | edition to verify | Targeted | Privacy impact assessment guidance |
| [ISO/IEC 29151](https://www.iso.org/search.html?q=ISO%2FIEC%2029151) | international standard | edition to verify | Conditional | PII protection controls |
| [ISO/IEC 31700 series](https://www.iso.org/search.html?q=ISO%2FIEC%2031700%20series) | international standard | edition and parts to verify | Conditional | Privacy-by-design concepts for relevant interfaces |
| [ISO/IEC 27031](https://www.iso.org/search.html?q=ISO%2FIEC%2027031) | international standard | edition to verify | Targeted | ICT readiness for business continuity |
| [ISO/IEC 27033 series](https://www.iso.org/search.html?q=ISO%2FIEC%2027033%20series) | international standard | parts and editions to verify | Targeted | Security of network communications |
| [ISO/IEC 27034 series](https://www.iso.org/search.html?q=ISO%2FIEC%2027034%20series) | international standard | parts and editions to verify | Targeted | Application security management |
| [ISO/IEC 27035 series](https://www.iso.org/search.html?q=ISO%2FIEC%2027035%20series) | international standard | parts and editions to verify | Core | Information security incident handling |
| [ISO/IEC 27036 series](https://www.iso.org/search.html?q=ISO%2FIEC%2027036%20series) | international standard | parts and editions to verify | Targeted | External supplier and service trust management |
| [ISO/IEC 27037](https://www.iso.org/search.html?q=ISO%2FIEC%2027037) | international standard | edition to verify | Targeted | Identification and preservation of digital evidence |
| [ISO/IEC 27040](https://www.iso.org/search.html?q=ISO%2FIEC%2027040) | international standard | edition to verify | Targeted | Secure database and storage practices |
| [ISO/IEC 27041](https://www.iso.org/search.html?q=ISO%2FIEC%2027041) | international standard | edition to verify | Conditional | Investigative method assurance |
| [ISO/IEC 27042](https://www.iso.org/search.html?q=ISO%2FIEC%2027042) | international standard | edition to verify | Conditional | Analysis and interpretation of digital evidence |
| [ISO/IEC 27043](https://www.iso.org/search.html?q=ISO%2FIEC%2027043) | international standard | edition to verify | Conditional | Incident investigation principles |
| [ISO/IEC 27706](https://www.iso.org/search.html?q=ISO%2FIEC%2027706) | international standard | 2025 | Conditional | Privacy certification-body requirements |
| [ISO 31000](https://www.iso.org/search.html?q=ISO%2031000) | international standard | 2018 | Targeted | Organization-wide risk management guidelines |
| [ISO 22301](https://www.iso.org/search.html?q=ISO%2022301) | international standard | 2019 | Targeted | Business continuity management |

## NIST cybersecurity and secure engineering (20)

| Reference (official publisher link) | Type | Reported edition | Relevance | KubeIntellect application |
| --- | --- | --- | --- | --- |
| [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework) | framework guidance | 2.0 (2024) | Core | Cybersecurity outcomes and maturity assessment |
| [NIST SP 800-53](https://csrc.nist.gov/publications/sp800) | framework guidance | Rev. 5 | Core | Security and privacy control catalogue |
| [NIST SP 800-53A](https://csrc.nist.gov/publications/sp800) | framework guidance | Rev. 5 | Targeted | Independent security-control testing approach |
| [NIST SP 800-30](https://csrc.nist.gov/publications/sp800) | framework guidance | Rev. 1 | Targeted | Security risk assessment |
| [NIST SP 800-34](https://csrc.nist.gov/publications/sp800) | framework guidance | Rev. 1 | Targeted | Contingency planning for information systems |
| [NIST SP 800-37](https://csrc.nist.gov/publications/sp800) | framework guidance | Rev. 2 | Targeted | Risk management framework |
| [NIST SP 800-57](https://csrc.nist.gov/publications/sp800) | framework guidance | parts and editions to verify | Targeted | Cryptographic key lifecycle management |
| [NIST SP 800-61](https://csrc.nist.gov/publications/sp800) | framework guidance | Rev. 3 (2025) | Core | Modern incident response guidance |
| [NIST SP 800-63](https://csrc.nist.gov/publications/sp800) | framework guidance | Rev. 4 family (2025) | Core | Digital identity authentication and federation |
| [NIST SP 800-115](https://csrc.nist.gov/publications/sp800) | framework guidance | 2008 | Targeted | Technical security testing guidance |
| [NIST SP 800-161](https://csrc.nist.gov/publications/sp800) | framework guidance | Rev. 1 | Targeted | Cybersecurity supply-chain risk management |
| [NIST SP 800-190](https://csrc.nist.gov/publications/sp800) | framework guidance | 2017 | Core | Application container security guidance |
| [NIST SP 800-204](https://csrc.nist.gov/publications/sp800) | framework guidance | 2019 | Targeted | Cloud-native microservices security |
| [NIST SP 800-204A](https://csrc.nist.gov/publications/sp800) | framework guidance | 2020 | Conditional | Service-mesh security |
| [NIST SP 800-204B](https://csrc.nist.gov/publications/sp800) | framework guidance | 2021 | Targeted | Attribute-based access control in microservices |
| [NIST SP 800-204C](https://csrc.nist.gov/publications/sp800) | framework guidance | 2022 | Targeted | Cloud-native software development security |
| [NIST SP 800-204D](https://csrc.nist.gov/publications/sp800) | framework guidance | 2023 | Core | CI/CD and software supply-chain security |
| [NIST SP 800-207](https://csrc.nist.gov/publications/sp800) | framework guidance | 2020 | Core | Zero Trust Architecture |
| [NIST SP 800-218](https://csrc.nist.gov/publications/sp800) | framework guidance | 2022 | Core | Secure Software Development Framework |
| [FIPS 140-3](https://csrc.nist.gov/pubs/fips/140-3/final) | government standard | 2019 with updates | Conditional | Validated cryptographic modules when required |

## Kubernetes and cloud-native specifications (24)

| Reference (official publisher link) | Type | Reported edition | Relevance | KubeIntellect application |
| --- | --- | --- | --- | --- |
| [Kubernetes API conventions](https://kubernetes.io/docs/reference/using-api/api-concepts/) | technical specification | version-dependent | Core | Resource lifecycle and API compatibility |
| [Kubernetes RBAC API](https://kubernetes.io/docs/reference/access-authn-authz/rbac/) | technical specification | version-dependent | Core | Namespace and resource permission enforcement |
| [Kubernetes Pod Security Standards](https://kubernetes.io/docs/concepts/security/pod-security-standards/) | technical specification | current Kubernetes release | Core | Privileged Baseline and Restricted profiles |
| [Kubernetes Pod Security Admission](https://kubernetes.io/docs/concepts/security/pod-security-admission/) | technical specification | version-dependent | Core | Admission enforcement for pod profiles |
| [Kubernetes NetworkPolicy API](https://kubernetes.io/docs/concepts/services-networking/network-policies/) | technical specification | version-dependent | Core | Network segmentation and agent egress bounds |
| [Kubernetes Admission Control APIs](https://kubernetes.io/docs/reference/access-authn-authz/admission-controllers/) | technical specification | version-dependent | Core | Server-enforced mutation and validation boundaries |
| [Kubernetes Audit Policy](https://kubernetes.io/docs/tasks/debug/debug-cluster/audit/) | technical specification | version-dependent | Core | Audit events for tool effects and access |
| [Kubernetes Encryption Configuration and KMS](https://kubernetes.io/docs/tasks/administer-cluster/encrypt-data/) | technical specification | version-dependent | Targeted | Encryption at rest and key-provider integration |
| [Kubernetes Certificates API](https://kubernetes.io/docs/reference/access-authn-authz/certificate-signing-requests/) | technical specification | version-dependent | Targeted | Certificate issuance and rotation |
| [Kubernetes Metrics API](https://kubernetes.io/docs/tasks/debug/debug-cluster/resource-metrics-pipeline/) | technical specification | version-dependent | Targeted | Resource-metrics interoperability |
| [Kubernetes Gateway API](https://gateway-api.sigs.k8s.io/) | technical specification | release to verify | Targeted | Portable traffic and gateway routing |
| [Kubernetes CRD structural schemas](https://kubernetes.io/docs/tasks/extend-kubernetes/custom-resources/custom-resource-definitions/) | technical specification | version-dependent | Targeted | Safe extension schemas for custom resources |
| [Kubernetes ValidatingAdmissionPolicy and CEL](https://kubernetes.io/docs/reference/access-authn-authz/validating-admission-policy/) | technical specification | version-dependent | Core | Fail-closed server-side safety policy checks |
| [CNI specification](https://www.cni.dev/docs/spec/) | technical specification | edition to verify | Targeted | Container networking interoperability |
| [CSI specification](https://github.com/container-storage-interface/spec) | technical specification | edition to verify | Targeted | Storage plugin portability |
| [CRI specification](https://kubernetes.io/docs/concepts/architecture/cri/) | technical specification | version-dependent | Targeted | Container-runtime interoperability |
| [OCI Image Specification](https://specs.opencontainers.org/image-spec/) | technical specification | v1.1 family | Core | Reproducible image layout |
| [OCI Runtime Specification](https://specs.opencontainers.org/runtime-spec/) | technical specification | v1.3 family | Core | Container execution portability |
| [OCI Distribution Specification](https://specs.opencontainers.org/distribution-spec/) | technical specification | v1.1 family | Core | Registry and artifact interchange |
| [Helm chart best practices](https://helm.sh/docs/chart_best_practices/) | technical specification | living documentation | Core | Portable Kubernetes packaging conventions |
| [CIS Kubernetes Benchmark](https://www.cisecurity.org/benchmark/kubernetes) | security benchmark | edition depends on cluster version | Core | Kubernetes baseline tests matched to target version |
| [CIS Docker Benchmark](https://www.cisecurity.org/benchmark/docker) | security benchmark | edition to verify | Conditional | Docker host baseline when used |
| [CIS Controls](https://www.cisecurity.org/controls/v8-1) | security benchmark | v8.1 | Targeted | Mapped operational security outcomes |
| [NSA/CISA Kubernetes Hardening Guidance](https://www.cisa.gov/resources-tools/resources/kubernetes-hardening-guidance) | framework guidance | edition to verify | Core | Government guidance on production cluster defenses |

## Application, LLM and threat-model security (19)

| Reference (official publisher link) | Type | Reported edition | Relevance | KubeIntellect application |
| --- | --- | --- | --- | --- |
| [OWASP Top 10 for Agentic Applications](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/) | framework guidance | 2026 | Core | Agent tool misuse identity memory and approval risks |
| [OWASP Top 10 for LLM Applications](https://genai.owasp.org/llm-top-10/) | framework guidance | 2026 edition reported | Core | Prompt injection and LLM application risks |
| [OWASP Agent Control Standard](https://genai.owasp.org/) | framework guidance | 2026 | Core | Agent behavior controls at execution boundary |
| [OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/) | framework guidance | version to verify | Core | Testable application controls |
| [OWASP API Security Top 10](https://owasp.org/www-project-api-security/) | framework guidance | 2023 | Core | Authenticated API exposure and tool gateway risks |
| [OWASP Web Top 10](https://owasp.org/www-project-top-ten/) | framework guidance | 2021 | Targeted | Browser and hosted chat surface risks |
| [OWASP Software Assurance Maturity Model](https://owaspsamm.org/) | framework guidance | edition to verify | Targeted | Engineering security maturity |
| [OWASP Machine Learning Security Top 10](https://owasp.org/www-project-machine-learning-security-top-10/) | framework guidance | edition to verify | Targeted | ML-specific attack paths |
| [MITRE ATLAS](https://atlas.mitre.org/) | threat taxonomy | living knowledge base | Core | Attack techniques against AI systems |
| [MITRE ATT&CK for Containers](https://attack.mitre.org/matrices/enterprise/) | threat taxonomy | living matrix | Core | Observed container attacker techniques |
| [MITRE ATT&CK for Cloud](https://attack.mitre.org/matrices/enterprise/) | threat taxonomy | living matrix | Targeted | Cloud attack techniques for AKS EKS GKE |
| [MITRE CWE](https://cwe.mitre.org/) | threat taxonomy | living catalog | Targeted | Taxonomy for implementation vulnerabilities |
| [MITRE CAPEC](https://capec.mitre.org/) | threat taxonomy | living catalog | Targeted | Threat modeling and red-team cases |
| [CVE Program](https://www.cve.org/) | threat taxonomy | living catalog | Targeted | CVE tracking for dependencies |
| [FIRST CVSS](https://www.first.org/cvss/v4.0/specification-document) | framework guidance | 4.0 | Targeted | Structured vulnerability severity scoring |
| [CSA Cloud Controls Matrix](https://cloudsecurityalliance.org/research/cloud-controls-matrix) | framework guidance | version to verify | Targeted | Cloud controls aligned to providers |
| [CSA AI Controls Matrix](https://cloudsecurityalliance.org/research/ai-controls-matrix) | framework guidance | version to verify | Targeted | AI control mapping |
| [CSA STAR](https://cloudsecurityalliance.org/star) | framework guidance | scheme to verify | Conditional | Supplier assurance and transparency |
| [STRIDE threat modeling](https://learn.microsoft.com/en-us/azure/security/develop/threat-modeling-tool-threats) | framework guidance | method | Targeted | Structured analysis of threats to system boundaries |

## Software supply chain and open-source assurance (14)

| Reference (official publisher link) | Type | Reported edition | Relevance | KubeIntellect application |
| --- | --- | --- | --- | --- |
| [SLSA framework](https://slsa.dev/) | technical specification | v1.2 | Core | Source and build provenance assurance |
| [SPDX specification](https://spdx.dev/) | technical specification | ISO/IEC 5962:2021 baseline; newer SPDX versions exist | Core | Software component and licensing metadata |
| [CycloneDX specification](https://cyclonedx.org/specification/overview/) | technical specification | ECMA-424 2nd edition (2025) | Core | Portable software and dependencies inventory |
| [OpenChain ISO/IEC 5230](https://openchainproject.org/) | technical specification | edition to verify | Targeted | Open-source license compliance programs |
| [OpenChain ISO/IEC 18974](https://openchainproject.org/) | technical specification | 2023 | Targeted | Open-source security assurance |
| [OpenSSF OSPS Baseline](https://baseline.openssf.org/) | technical specification | v2026.08.28 | Core | Open-source minimum security practices |
| [OpenSSF Scorecard](https://securityscorecards.dev/) | technical specification | living tool | Targeted | Continuous supply-chain posture checks |
| [OpenSSF Best Practices Badge](https://www.bestpractices.dev/) | technical specification | living scheme | Targeted | Project best-practice self-assessment |
| [Sigstore](https://www.sigstore.dev/) | technical specification | current implementation | Core | Keyless signature and provenance verification |
| [in-toto Attestation](https://github.com/in-toto/attestation) | technical specification | v1 family | Core | Supply-chain step attestations |
| [The Update Framework](https://theupdateframework.io/) | technical specification | current specification | Conditional | Secure software update metadata and rollback protection |
| [CSAF 2.0](https://docs.oasis-open.org/csaf/csaf/v2.0/) | technical specification | 2.0 | Targeted | Machine-readable vulnerability advisories |
| [OpenVEX](https://github.com/openvex/spec) | technical specification | current schema | Targeted | Explain exploitability of known CVEs |
| [SPDX License List](https://spdx.org/licenses/) | technical specification | living list | Targeted | Consistent license metadata |

## Agent interop, identity and verifiable evidence (58)

| Reference (official publisher link) | Type | Reported edition | Relevance | KubeIntellect application |
| --- | --- | --- | --- | --- |
| [Model Context Protocol (MCP)](https://modelcontextprotocol.io/specification/2026-07-28) | industry protocol | 2026-07-28 | Core | Standardized model tooling and resource access with authorization |
| [Agent2Agent (A2A) Protocol](https://a2a-protocol.org/latest/specification/) | industry protocol | v1.0 family | Targeted | Delegation and communication with other agents |
| [Agent-User Interaction Protocol (AG-UI)](https://docs.ag-ui.com/introduction) | industry protocol | 1.0 SDK family | Targeted | Structured approval and interactive event streaming |
| [AGNTCY Open Agentic Schema Framework](https://github.com/agntcy/oasf) | industry protocol | v1.1 family | Conditional | Agent capability metadata and discovery |
| [OpenAPI Specification](https://spec.openapis.org/oas/latest.html) | industry protocol | 3.2.1 reported | Core | Portable HTTP API descriptions |
| [OpenAPI Arazzo](https://spec.openapis.org/arazzo/latest.html) | industry protocol | current specification | Conditional | Sequence and dependency descriptions for remediation APIs |
| [OpenAPI Overlay](https://spec.openapis.org/overlay/latest.html) | industry protocol | current specification | Watch | Contract annotations and extension metadata |
| [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest) | industry protocol | current specification | Targeted | Describe webhook alert and event integrations |
| [JSON Schema](https://json-schema.org/draft/2020-12) | industry protocol | 2020-12 | Core | Strict types and input validation of agent and tool contracts |
| [YAML](https://yaml.org/spec/1.2.2/) | industry protocol | 1.2 | Targeted | Portable deployment and agent configuration |
| [JSON-RPC](https://www.jsonrpc.org/specification) | industry protocol | 2.0 | Targeted | Typed request response and errors |
| [gRPC](https://grpc.io/docs/) | industry protocol | living specification | Conditional | Typed internal service communication |
| [Protocol Buffers](https://protobuf.dev/) | industry protocol | living specification | Conditional | Schema-governed inter-service messages |
| [CloudEvents](https://cloudevents.io/) | industry protocol | v1.0 family | Core | Portable alert and action event envelope |
| [OpenTelemetry](https://opentelemetry.io/docs/specs/otel/) | industry protocol | current specifications | Core | Interoperable metrics logs and traces |
| [OpenTelemetry GenAI Semantic Conventions](https://github.com/open-telemetry/semantic-conventions-genai) | industry protocol | Development maturity reported | Targeted | Model call and agent span attributes |
| [SPIFFE and SPIRE](https://spiffe.io/) | industry protocol | current specifications | Targeted | Trust identities for agent workers and tool gateways |
| [Open Policy Agent](https://www.openpolicyagent.org/docs) | industry protocol | current specification | Targeted | Policy decision enforcement for agent/tool boundaries |
| [OpenCost](https://www.opencost.io/docs/) | industry protocol | current specification | Targeted | Standardized Kubernetes cost attribution |
| [W3C Trace Context](https://www.w3.org/TR/trace-context/) | w3c recommendation | Recommendation | Core | Propagate trace IDs across agent and Kubernetes boundaries |
| [W3C PROV-DM](https://www.w3.org/TR/prov-dm/) | w3c recommendation | Recommendation | Core | Machine-readable causal entity activity and agent relationships |
| [W3C PROV-O](https://www.w3.org/TR/prov-o/) | w3c recommendation | Recommendation | Core | Semantic graph and external evidence links |
| [W3C Baggage](https://www.w3.org/TR/baggage/) | w3c recommendation | Recommendation | Conditional | Context propagation with privacy protections |
| [W3C Verifiable Credentials Data Model](https://www.w3.org/TR/vc-data-model-2.0/) | w3c recommendation | 2.0 | Conditional | Verifiable externally issued agent or approval assertions |
| [W3C Decentralized Identifiers](https://www.w3.org/TR/did-core/) | w3c recommendation | 1.0 | Watch | Decentralized identifiers only if justified by federation design |
| [W3C WebAuthn](https://www.w3.org/TR/webauthn-3/) | w3c recommendation | level to verify | Conditional | Phishing-resistant human authorization |
| [W3C ODRL Information Model](https://www.w3.org/TR/odrl-model/) | w3c recommendation | 2.2 | Conditional | Policy-expression exchange separate from enforcement |
| [RFC 9110 HTTP Semantics](https://www.rfc-editor.org/rfc/rfc9110) | ietf rfc | 9110 | Core | Correct request and response semantics |
| [RFC 8446 TLS 1.3](https://www.rfc-editor.org/rfc/rfc8446) | ietf rfc | 8446 | Core | Authenticated encrypted connections |
| [RFC 4251 SSH Protocol Architecture](https://www.rfc-editor.org/rfc/rfc4251) | ietf rfc | 4251 | Targeted | SSH-tunnel security model |
| [RFC 6749 OAuth 2.0](https://www.rfc-editor.org/rfc/rfc6749) | ietf rfc | 6749 | Targeted | Delegation to approved clients and tool callers |
| [RFC 9700 OAuth 2.0 Security BCP](https://www.rfc-editor.org/rfc/rfc9700) | ietf rfc | 9700 | Core | OAuth threat and mitigation baseline |
| [RFC 8693 OAuth 2.0 Token Exchange](https://www.rfc-editor.org/rfc/rfc8693) | ietf rfc | 8693 | Core | Mint short-lived narrower tool-scoped credentials |
| [RFC 8707 OAuth Resource Indicators](https://www.rfc-editor.org/rfc/rfc8707) | ietf rfc | 8707 | Targeted | Audience-bound agent tool tokens |
| [RFC 8705 OAuth Mutual TLS](https://www.rfc-editor.org/rfc/rfc8705) | ietf rfc | 8705 | Targeted | Sender-constrained identity and token transport |
| [RFC 9207 OAuth Issuer Identification](https://www.rfc-editor.org/rfc/rfc9207) | ietf rfc | 9207 | Targeted | Validate trusted authorization issuer |
| [RFC 9449 OAuth DPoP](https://www.rfc-editor.org/rfc/rfc9449) | ietf rfc | 9449 | Targeted | Reduce replay risk for stolen bearer credentials |
| [RFC 9728 OAuth Protected Resource Metadata](https://www.rfc-editor.org/rfc/rfc9728) | ietf rfc | 9728 | Targeted | Resource metadata and issuer discovery |
| [RFC 7009 OAuth Token Revocation](https://www.rfc-editor.org/rfc/rfc7009) | ietf rfc | 7009 | Targeted | Revoke credentials while independently testing sink effects |
| [RFC 7662 OAuth Token Introspection](https://www.rfc-editor.org/rfc/rfc7662) | ietf rfc | 7662 | Targeted | Check current downstream authority |
| [RFC 9068 JWT Access Token Profile](https://www.rfc-editor.org/rfc/rfc9068) | ietf rfc | 9068 | Conditional | Interoperable audience and scope claims |
| [RFC 8725 JWT Best Current Practices](https://www.rfc-editor.org/rfc/rfc8725) | ietf rfc | 8725 | Targeted | JWT algorithm and token-type confusion defenses |
| [RFC 7519 JSON Web Token](https://www.rfc-editor.org/rfc/rfc7519) | ietf rfc | 7519 | Targeted | Signed token claims |
| [RFC 7515 JSON Web Signature](https://www.rfc-editor.org/rfc/rfc7515) | ietf rfc | 7515 | Targeted | Signed structured authorization and receipts |
| [RFC 9052 COSE Structures and Process](https://www.rfc-editor.org/rfc/rfc9052) | ietf rfc | 9052 | Targeted | Compact signed receipts |
| [RFC 8785 JSON Canonicalization Scheme](https://www.rfc-editor.org/rfc/rfc8785) | ietf rfc | 8785 | Core | Stable canonical bytes for hashed action envelopes |
| [RFC 9943 SCITT Architecture](https://www.rfc-editor.org/rfc/rfc9943) | ietf rfc | 9943 | Core | Signed statement transparency architecture |
| [RFC 9942 COSE Receipts](https://www.rfc-editor.org/rfc/rfc9942) | ietf rfc | 9942 | Core | Transportable inclusion and consistency receipt formats |
| [RFC 9562 UUIDs](https://www.rfc-editor.org/rfc/rfc9562) | ietf rfc | 9562 | Targeted | Stable task and execution identifiers |
| [RFC 7643 SCIM Core Schema](https://www.rfc-editor.org/rfc/rfc7643) | ietf rfc | 7643 | Conditional | Enterprise identity provisioning |
| [RFC 7644 SCIM Protocol](https://www.rfc-editor.org/rfc/rfc7644) | ietf rfc | 7644 | Conditional | Enterprise principal lifecycle |
| [RFC 8949 CBOR](https://www.rfc-editor.org/rfc/rfc8949) | ietf rfc | 8949 | Conditional | Compact evidence representation |
| [RFC 8610 CDDL](https://www.rfc-editor.org/rfc/rfc8610) | ietf rfc | 8610 | Conditional | Schema language for CBOR envelopes |
| [RFC 3161 Time-Stamp Protocol](https://www.rfc-editor.org/rfc/rfc3161) | ietf rfc | 3161 | Conditional | Trusted timestamp authority receipts |
| [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html) | industry protocol | 1.0 | Targeted | Human sign-in and federation |
| [IETF WIMSE Architecture](https://datatracker.ietf.org/doc/draft-ietf-wimse-arch/) | ietf draft | Internet-Draft; not final | Watch | Workload identity for cross-service and agent delegation |
| [IETF OAuth Transaction Tokens](https://datatracker.ietf.org/doc/draft-ietf-oauth-transaction-tokens/) | ietf draft | Internet-Draft; not final | Watch | Transaction context-bound authorization research |
| [IETF Identity and Authorization Chaining](https://datatracker.ietf.org/doc/draft-ietf-oauth-identity-chaining/) | ietf draft | Internet-Draft; status to recheck | Watch | Preserving actor chain metadata across services |

## Cloud portability, SRE and cost operations (20)

| Reference (official publisher link) | Type | Reported edition | Relevance | KubeIntellect application |
| --- | --- | --- | --- | --- |
| [ISO/IEC 22123 series](https://www.iso.org/search.html?q=ISO%2FIEC%2022123%20series) | international standard | parts and editions to verify | Targeted | Cloud computing concepts and definitions |
| [ISO/IEC 5140](https://www.iso.org/search.html?q=ISO%2FIEC%205140) | international standard | 2024 | Targeted | Multi-cloud concepts |
| [ISO/IEC TR 10822-1](https://www.iso.org/search.html?q=ISO%2FIEC%20TR%2010822-1) | international standard | 2025 | Targeted | Multi-cloud management reference |
| [ISO/IEC 19941-1](https://www.iso.org/search.html?q=ISO%2FIEC%2019941-1) | international standard | 2026 | Targeted | Cloud service portability and interoperability |
| [ISO/IEC 19944-1](https://www.iso.org/search.html?q=ISO%2FIEC%2019944-1) | international standard | 2020 | Targeted | Cloud data flow and usage |
| [ISO/IEC 19944-2](https://www.iso.org/search.html?q=ISO%2FIEC%2019944-2) | international standard | 2022 | Conditional | Data-flow and data-use guidance |
| [ISO/IEC 19086-1](https://www.iso.org/search.html?q=ISO%2FIEC%2019086-1) | international standard | edition to verify | Targeted | Cloud service-level agreements baseline |
| [ISO/IEC 19086-2](https://www.iso.org/search.html?q=ISO%2FIEC%2019086-2) | international standard | edition to verify | Targeted | Metrics model for cloud SLAs |
| [ISO/IEC 19086-3](https://www.iso.org/search.html?q=ISO%2FIEC%2019086-3) | international standard | edition to verify | Targeted | Cloud SLA conformance requirements |
| [ISO/IEC 19086-4](https://www.iso.org/search.html?q=ISO%2FIEC%2019086-4) | international standard | edition to verify | Targeted | Security and privacy in cloud SLAs |
| [ISO/IEC TR 23951](https://www.iso.org/search.html?q=ISO%2FIEC%20TR%2023951) | international standard | 2025 | Conditional | Cloud service measurement practices |
| [ISO/IEC TR 23613](https://www.iso.org/search.html?q=ISO%2FIEC%20TR%2023613) | international standard | 2020 | Targeted | Cloud service metering and billing |
| [ISO/IEC 23751](https://www.iso.org/search.html?q=ISO%2FIEC%2023751) | international standard | 2022 | Conditional | Data-sharing agreement framework |
| [ISO/IEC TR 3445](https://www.iso.org/search.html?q=ISO%2FIEC%20TR%203445) | international standard | 2022 | Conditional | Auditing cloud services |
| [ISO/IEC TS 10866](https://www.iso.org/search.html?q=ISO%2FIEC%20TS%2010866) | international standard | 2024 | Conditional | Digital sovereignty terminology and considerations |
| [ISO/IEC 20000-1](https://www.iso.org/search.html?q=ISO%2FIEC%2020000-1) | international standard | 2018 | Targeted | IT service management processes |
| [ITIL 4](https://www.peoplecert.org/) | framework guidance | current practice system | Conditional | Incident change and problem management |
| [Google SRE SLI SLO Error Budget Practices](https://sre.google/workbook/implementing-slos/) | framework guidance | living guidance | Core | Reliability targets and error budgets |
| [FinOps Foundation Framework](https://www.finops.org/framework/) | framework guidance | living guidance | Targeted | Cloud financial management |
| [DORA Software Delivery Metrics](https://dora.dev/guides/dora-metrics-four-keys/) | framework guidance | living guidance | Targeted | Lead time deployment frequency change failure and recovery |

## Software architecture, quality and assurance (14)

| Reference (official publisher link) | Type | Reported edition | Relevance | KubeIntellect application |
| --- | --- | --- | --- | --- |
| [ISO/IEC/IEEE 42010](https://www.iso.org/search.html?q=ISO%2FIEC%2FIEEE%2042010) | international standard | 2022 | Core | Explicit architecture description and viewpoints |
| [ISO/IEC/IEEE 12207](https://www.iso.org/search.html?q=ISO%2FIEC%2FIEEE%2012207) | international standard | edition to verify | Targeted | Software lifecycle processes |
| [ISO/IEC/IEEE 15288](https://www.iso.org/search.html?q=ISO%2FIEC%2FIEEE%2015288) | international standard | edition to verify | Targeted | Systems lifecycle processes |
| [ISO/IEC/IEEE 29148](https://www.iso.org/search.html?q=ISO%2FIEC%2FIEEE%2029148) | international standard | edition to verify | Targeted | Requirements engineering traceability |
| [ISO/IEC/IEEE 29119 series](https://www.iso.org/search.html?q=ISO%2FIEC%2FIEEE%2029119%20series) | international standard | parts and editions to verify | Targeted | Software test artifacts and processes |
| [ISO/IEC 25010](https://www.iso.org/search.html?q=ISO%2FIEC%2025010) | international standard | 2023 | Core | Functional quality reliability security and maintainability |
| [ISO/IEC 25023](https://www.iso.org/search.html?q=ISO%2FIEC%2025023) | international standard | edition to verify | Targeted | Measurement of software product quality |
| [ISO/IEC 25012](https://www.iso.org/search.html?q=ISO%2FIEC%2025012) | international standard | edition to verify | Targeted | Data quality characteristics |
| [ISO/IEC 25024](https://www.iso.org/search.html?q=ISO%2FIEC%2025024) | international standard | edition to verify | Targeted | Measurement of data quality |
| [ISO/IEC 25040](https://www.iso.org/search.html?q=ISO%2FIEC%2025040) | international standard | edition to verify | Targeted | Quality evaluation process |
| [ISO 9001](https://www.iso.org/search.html?q=ISO%209001) | international standard | 2015 | Conditional | Organizational quality system |
| [IEEE 1012](https://standards.ieee.org/) | international standard | edition to verify | Targeted | Software and system verification and validation |
| [IEEE 7001](https://standards.ieee.org/) | international standard | edition to verify | Targeted | Transparency requirements for autonomous systems |
| [IEEE 7009](https://standards.ieee.org/) | international standard | edition to verify | Conditional | Fail-safe and safety-aware autonomous system design |

## European legal and regulatory scope (10)

| Reference (official publisher link) | Type | Reported edition | Relevance | KubeIntellect application |
| --- | --- | --- | --- | --- |
| [EU AI Act Regulation 2024/1689](https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng) | legislation | as amended; staged application | Scope-check | Assess AI-system role intended use and relevant obligations |
| [EU General Data Protection Regulation 2016/679](https://eur-lex.europa.eu/eli/reg/2016/679/oj/eng) | legislation | as amended | Scope-check | Assess controller processor and personal-data processing |
| [EU NIS2 Directive 2022/2555](https://eur-lex.europa.eu/eli/dir/2022/2555/oj/eng) | legislation | as transposed nationally | Scope-check | Applicable covered organizations and operators |
| [EU Cyber Resilience Act Regulation 2024/2847](https://eur-lex.europa.eu/eli/reg/2024/2847/oj/eng) | legislation | staged application | Scope-check | Assess product distribution and open-source steward obligations |
| [EU DORA Regulation 2022/2554](https://eur-lex.europa.eu/eli/reg/2022/2554/oj/eng) | legislation | applicable from 2025 | Conditional | Financial-sector ICT operational resilience |
| [EU Data Act Regulation 2023/2854](https://eur-lex.europa.eu/eli/reg/2023/2854/oj/eng) | legislation | staged application | Conditional | Data access and cloud service-switching conditions |
| [EU ePrivacy Directive 2002/58/EC](https://eur-lex.europa.eu/eli/dir/2002/58/oj/eng) | legislation | as amended | Scope-check | Relevant communications and tracking obligations |
| [EU eIDAS Regulation 910/2014](https://eur-lex.europa.eu/eli/reg/2014/910/oj/eng) | legislation | as amended | Conditional | Qualified trust services and identity attestations |
| [EU Data Governance Act Regulation 2022/868](https://eur-lex.europa.eu/eli/reg/2022/868/oj/eng) | legislation | as amended | Conditional | Data intermediaries and reuse scenarios |
| [EU European Accessibility Act Directive 2019/882](https://eur-lex.europa.eu/eli/dir/2019/882/oj/eng) | legislation | as transposed nationally | Scope-check | Covered consumer-facing services and products |

## Accessibility, sustainability and research (9)

| Reference (official publisher link) | Type | Reported edition | Relevance | KubeIntellect application |
| --- | --- | --- | --- | --- |
| [ISO 9241-210](https://www.iso.org/search.html?q=ISO%209241-210) | international standard | 2019 | Targeted | Human-centred design for chat and approval interfaces |
| [ISO/IEC 21031](https://www.iso.org/search.html?q=ISO%2FIEC%2021031) | international standard | 2024 | Conditional | Software Carbon Intensity measurement |
| [ISO/IEC 30134 series](https://www.iso.org/search.html?q=ISO%2FIEC%2030134%20series) | international standard | parts and editions to verify | Conditional | Data-centre energy and resource KPIs |
| [ISO 50001](https://www.iso.org/search.html?q=ISO%2050001) | international standard | 2018 | Conditional | Energy-management systems for larger deployments |
| [ISO 14001](https://www.iso.org/search.html?q=ISO%2014001) | international standard | 2015 | Conditional | Environmental management systems |
| [WCAG](https://www.w3.org/TR/WCAG22/) | accessibility spec | 2.2 | Targeted | Accessible hosted dashboard and chat interactions |
| [EN 301 549](https://www.etsi.org/technologies/human-factors) | accessibility spec | edition to verify | Targeted | ICT accessibility requirements |
| [FAIR Data Principles](https://www.go-fair.org/fair-principles/) | research guidance | 2016 principles | Targeted | Findable accessible interoperable reusable research outputs |
| [ACM Artifact Review and Badging](https://www.acm.org/publications/policies/artifact-review-and-badging-current) | research guidance | latest guidance | Targeted | Reproducible code data and paper artifact assessment |

---

## Verification and preservation requirements

1. Verify the standard's exact identifier, current edition, applicability and status on the issuing body's primary site; record the date and source in the CSV.
2. Scope controls by actual exposed API, mode, deployment and data flow; do not map an entire standards family to blanket compliance.
3. For each proposed control, collect an implementation link, explicit test, result and reviewer; use [traceability](kubeintellect-traceability.md) as the starting point.
4. Keep this public register limited to public evidence and generic test proposals; private security research and unpublished implementation details must remain outside it.
5. Treat draft and vendor specifications as experiments until an adopting implementation and interoperability tests justify an assurance claim.

## Related public draft registers

The [Agent Movement 284-reference](https://github.com/MSKazemi/standards/pull/2) and [NovaFabric 227-reference](https://github.com/MSKazemi/standards/pull/1) registers are under separate **unmerged draft pull requests** as of this research date. Cross-project ideas are summarized in [the reuse matrix](cross-project-standards.md).
