# NovaFabric Standards and Regulatory Landscape

**Related project:** [MSKazemi/novafabric](https://github.com/MSKazemi/novafabric) — open-source evidence, provenance, and replay infrastructure for AI agent runs.  
**Maintained in:** [MSKazemi/standards](https://github.com/MSKazemi/standards), as a public research register alongside other project inventories.  
**Research baseline:** 2026-11-21 (Europe/Rome). **Public project snapshot:** [`main` @ `4f89480c`](https://github.com/MSKazemi/novafabric/tree/4f89480c2de83f0f51003cb096db58b9904a4ce5).  
**Review status:** Candidate relevance and reported implementation states are documented for research, not independently certified or verified.

**Inventory:** 264 references across 14 numbered categories. [How to use this register](../docs/how-to-use-standards.md) · [NovaFabric adoption workplan](novafabric-standards-adoption-plan.md) · [Machine-readable CSV](../data/novafabric-standards.csv).

**Scope:** Broad technical and regulatory *candidate registry*, not a claim that every item must be implemented. Covers formal standards, specifications, RFCs, regulations, voluntary frameworks, and industry guidance (identified separately).

**Research priorities:** P0 = directly shapes NovaFabric evidence/trust/replay; P1 = important interoperability and customer trust; P2 = vertical-specific or useful near-term; P3 = monitoring/future only. These are *relevance tiers*, not GitHub issue urgency or a commitment to implement.

**Implementation status:** Only entries explicitly named in the public `docs/standards-conformance.md` and the readme are labelled as *documented*. This is not an independent conformance test. All other entries are `Assess / not verified`.

**Legal/copyright:** Do not copy protected ISO, AICPA, CIS, or other proprietary control text into the repo. Use reference IDs, titles, our own explanations, permitted public metadata, and links. These mappings are not certifications or compliance verdicts.

## 01. Verifiable evidence, signatures, timestamps, and trust (30)

| Standard / specification | Class | Priority | NovaFabric relevance | Repo evidence status |
|---|---|---|---|---|
| in-toto Attestation / Statement v1 | Open specification | P0 | Signed descriptions of run artifacts and subject digests | Documented: works today |
| DSSE (Dead Simple Signing Envelope) | Open specification | P0 | Portable signed Evidence Bundle envelopes | Documented: works today |
| IETF RFC 9943 (SCITT architecture, 2026) | IETF Proposed Standard | P0 | Independent transparency services for signed statements | Assess / not verified |
| IETF RFC 9942 (COSE Receipts, 2026) | IETF Proposed Standard | P0 | Interoperable inclusion and consistency receipts | Assess / not verified |
| IETF RFC 3161 (Time-Stamp Protocol) | IETF RFC | P0 | Timestamp tokens for sealed capsules | Documented: works today (opt-in) |
| IETF RFC 5816 (RFC 3161 update) | IETF RFC | P1 | Updated timestamp token and certificate conventions | Assess / not verified |
| IETF RFC 9162 (Certificate Transparency v2) | IETF RFC | P0 | Modern append-only Merkle proof conventions | Documented: Merkle hash reference |
| IETF RFC 6962 (Certificate Transparency v1) | IETF RFC | P1 | Legacy Merkle proof compatibility | Documented: works today / historical compat |
| IETF RFC 8785 (JSON Canonicalization Scheme) | IETF RFC | P0 | Reproducible canonical signed object digests | Documented: proposal digest only |
| IETF RFC 8949 (CBOR) | IETF Internet Standard | P1 | Compact exchange format for receipts | Assess / not verified |
| IETF RFC 9052 / 9053 (COSE) | IETF RFCs | P1 | Cryptographic encoding for SCITT-style receipts | Assess / not verified |
| IETF RFC 7515 / 7517 / 7519 (JWS, JWK, JWT) | IETF RFCs | P1 | Signed identity and token metadata | Assess / not verified |
| IETF RFC 5280 (X.509 certificate profile) | IETF RFC | P0 | Certificate path validation and signer identity | Assess / not verified |
| IETF RFC 6960 (OCSP) | IETF RFC | P1 | Certificate revocation evidence | Assess / not verified |
| IETF RFC 4998 (Evidence Record Syntax) | IETF RFC | P2 | Long-term preservation of evidence validation | Assess / not verified |
| IETF RFC 6283 (XML Evidence Record Syntax) | IETF RFC | P3 | Alternative long-term archival evidence structures | Assess / not verified |
| ETSI EN 319 401 | ETSI European standard | P1 | Trust-service-provider policy requirements | Assess / not verified |
| ETSI EN 319 421 | ETSI European standard | P1 | Time-stamping service requirements | Assess / not verified |
| ETSI EN 319 422 | ETSI European standard | P1 | Timestamp protocol and token profiles | Assess / not verified |
| ETSI EN 319 122 / 132 / 142 families | ETSI standards | P2 | CAdES / XAdES / PAdES signature interoperability | Assess / not verified |
| FIPS 180-4 / 202 | US cryptographic standards | P0 | SHA-2 / SHA-3 digest primitives | Assess / not verified |
| FIPS 186-5 | US cryptographic standard | P0 | Digital signature algorithms | Assess / not verified |
| FIPS 140-3 | US cryptographic standard | P2 | Cryptographic module validation expectations | Assess / not verified |
| FIPS 203 / 204 / 205 | US cryptographic standards | P2 | Post-quantum key establishment and signature migration | Assess / not verified |
| PKCS #11 / OASIS PKCS 11 | OASIS specification | P1 | HSM token and signing-key abstraction | Assess / not verified |
| IETF RFC 9334 (RATS architecture) | IETF Informational RFC | P2 | Remote attestation model for execution environment evidence | Assess / not verified |
| IETF RFC 9711 (Entity Attestation Token) | IETF Proposed Standard | P2 | Represent verified machine and runtime claims | Assess / not verified |
| C2PA 2.3 | Industry specification | P2 | Content Credentials for generated media; unsigned export is not signed C2PA | Documented: experimental, unsigned export |
| W3C Verifiable Credentials Data Model v2.0 | W3C Recommendation | P2 | Portable verifiable compliance or execution credentials | Assess / not verified |
| W3C Data Integrity cryptosuites | W3C Recommendation / specifications | P2 | Signature proofs for graph/credential evidence | Assess / not verified |

## 02. AI run capture, observability, provenance, and interoperability (21)

| Standard / specification | Class | Priority | NovaFabric relevance | Repo evidence status |
|---|---|---|---|---|
| OpenTelemetry Tracing specification | CNCF specification | P0 | Standard span semantics and trace interoperation | Assess / not verified |
| OpenTelemetry Logs specification | CNCF specification | P0 | Log records and correlation | Assess / not verified |
| OpenTelemetry OTLP | CNCF specification | P1 | Standard telemetry transport | Assess / not verified |
| OpenTelemetry GenAI semantic conventions | CNCF specification | P0 | Model, prompt metadata, and token-use event semantics | Documented: works today |
| W3C Trace Context | W3C Recommendation | P0 | Traceparent and tracestate across services | Assess / not verified |
| W3C Baggage | W3C Recommendation | P1 | Distributed metadata propagation | Assess / not verified |
| OpenLineage | Open specification | P0 | Runs, jobs, datasets, and lineage event interchange | Documented: works today |
| W3C PROV-DM | W3C Recommendation | P0 | Entity, activity, and agent provenance graph | Documented: works today |
| W3C PROV-O | W3C Recommendation | P1 | RDF/OWL provenance graph mappings | Documented: experimental |
| W3C PROV-N | W3C Recommendation | P1 | Human-readable provenance interchange | Documented: works today |
| W3C PROV-JSON (community serialization) | Community serialization | P2 | JSON export convenience; distinguish from W3C Recommendations | Assess / not verified |
| W3C SHACL | W3C Recommendation | P1 | Shape validation of semantic evidence graphs | Documented: experimental |
| W3C JSON-LD 1.1 | W3C Recommendation | P1 | Linked-data interchange of provenance | Assess / not verified |
| W3C DCAT v3 | W3C Recommendation | P2 | Dataset catalog interoperability | Assess / not verified |
| JSON Schema draft 2020-12 | Open specification | P0 | Validation and evolution of capsule and bundle schemas | Documented: works today |
| OpenAPI 3.1 | OpenAPI Initiative specification | P1 | API contract and developer integration | Assess / not verified |
| Model Context Protocol (MCP) | Open protocol | P0 | Tool invocation capture and proxy integration | Documented: experimental |
| Agent2Agent (A2A) Protocol | Open protocol | P2 | Cross-agent interoperability and interaction tracing | Assess / not verified |
| CloudEvents 1.0.x | CNCF specification | P2 | Transport-neutral event envelope | Assess / not verified |
| openCypher | Industry language specification | P2 | Graph queries for lineage indexes | Assess / not verified |
| OASIS XACML 3.0 | OASIS standard | P2 | Optional interoperable policy decision models | Assess / not verified |

## 03. AI governance, testing, risk, and accountability (38)

| Standard / specification | Class | Priority | NovaFabric relevance | Repo evidence status |
|---|---|---|---|---|
| ISO/IEC 42001:2023 | ISO/IEC standard | P0 | AI management system evidence mapping | Documented: experimental evidence export |
| ISO/IEC 42005:2025 | ISO/IEC standard | P1 | Impact assessment inputs and artifacts | Assess / not verified |
| ISO/IEC 42006:2025 | ISO/IEC standard | P2 | Understanding certification-body assessment evidence | Assess / not verified |
| ISO/IEC 22989:2022 | ISO/IEC standard | P1 | Consistent AI vocabulary | Assess / not verified |
| ISO/IEC 23053:2022 | ISO/IEC standard | P1 | AI/ML system architecture concepts | Assess / not verified |
| ISO/IEC 23894:2023 | ISO/IEC standard | P1 | AI risk management | Assess / not verified |
| ISO/IEC 5338:2023 | ISO/IEC standard | P1 | AI system lifecycle processes | Assess / not verified |
| ISO/IEC 5339:2024 | ISO/IEC standard | P2 | AI application guidance | Assess / not verified |
| ISO/IEC 25059:2023 | ISO/IEC standard | P1 | AI-system quality model | Assess / not verified |
| ISO/IEC TS 25058:2024 | ISO/IEC technical specification | P2 | Quality evaluation guidance for AI systems | Assess / not verified |
| ISO/IEC 5259-1:2024 | ISO/IEC standard | P2 | AI dataset quality terminology | Assess / not verified |
| ISO/IEC 5259-2:2024 | ISO/IEC standard | P2 | Dataset quality measures | Assess / not verified |
| ISO/IEC 5259-3:2024 | ISO/IEC standard | P2 | Dataset quality management | Assess / not verified |
| ISO/IEC 5259-4:2024 | ISO/IEC standard | P2 | Data quality process framework | Assess / not verified |
| ISO/IEC 5259-5:2025 | ISO/IEC standard | P2 | Data quality governance | Assess / not verified |
| ISO/IEC TR 5259-6:2026 | ISO/IEC technical report | P3 | Data quality visualization framework | Assess / not verified |
| ISO/IEC 12792:2025 | ISO/IEC standard | P2 | Transparency taxonomy of AI systems | Assess / not verified |
| ISO/IEC TS 6254:2025 | ISO/IEC technical specification | P2 | Explainability and interpretability | Assess / not verified |
| ISO/IEC TS 8200:2024 | ISO/IEC technical specification | P2 | Controllability of automated AI systems | Assess / not verified |
| ISO/IEC TS 12791:2024 | ISO/IEC technical specification | P2 | Unwanted bias treatment | Assess / not verified |
| ISO/IEC TR 24027:2021 | ISO/IEC technical report | P2 | Bias in AI systems | Assess / not verified |
| ISO/IEC TR 24028:2020 | ISO/IEC technical report | P2 | Trustworthiness concepts | Assess / not verified |
| ISO/IEC TR 24029-1:2021 / ISO/IEC 24029-2:2023 | ISO/IEC series | P2 | Robustness evaluation of neural networks | Assess / not verified |
| ISO/IEC 38507:2022 | ISO/IEC standard | P2 | Board-level governance implications of AI | Assess / not verified |
| ISO/IEC TR 5469:2024 | ISO/IEC technical report | P3 | AI and functional safety relationship | Assess / not verified |
| ISO/IEC TS 42119-2:2025 | ISO/IEC technical specification | P2 | AI system testing overview | Assess / not verified |
| ISO/IEC TS 4213:2022 | ISO/IEC technical specification | P3 | Classification-performance assessment | Assess / not verified |
| ISO/IEC DIS 42007 (draft, not final) | Draft ISO/IEC standard | P3 | Monitor AI system conformity-assessment approaches | Assess / not verified |
| NIST AI RMF 1.0 | Voluntary framework | P0 | Govern, Map, Measure, Manage evidence mapping | Documented: experimental risk export |
| NIST AI 600-1 (GenAI Profile) | Voluntary framework profile | P1 | Generative AI risk and assurance scenarios | Assess / not verified |
| NIST AI 100-2 (Adversarial ML taxonomy) | Technical publication | P2 | Security-specific evaluation vocabulary | Assess / not verified |
| AIUC-1 | Private/industry assurance standard | P2 | AI-agent assurance mappings; not an ISO certificate | Assess / not verified |
| CSA AI Controls Matrix | Industry controls framework | P2 | Cloud AI risks and control mapping | Assess / not verified |
| OECD AI Principles | Intergovernmental principles | P3 | High-level responsible-AI governance | Assess / not verified |
| UNESCO Recommendation on AI Ethics | Intergovernmental recommendation | P3 | Ethical AI governance reference | Assess / not verified |
| IEEE 7000 | IEEE standard | P3 | Ethical concerns in system design | Assess / not verified |
| IEEE 7001 | IEEE standard | P2 | Transparency of autonomous systems | Assess / not verified |
| IEEE 7003 | IEEE standard | P2 | Algorithmic bias considerations | Assess / not verified |

## 04. Security, privacy, forensics, and threat modeling (38)

| Standard / specification | Class | Priority | NovaFabric relevance | Repo evidence status |
|---|---|---|---|---|
| ISO/IEC 27001:2022 | ISO/IEC standard | P1 | Organizational ISMS evidence | Assess / not verified |
| ISO/IEC 27002:2022 | ISO/IEC standard | P1 | Technical and organizational security controls | Assess / not verified |
| ISO/IEC 27005 | ISO/IEC standard | P2 | Security risk assessment | Assess / not verified |
| ISO/IEC 27017 | ISO/IEC standard | P2 | Cloud security controls | Assess / not verified |
| ISO/IEC 27018 | ISO/IEC standard | P2 | Personal data protection in public cloud | Assess / not verified |
| ISO/IEC 27701:2025 | ISO/IEC standard | P1 | Privacy information management | Assess / not verified |
| ISO/IEC 29100 | ISO/IEC standard | P2 | Privacy framework | Assess / not verified |
| ISO/IEC 29134 | ISO/IEC standard | P2 | Privacy impact assessments | Assess / not verified |
| ISO/IEC 27035 series | ISO/IEC standards | P2 | Incident management | Assess / not verified |
| ISO/IEC 27036-3:2023 | ISO/IEC standard | P2 | Supply-chain security relationships | Assess / not verified |
| ISO/IEC 27037:2012 | ISO/IEC standard | P0 | Identification and preservation of digital evidence | Assess / not verified |
| ISO/IEC 27038:2014 | ISO/IEC standard | P0 | Digital redaction | Assess / not verified |
| ISO/IEC 27040:2024 | ISO/IEC standard | P1 | Secure storage | Assess / not verified |
| ISO/IEC 27041:2015 | ISO/IEC standard | P2 | Suitability of investigative methods | Assess / not verified |
| ISO/IEC 27042:2015 | ISO/IEC standard | P2 | Interpretation of digital evidence | Assess / not verified |
| ISO/IEC 27043:2015 | ISO/IEC standard | P2 | Investigation principles | Assess / not verified |
| ISO/IEC 27050 series | ISO/IEC standards | P2 | Electronic discovery | Assess / not verified |
| NIST Cybersecurity Framework 2.0 | Voluntary framework | P1 | Enterprise security evidence reporting | Assess / not verified |
| NIST SP 800-53 Rev. 5 | NIST control catalog | P1 | Security and privacy control evidence | Assess / not verified |
| NIST SP 800-61 Rev. 3 | NIST guidance | P2 | Incident response | Assess / not verified |
| NIST SP 800-92 | NIST guidance | P1 | Log management | Assess / not verified |
| NIST SP 800-57 series | NIST guidance | P2 | Cryptographic key management | Assess / not verified |
| NIST SP 800-63 suite | NIST guidance | P2 | Digital identity assurance | Assess / not verified |
| NIST SP 800-218 (SSDF) | NIST framework | P1 | Secure development practices | Assess / not verified |
| NIST SP 800-161 Rev. 1 | NIST guidance | P2 | Supply-chain security risk management | Assess / not verified |
| NIST SP 800-190 | NIST guidance | P2 | Container security | Assess / not verified |
| NIST SP 800-204 series | NIST guidance | P2 | Microservices and service-mesh security | Assess / not verified |
| OWASP Top 10 for LLM Applications 2026 | Community security framework | P1 | Current LLM application risk scenarios | Assess / not verified |
| OWASP Top 10 for Agentic Applications | Community security framework | P1 | Autonomous agent and tool-use threats | Assess / not verified |
| OWASP ASVS | Community verification standard | P2 | Web/API application security validation | Assess / not verified |
| OWASP API Security Top 10 | Community framework | P2 | Server API threat mapping | Assess / not verified |
| MITRE ATLAS | Community attack knowledge base | P1 | Adversarial ML attack patterns | Assess / not verified |
| MITRE ATT&CK | Community attack knowledge base | P2 | Infrastructure and identity attack patterns | Assess / not verified |
| MITRE CWE / CVE | Public classification systems | P2 | Weakness and vulnerability classification | Assess / not verified |
| CSA Cloud Controls Matrix | Industry control framework | P2 | Cloud security and privacy crosswalks | Assess / not verified |
| CIS Controls v8.1 | Community security controls | P2 | Operational security practices | Assess / not verified |
| CIS Kubernetes Benchmark | Community configuration benchmark | P2 | Kubernetes deployment hardening | Assess / not verified |
| AICPA Trust Services Criteria (SOC 2 reporting) | Assurance criteria | P2 | Audit evidence for service organizations; SOC 2 is not an ISO standard | Assess / not verified |

## 05. European legal and sectoral requirements (14)

| Standard / specification | Class | Priority | NovaFabric relevance | Repo evidence status |
|---|---|---|---|---|
| EU AI Act (Regulation EU 2024/1689) | EU regulation | P0 | Logging, technical documentation, oversight, transparency | Documented: experimental evidence export |
| GDPR (Regulation EU 2016/679) | EU regulation | P0 | PII capture, minimization, erasure, data subject rights | Documented: experimental evidence features |
| EU NIS2 Directive (EU 2022/2555) | EU directive | P2 | Cybersecurity reporting and controls for in-scope operators | Assess / not verified |
| EU DORA (Regulation EU 2022/2554) | EU regulation | P2 | ICT evidence, incident reporting, financial operational resilience | Assess / not verified |
| EU Cyber Resilience Act (EU 2024/2847) | EU regulation | P1 | Software product security and vulnerability governance; scope must be assessed | Assess / not verified |
| EU eIDAS (Regulation EU 910/2014; amended EU 2024/1183) | EU regulation | P1 | Trust services, qualified timestamps, EU digital identity | Assess / not verified |
| EU Data Act (Regulation EU 2023/2854) | EU regulation | P3 | Data access and cloud-switching use cases | Assess / not verified |
| EU Cybersecurity Act (Regulation EU 2019/881) | EU regulation | P3 | European cybersecurity certification schemes | Assess / not verified |
| MiFID II (Directive 2014/65/EU) | EU directive | P2 | Financial trading and client-order records | Assess / not verified |
| MiFIR (Regulation EU 600/2014) | EU regulation | P2 | Financial transaction reporting | Assess / not verified |
| EU MDR (Regulation EU 2017/745) | EU regulation | P2 | Clinical software technical documentation | Assess / not verified |
| EU IVDR (Regulation EU 2017/746) | EU regulation | P3 | In vitro diagnostic AI systems | Assess / not verified |
| European Health Data Space (Regulation EU 2025/327) | EU regulation | P3 | Health data interoperability and governance | Assess / not verified |
| European harmonised AI Act standards (CEN/CENELEC programme) | Standards programme | P1 | Monitor future OJ-cited harmonised standards; do not assert harmonisation prematurely | Assess / not verified |

## 06. US regulations and financial-sector guidance (17)

| Standard / specification | Class | Priority | NovaFabric relevance | Repo evidence status |
|---|---|---|---|---|
| HIPAA Privacy Rule / Security Rule | US regulation | P2 | Sensitive health information evidence and access controls | Assess / not verified |
| FDA 21 CFR Part 11 | US regulation | P2 | Electronic records and signatures | Assess / not verified |
| SEC Exchange Act Rule 17a-4 | US regulation | P2 | Retention and WORM-equivalent records | Assess / not verified |
| FINRA Rule 4511 | US industry regulation | P2 | Books, records, and retention | Assess / not verified |
| CFTC Regulation 1.31 | US regulation | P2 | Commodity-related recordkeeping | Assess / not verified |
| SEC Rule 613 / CAT NMS Plan | US regulation / plan | P3 | Event lifecycle audit pattern; not a CAT-compatible export | Assess / not verified |
| ECOA Regulation B, 12 CFR 1002.9 | US regulation | P2 | Decision reasons and adverse-action evidence | Assess / not verified |
| Federal Reserve SR 26-2 (2026) | US supervisory guidance | P2 | Current model-risk guidance replacing SR 11-7 | Assess / not verified |
| Federal Reserve SR 11-7 (superseded) | Historical US guidance | P3 | Legacy crosswalks only; mark superseded by SR 26-2 | Assess / not verified |
| OMB M-25-21 (2025) | US federal policy | P2 | Federal AI use and governance | Assess / not verified |
| OMB M-25-22 (2025) | US federal policy | P2 | Federal AI acquisition | Assess / not verified |
| OMB M-24-10 (superseded) | Historical US federal policy | P3 | Legacy reference; avoid presenting as current policy | Assess / not verified |
| OMB M-26-14 (2026) | US federal policy | P3 | Federal logging and network-visibility requirements | Assess / not verified |
| OMB M-26-15 (2026) | US federal policy | P3 | Federal post-quantum migration programme | Assess / not verified |
| Colorado AI Act SB24-205 | US state law | P3 | High-risk automated decision-making; monitor implementation changes | Assess / not verified |
| SOX (Sarbanes-Oxley Act) | US law | P3 | Internal controls and audit retention use cases | Assess / not verified |
| FedRAMP | US authorization programme | P3 | Cloud authorization evidence for federal hosted deployments | Assess / not verified |

## 07. Digital records, archiving, scientific reproducibility (22)

| Standard / specification | Class | Priority | NovaFabric relevance | Repo evidence status |
|---|---|---|---|---|
| ISO 15489-1:2016 | ISO standard | P1 | Creation, capture, and management of reliable records | Assess / not verified |
| ISO 16175-1:2020 / ISO TS 16175-2:2020 | ISO series | P2 | Software functionality for record management | Assess / not verified |
| ISO 14721:2025 (OAIS) | ISO standard | P1 | Long-term digital preservation model; replaces 2012 edition | Assess / not verified |
| ISO 16363 | ISO standard | P2 | Trustworthy digital repository audit and certification | Assess / not verified |
| ISO 17068:2017 | ISO standard | P2 | Trusted third-party repository for digital records | Assess / not verified |
| ISO 18128:2024 | ISO standard | P2 | Records-management risk assessment | Assess / not verified |
| ISO 23081 series | ISO series | P2 | Metadata for records | Assess / not verified |
| ISO 30301 | ISO standard | P2 | Management systems for records | Assess / not verified |
| ISO 19005 series (PDF/A) | ISO series | P3 | Long-lived human-readable evidence exports | Assess / not verified |
| ISO 28500 (WARC) | ISO standard | P3 | Web archival records | Assess / not verified |
| IETF RFC 8493 (BagIt) | IETF RFC | P2 | Fixity manifests and archive packaging | Assess / not verified |
| RO-Crate 1.3 | Community specification | P2 | Research-object packaging with JSON-LD | Assess / not verified |
| FAIR data principles | Community principles | P1 | Findable, accessible, interoperable, reusable evidence | Assess / not verified |
| FAIR for Research Software (FAIR4RS) | Community principles | P2 | Reusable scientific software | Assess / not verified |
| DataCite Metadata Schema 4.7 | Community metadata specification | P2 | Persistent identification and citation metadata | Assess / not verified |
| PREMIS Data Dictionary | Library of Congress preservation metadata | P2 | Preservation actions and evidence provenance | Assess / not verified |
| Dublin Core Metadata Terms | DCMI specification | P2 | Descriptive metadata interoperation | Assess / not verified |
| DOI / ISO 26324 | ISO standard | P2 | Persistent identification of citable evidence | Assess / not verified |
| ACM Artifact Review and Badging | Research policy/framework | P2 | Available, evaluated, reusable artifact expectations | Assess / not verified |
| FORCE11 Software Citation Principles | Community principles | P3 | Scientific software citation | Assess / not verified |
| ISO/IEC 25010 | ISO/IEC standard | P2 | Software quality characteristics for reproducibility | Assess / not verified |
| ISO/IEC/IEEE 29119 series | International testing standards | P2 | Evidence-backed test design and execution | Assess / not verified |

## 08. Supply-chain, licensing, packaging, and release integrity (16)

| Standard / specification | Class | Priority | NovaFabric relevance | Repo evidence status |
|---|---|---|---|---|
| SPDX 3.0 / ISO/IEC 5962:2021 | International/open specification | P1 | SBOM, AI asset, license and dependency metadata | Assess / not verified |
| CycloneDX 1.7 / ECMA-424 (2nd ed., 2025) | Ecma standard | P1 | AI BOM, CBOM, dependency and attestation metadata | Documented: experimental AIBOM |
| Package URL / ECMA-427 | Ecma standard | P2 | Identifying third-party software packages | Assess / not verified |
| SLSA Build provenance | Open supply-chain framework | P0 | Reproducible build provenance for released artifacts | Documented: release provenance |
| Sigstore (Fulcio, Rekor, Cosign) | Open ecosystem specifications | P1 | Build/release identity and verification | Assess / not verified |
| The Update Framework (TUF) | Open specification | P1 | Securing software release metadata and update integrity | Assess / not verified |
| OpenChain ISO/IEC 5230 | ISO/IEC standard | P2 | Open-source license compliance | Assess / not verified |
| OpenChain ISO/IEC 18974 | ISO/IEC standard | P2 | Open-source security assurance | Assess / not verified |
| OpenSSF Scorecard | Community security metrics | P1 | Repository supply-chain health | Assess / not verified |
| OpenSSF Best Practices Badge | Community program | P2 | Open-source governance assurance | Assess / not verified |
| CISA SBOM Minimum Elements | US guidance | P2 | Procurement-visible inventory expectations | Assess / not verified |
| OCI Image Specification | Open Container Initiative specification | P1 | Portable container images | Assess / not verified |
| OCI Runtime Specification | Open Container Initiative specification | P2 | Portable container runtime | Assess / not verified |
| OCI Distribution Specification | Open Container Initiative specification | P1 | Container registry interfaces | Assess / not verified |
| SPDX License List / REUSE Specification | Open metadata conventions | P2 | Machine-readable licensing metadata | Assess / not verified |
| Reproducible Builds guidance | Community methodology | P2 | Build result determinism and verification | Assess / not verified |

## 09. Assurance cases, critical systems, and sector-specific safety (15)

| Standard / specification | Class | Priority | NovaFabric relevance | Repo evidence status |
|---|---|---|---|---|
| ISO/IEC/IEEE 15026 series | International standards | P1 | System and software assurance, including assurance cases | Assess / not verified |
| OMG Structured Assurance Case Metamodel (SACM) | OMG specification | P1 | Machine-readable assurance argument exchange | Documented: experimental assurance-case concept |
| Goal Structuring Notation (GSN) Community Standard | Community standard | P1 | Structured safety and assurance arguments | Documented: experimental assurance-case concept |
| UL 4600 | UL standard | P2 | Autonomous-system safety assurance cases | Assess / not verified |
| IEC 61508 series | IEC standards | P3 | Functional safety of electrical/electronic systems | Assess / not verified |
| ISO 26262 series | ISO standards | P3 | Automotive functional safety | Assess / not verified |
| ISO 21448 (SOTIF) | ISO standard | P3 | Safety of the intended functionality | Assess / not verified |
| ISO/SAE 21434 | ISO/SAE standard | P3 | Road-vehicle cybersecurity | Assess / not verified |
| IEC 62443 series | IEC standards | P3 | Industrial automation and control system security | Assess / not verified |
| ISO 13485:2016 | ISO standard | P2 | Medical-device quality-management records | Assess / not verified |
| ISO 14971:2019 | ISO standard | P2 | Medical-device risk management | Assess / not verified |
| IEC 62304:2006 + amendments | IEC standard | P2 | Medical device software life cycle | Assess / not verified |
| IEC 81001-5-1 | IEC standard | P2 | Health software security lifecycle | Assess / not verified |
| NIST SP 800-30 Rev. 1 | NIST guidance | P2 | Information-system risk assessment | Assess / not verified |
| ISO 31000:2018 | ISO standard | P2 | Enterprise risk management | Assess / not verified |

## 10. Identity, access, trust delegation, and enterprise operations (16)

| Standard / specification | Class | Priority | NovaFabric relevance | Repo evidence status |
|---|---|---|---|---|
| OpenID Connect Core 1.0 | OpenID Foundation specification | P1 | Server mode identity federation | Documented: experimental |
| OAuth 2.0 (RFC 6749) and Security BCP | IETF specifications | P1 | API access delegation | Assess / not verified |
| OAuth 2.0 PKCE (RFC 7636) | IETF RFC | P1 | Secure public-client authorization flows | Assess / not verified |
| OAuth DPoP (RFC 9449) | IETF RFC | P2 | Proof-of-possession protection against token replay | Assess / not verified |
| OAuth mTLS (RFC 8705) | IETF RFC | P2 | Certificate-bound tokens | Assess / not verified |
| SAML 2.0 | OASIS standard | P2 | Enterprise SSO interoperability | Documented: experimental |
| SCIM 2.0 (RFC 7643 / 7644) | IETF RFCs | P2 | User and group provisioning | Documented: experimental |
| WebAuthn / FIDO2 | W3C/FIDO specifications | P2 | Stronger interactive authentication | Assess / not verified |
| W3C Decentralized Identifiers (DID) v1.0 | W3C Recommendation | P2 | Portable agent/issuer identifiers | Assess / not verified |
| SPIFFE ID / SPIRE | CNCF ecosystem specification | P2 | Workload identities in multi-tenant clusters | Assess / not verified |
| Kubernetes Pod Security Standards | Kubernetes policy standard | P1 | Least-privilege cluster deployment | Assess / not verified |
| Kubernetes RBAC API | Kubernetes specification | P1 | Tenant permissions and service identities | Assess / not verified |
| ISO/IEC 20000-1 | ISO/IEC standard | P3 | IT service management for managed deployments | Assess / not verified |
| ISO 22301 | ISO standard | P3 | Business continuity and recovery evidence | Assess / not verified |
| ISO 9001 | ISO standard | P3 | General quality management processes | Assess / not verified |
| W3C WCAG 2.2 | W3C Recommendation | P2 | Accessible evidence-review dashboard | Assess / not verified |

## Additional interoperability and assurance candidates (37; researched 2026-11-21)

These **37 new references** are research candidates with publisher/specification links. Their inclusion does **not** mean that NovaFabric implements them or that a requirement is applicable. The four additions below cover existing gaps in the original 227-entry landscape. Research priority (P0-P3) is not GitHub issue severity.

## 11. Evidence transport, canonical records and provenance validation (10)

| Standard / specification | Class | Priority | NovaFabric relevance | Repo evidence status |
|---|---|---|---|---|
| [RFC 9421 — HTTP Message Signatures](https://www.rfc-editor.org/info/rfc9421/) | IETF Standards Track | P1 | Optional end-to-end authentication of evidence API requests and responses; verify covered fields and replay resistance | Assess / not verified |
| [RFC 9530 — HTTP Digest Fields](https://www.rfc-editor.org/info/rfc9530/) | IETF Standards Track | P1 | Portable Content-Digest and Repr-Digest for transferred evidence; digests alone do not authenticate senders | Assess / not verified |
| [RFC 9535 — JSONPath](https://www.rfc-editor.org/info/rfc9535/) | IETF Standards Track | P2 | Portable queries for structured evidence and assertions; no user query execution implied | Assess / not verified |
| [RFC 9457 — Problem Details for HTTP APIs](https://www.rfc-editor.org/info/rfc9457/) | IETF Standards Track | P2 | Machine-readable non-sensitive error responses for future evidence APIs | Assess / not verified |
| [RFC 9562 — UUID](https://www.rfc-editor.org/info/rfc9562/) | IETF Standards Track | P2 | Interoperable globally unique IDs for runs, receipts and events; preserve existing IDs | Assess / not verified |
| [RFC 3339 / RFC 9557 — Internet timestamps](https://www.rfc-editor.org/info/rfc3339/) | IETF Standards Track (base and update) | P1 | Explicit UTC offsets and consistent timestamp parsing; distinguish event time from trusted TSA time | Assess / not verified |
| [RFC 8610 / RFC 9682 — CDDL](https://www.rfc-editor.org/info/rfc8610/) | IETF Standards Track (base and update) | P2 | Formal definition of optional CBOR/COSE exchange profiles without replacing capsule JSON schemas | Assess / not verified |
| [W3C RDF Dataset Canonicalization 1.0 (RDFC-1.0)](https://www.w3.org/TR/rdf-canon/) | W3C Recommendation | P1 | Stable hashes and possible signatures for semantically equivalent provenance RDF datasets | Assess / not verified |
| [W3C PROV-CONSTRAINTS](https://www.w3.org/TR/prov-constraints/) | W3C Recommendation | P1 | Semantic validation of PROV relations in addition to syntax/schema checks | Assess / not verified |
| [W3C PROV-AQ](https://www.w3.org/TR/prov-aq/) | W3C Working Group Note | P2 | Provenance record discovery and query patterns for optional sharing APIs | Assess / not verified |

## 12. Agent delegation, authorization and continuous access (13)

| Standard / specification | Class | Priority | NovaFabric relevance | Repo evidence status |
|---|---|---|---|---|
| [RFC 8693 — OAuth 2.0 Token Exchange](https://www.rfc-editor.org/info/rfc8693/) | IETF Standards Track | P1 | Delegation and impersonation boundaries for agent-to-tool chains; keep actor and subject distinct | Assess / not verified |
| [RFC 8707 — OAuth 2.0 Resource Indicators](https://www.rfc-editor.org/info/rfc8707/) | IETF Standards Track | P1 | Audience-bound access tokens to reduce cross-service token confusion | Assess / not verified |
| [RFC 9396 — OAuth 2.0 Rich Authorization Requests](https://www.rfc-editor.org/info/rfc9396/) | IETF Standards Track | P1 | Fine-grained requested tool actions, resource names and constraints rather than broad scopes | Assess / not verified |
| [RFC 9470 — OAuth 2.0 Step-Up Authentication](https://www.rfc-editor.org/info/rfc9470/) | IETF Standards Track | P2 | Optional reauthentication on sensitive evidence export or administrative operations | Assess / not verified |
| [RFC 9728 — OAuth Protected Resource Metadata](https://www.rfc-editor.org/info/rfc9728/) | IETF Standards Track | P1 | Discover authorization-server requirements on protected agent/tool resource endpoints | Assess / not verified |
| [RFC 9068 — JWT Profile for OAuth 2.0 Access Tokens](https://www.rfc-editor.org/info/rfc9068/) | IETF Standards Track | P2 | Interoperable JWT access-token claims for server mode, not for offline local mode | Assess / not verified |
| [RFC 8414 — OAuth Authorization Server Metadata](https://www.rfc-editor.org/info/rfc8414/) | IETF Standards Track | P2 | Issuer and endpoint discovery for standards-based server authorization | Assess / not verified |
| [OpenID AuthZEN Authorization API 1.0](https://openid.net/specs/authorization-api-1_0-final.html) | OpenID Final Specification (2026-01) | P1 | Interoperable PDP/PEP decision interface for policy-enforced evidence access | Assess / not verified |
| [OpenID Federation 1.1](https://openid.net/specs/openid-federation-1_1-final.html) | OpenID Final Specification (2026-05) | P2 | Signed federation trust chains when multiple organizations exchange receipts | Assess / not verified |
| [OpenID Shared Signals Framework 1.0](https://openid.net/specs/openid-sharedsignals-framework-1_0-final.html) | OpenID Final Specification (2025) | P2 | Security event sharing between trusted participants; conditional on server integrations | Assess / not verified |
| [OpenID CAEP 1.0](https://openid.net/specs/openid-caep-1_0-final.html) | OpenID Final Specification (2025) | P2 | Session revocation and continuous authorization signals for long-running agents | Assess / not verified |
| [NIST SP 800-162 — Attribute-Based Access Control](https://csrc.nist.gov/pubs/sp/800/162/upd2/final) | NIST guidance | P1 | Define actor, resource, action, environment attributes and policy-decision evidence | Assess / not verified |
| [NIST SP 800-207 — Zero Trust Architecture](https://csrc.nist.gov/pubs/sp/800/207/final) | NIST guidance | P1 | Server-side least privilege and explicit trust boundaries; not required for local CLI use | Assess / not verified |

## 13. Data lifecycle, product security and vulnerability communication (9)

| Standard / specification | Class | Priority | NovaFabric relevance | Repo evidence status |
|---|---|---|---|---|
| [NIST SP 800-88 Rev. 2 (2025)](https://csrc.nist.gov/pubs/sp/800/88/r2/final) | NIST guidance (final) | P1 | Distinguish cryptographic erase, media sanitization and retained immutable evidence; prove limits of deletion | Assess / not verified |
| [ISO/IEC 20889:2018](https://www.iso.org/standard/69373.html) | ISO/IEC international standard | P1 | Terminology and residual re-identification risk for PII de-identification/redaction evidence | Assess / not verified |
| [ISO/IEC 29147:2018](https://www.iso.org/standard/72311.html) | ISO/IEC international standard (revision in progress) | P1 | Coordinated vulnerability disclosure policy and communication for an evidence-security product | Assess / not verified |
| [ISO/IEC 30111:2019](https://www.iso.org/standard/69725.html) | ISO/IEC international standard (revision in progress) | P1 | Intake, triage, remediation and traceable vulnerability-handling workflows | Assess / not verified |
| [OpenSSF OSPS Baseline v2026.08.28](https://baseline.openssf.org/) | OpenSSF community security baseline | P1 | Maturity-tiered OSS project security checklist; compare CI/release posture and retain evidence | Assess / not verified |
| [OASIS CSAF 2.1 (Committee Specification 01)](https://docs.oasis-open.org/csaf/csaf/v2.1/csaf-v2.1.html) | OASIS Committee Specification (2026-11; not yet an OASIS Standard) | P2 | Structured security advisories for future product vulnerability disclosures; verify profile before export | Assess / not verified |
| [OpenVEX v0.2.0](https://github.com/openvex/spec/blob/main/OPENVEX-SPEC.md) | Community draft specification | P2 | Machine-readable vulnerability applicability statements linked to released components | Assess / not verified |
| [ISO/IEC 27004:2016](https://www.iso.org/standard/64120.html) | ISO/IEC international standard (revision in progress) | P2 | Measurement and monitoring plan for information-security controls and their effectiveness | Assess / not verified |
| [ISO 19011:2026](https://www.iso.org/standard/19011) | ISO international standard (guidelines) | P2 | Repeatable internal audit methods for management-system evidence packs, not certification | Assess / not verified |

## 14. Verification, measurement and reproducible software research (5)

| Standard / specification | Class | Priority | NovaFabric relevance | Repo evidence status |
|---|---|---|---|---|
| [IEEE 1012-2024](https://ieeesystemscouncil.org/standards/system-engineering-standards) | IEEE standard | P1 | Independent verification and validation planning for replay, signatures and negative tests | Assess / not verified |
| [ISO/IEC/IEEE 29148:2018](https://www.iso.org/standard/72089.html) | Joint international standard (revision draft under development) | P2 | Trace requirements to evidence artefacts, acceptance criteria and version-pinned tests | Assess / not verified |
| [ISO/IEC 25023:2016](https://www.iso.org/standard/35747.html) | ISO/IEC international standard (revision draft under development) | P2 | Quality measurements for reliability, correctness, performance and maintainability | Assess / not verified |
| [Citation File Format 1.2.0 (CFF)](https://github.com/citation-file-format/citation-file-format/blob/main/schema-guide.md) | Open community metadata specification | P2 | Machine-readable citations for reproducible evaluation software and benchmark artefacts | Assess / not verified |
| [Software Heritage persistent identifiers (SWHID) v1.2](https://www.swhid.org/swhid-specification/) | Open community identifier specification | P2 | Content-addressed source identifiers for archived code and reproducible experiment evidence | Assess / not verified |

## Version and currency review

- **SCITT:** Add RFC 9943 and RFC 9942 (June 2026) as potential signed-statement and receipt interop targets. No migration should occur without a compatibility and threat-model RFC.
- **ISO 14721 OAIS:** Earlier NovaFabric mapping material references the 2012 edition; the 2025 edition is current.
- **ISO/IEC 27701:** The 2025 edition replaced 2019.
- **CycloneDX:** The 2025 second edition of ECMA-424 defines CycloneDX 1.7.
- **RO-Crate:** The specification site reports 1.3 as current long-term release; older 1.1 references should be updated or pinned as deliberate compatibility targets.
- **DataCite:** Schema 4.7 released March 2026; older 4.5 crosswalk examples need version review.
- **Federal Reserve:** SR 26-2 superseded SR 11-7 in April 2026.
- **US federal AI guidance:** OMB M-25-21 and M-25-22 replaced earlier 2024 memoranda. Validate any 2024 citations and the exact obligation before publishing.
- **OWASP:** The 2026 LLM Top 10 is newer than the documented 2025 risk suite. Retain historical test profile as a pinned baseline and add a separate updated profile.
- **Readme conflict:** Public README describes capsule and bundle formats as frozen at v1.0 while standards-conformance.md says they are not frozen until a v1.0 freeze; reconcile with HEAD and release policy.
- **Document staleness:** Some historical project documentation lists RFC 3161 and other features as unavailable, while the [public conformance map](https://github.com/MSKazemi/novafabric/blob/main/docs/standards-conformance.md) reports RFC 3161 as available (opt-in). Reconcile outdated references against version-pinned public evidence before making capability claims.

## Suggested roadmap, not yet applied to GitHub

1. P0: Build a canonical versioned `standards-registry` machine-readable model with identifiers, issuer, edition, status, source URL, mapped product feature, evidence receipt, conformance profile, validation command, tests, and last review timestamp.
2. P0: Evaluate SCITT RFC 9943 / COSE Receipts RFC 9942 as a **new optional export** interoperable with existing DSSE/Merkle evidence; avoid a third top-level capsule format.
3. P0: Add offline independent verification fixtures for timestamp trust, certificate revocation, signature canonicalization, Merkle inclusion/consistency, redaction proof integrity, and cross-version evidence replay.
4. P1: Align AI Governance exports to AI Act, ISO/IEC 42001, 42005, NIST AI RMF 1.0 / NIST AI 600-1 while clearly labeling `evidence` vs `mapping` vs `not assessed`.
5. P1: Update documented version references, deprecate historical rules, and reconcile inconsistent project documentation.
6. P1: Keep conformance matrices version-pinned and maintain tests for the existing MCP, OpenTelemetry GenAI, OpenLineage, PROV, CycloneDX, and C2PA exports.
7. P2: Consider sector packs (financial records, healthcare, research archival) only when a partner or real use case justifies them.

## Primary sources and project references

- [ISO AI catalogue](https://www.iso.org/committee/6794475/x/catalogue/)
- [ISO information security catalogue](https://www.iso.org/committee/45306/x/catalogue/)
- [ISO records catalogue](https://www.iso.org/committee/48856/x/catalogue/)
- [IETF RFC Index](https://www.rfc-editor.org/rfc-index.html)
- [RFC 9943 SCITT](https://www.rfc-editor.org/info/rfc9943/)
- [RFC 9942 COSE receipts](https://www.rfc-editor.org/info/rfc9942/)
- [W3C PROV](https://www.w3.org/TR/prov-o/)
- [W3C Verifiable Credentials](https://www.w3.org/TR/vc-data-model/)
- [Ecma-424 CycloneDX](https://ecma-international.org/publications-and-standards/standards/ecma-424/)
- [SPDX specifications](https://spdx.dev/use/specifications/)
- [OpenTelemetry GenAI](https://opentelemetry.io/docs/specs/semconv/gen-ai/)
- [EU AI Act](https://eur-lex.europa.eu/eli/reg/2024/1689)
- [EU AI Act standardization](https://digital-strategy.ec.europa.eu/en/faqs/understanding-standardisation-ai-act)
- [EU qualified timestamps](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=OJ%3AL_202501929)
- [NIST GenAI profile](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence)
- [ISO OAIS 2025](https://www.iso.org/standard/87471.html)
- [ISO privacy management](https://www.iso.org/standard/27701)
- [OWASP LLM 2026](https://genai.owasp.org/resource/owasp-genai-llm-top-10-2026/)
- [RO-Crate specs](https://www.researchobject.org/ro-crate/specification)
- [DataCite latest](https://schema.datacite.org/versions.html)
- [Federal Reserve SR 26-2](https://www.federalreserve.gov/supervisionreg/srletters/SR2602.htm)
- [OMB memoranda](https://www.whitehouse.gov/omb/information-resources/guidance/memoranda/)
- [NovaFabric public conformance map](https://github.com/MSKazemi/novafabric/blob/main/docs/standards-conformance.md)

**Total references in this baseline:** 264 (227 initial + 37 additional).

**Register maintenance note:** Proposals above are not implementation authorizations. For live capability status, consult version-pinned source code, tests, and the public conformance document.