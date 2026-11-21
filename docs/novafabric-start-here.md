# Start here: standards for NovaFabric

**One-page guide — 2026-11-21 · Status: proposed priorities, not completed engineering work.**

> **264 entries = things to consider, not 264 features to build.**
>
> The goal is simple: a third party should be able to understand what NovaFabric captured, independently verify evidence integrity, and interpret the results without relying only on NovaFabric's own claims.

## 1. Three decisions

| Question | Answer |
|---|---|
| **What should NovaFabric implement?** | Only standards that solve a real interoperability, security, portability or customer requirement. |
| **What should NovaFabric test?** | First test standards the project already **reports supporting**, especially evidence verification and export formats. |
| **Does standards support mean compliance?** | **No.** A supported file format, evidence export or internal test is **not** a certification or a legal compliance verdict. |

## 2. What matters now, next and later

This is a **proposed work order**, not a statement that these features are missing. Consult the [public product conformance document](https://github.com/MSKazemi/novafabric/blob/main/docs/standards-conformance.md) for what NovaFabric reports as implemented and how mature it is.

| When | Focus | Standards / specifications | Desired outcome |
|---|---|---|---|
| **NOW — verify core claims** | Signed evidence and trusted time | **DSSE, in-toto, RFC 3161, JSON Schema**, relevant Merkle proof conventions | An external verifier accepts a valid bundle and rejects altered, incomplete or untrusted evidence. |
| **NOW — verify interoperability** | Portable model/tool and provenance records | **OpenTelemetry GenAI, W3C PROV, OpenLineage, MCP** | A version-pinned independent parser or consumer understands supported exports. |
| **NOW — verify privacy and replay limits** | Data redaction, integrity and realistic replay | **NIST/ISO privacy references** plus existing NovaFabric replay contracts | Tests demonstrate what is removed, what remains, and which replay claims are *not* possible for remote models. |
| **NEXT — evaluate, do not assume** | Shared API security and agent delegation | **OAuth token exchange, AuthZEN, HTTP Message Signatures, Digest Fields** | Scoped, reviewed implementation plan only if server deployments need them. |
| **LATER — demand-driven** | Evidence interoperability and regulated sectors | **SCITT/COSE receipts, ISO/IEC 42001, EU AI Act, sector-specific controls** | Adopt a narrow, justified export profile or evidence mapping; no blanket certification claim. |

**Important:** Some catalogue rows carry `P0` even if the proposal is “later.” In the 264-entry register, `P0–P3` means **technical relevance**, not GitHub issue urgency or implementation order. The **NOW/NEXT/LATER** table above is the recommended *work order*.

## 3. The workflow in five simple steps

```text
Pick one relevant standard
        |
        v
Find the exact feature + edition/profile already used by NovaFabric
        |
        v
Run positive, negative and independent-tool tests
        |
        v
Keep reproducible evidence (commands, inputs, hashes, outputs, limitations)
        |
        v
State exactly what is supported, and what is NOT proved
```

**Worked example — DSSE, evidence signing**

1. **Choose a small claim:** “An exported Evidence Bundle can be verified using the selected DSSE/in-toto profile.” This is a *candidate claim*, not evidence of a test run here.
2. **Locate the implementation:** Read the relevant signing/export code, the public conformance page and existing tests. Record the product commit and format version.
3. **Test success:** Generate a non-secret signed fixture; verify it with NovaFabric **and an independent implementation**.
4. **Test failure:** Modify the signed payload, remove an artifact, change the key or damage its trust data. Each relevant case should be detected and reported accurately.
5. **Publish the result:** Link raw commands and outputs; say which exact profile was tested. **Do not say** “NovaFabric is certified” or “every type of timestamp is legally qualified.”

A cryptographically valid signature proves **integrity under a chosen key/trust policy**; it does not establish the truth of what the agent said, the safety of its actions, or regulatory compliance.

## 4. Give Claude Code only three jobs to start

| Job | Concrete output | How to know it is done | Detailed work packet |
|---|---|---|---|
| **A. Check current claims** | Table: standard + version + actual command + artifact + implementation/test reference + limitation | The selected public “works today” claims are traceable to real evidence or explicitly marked unverified | [NF-STD-01](../projects/novafabric-standards-adoption-plan.md#nf-std-01--create-an-evidence-backed-claim-inventory) |
| **B. Prove evidence verification** | Portable fixture and positive/negative test results using an independent verifier | Valid signatures succeed; altered data, wrong trust and missing evidence fail with preserved logs | [NF-STD-02](../projects/novafabric-standards-adoption-plan.md#nf-std-02--independent-offline-evidence-verification) |
| **C. Check replay and redaction** | Test matrix for replay modes, missing data, PII redaction and unsupported claims | Documentation states precisely what replay/redaction guarantees and does not guarantee | [NF-STD-03](../projects/novafabric-standards-adoption-plan.md#nf-std-03--replay-integrity-and-evidence-loss-failure-modes) and [NF-STD-04](../projects/novafabric-standards-adoption-plan.md#nf-std-04--privacy-retention-and-erasure-proof-boundaries) |

**Before creating issues:** inspect existing NovaFabric issues, PRs, ADRs, and tests to avoid duplicate work. Only create appropriately scoped work in the **owning product repository** after that check. The [12 proposed work packets](../projects/novafabric-standards-adoption-plan.md) are a backlog of ideas, **not** 12 tasks already created or completed.

## 5. Where each thing lives

| You want to… | Go to |
|---|---|
| Understand the approach | **This page** |
| Find all candidate standards and categories | [NovaFabric 264-entry register](../projects/novafabric.md) |
| Filter records or track publisher links and review state | [Machine-readable CSV](../data/novafabric-standards.csv) |
| See detailed engineering tasks and acceptance criteria | [NovaFabric adoption workplan](../projects/novafabric-standards-adoption-plan.md) |
| Follow the complete adoption method | [How to use standards](how-to-use-standards.md) |
| Record one standards adoption decision | [Assessment template](../templates/standard-adoption-record.md) |
| Check what the **product actually reports supporting** | [NovaFabric public standards-conformance page](https://github.com/MSKazemi/novafabric/blob/main/docs/standards-conformance.md) |
| Review real implementation and tests | [NovaFabric code repository](https://github.com/MSKazemi/novafabric) |

## 6. What is complete, and what is not

**Completed in this standards repository:** candidate research register, a machine-readable inventory, adoption methodology, proposed work packets and this quick guide.

**Not established by this documentation:** implementation of new standards, independent verification of every reference, legal applicability, certifications, completed conformance testing, or approval to change NovaFabric's architecture.

**Guardrails for any future product work:** preserve offline verification, privacy/redaction defaults, nonblocking capture, backward compatibility and the existing **two top-level formats** (Run Capsule and Evidence Bundle). A new interchange standard may justify an *optional profile*, not an automatic new storage format.

The next concrete action is **Job A**, followed by **Job B**; evaluate Job C alongside them once the existing test and issue inventory is understood.
