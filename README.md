# Standards — cross-project technical reference hub

Public, version-aware research registers for **standards, specifications, protocols, guidance, and regulatory references** relevant to open-source engineering and AI-agent systems.

## Project standards registers

| Project | Register | Reference scope and status |
| --- | --- | --- |
| [YazSes](https://github.com/MSKazemi/yazses) | [YazSes register](projects/yazses.md) | **98** entries; already on `main` |
| [KubeIntellect](https://github.com/MSKazemi/kubeintellect) | [KubeIntellect register](projects/kubeintellect.md) · [traceability](projects/kubeintellect-traceability.md) · [CSV](data/kubeintellect-standards.csv) | **239** candidates in 11 families; proposed review-branch addition |
| [NovaFabric](https://github.com/MSKazemi/novafabric) | [Review draft PR #1](https://github.com/MSKazemi/standards/pull/1) | **227** candidate references; unmerged PR (no file on `main` yet) |
| [Agent Movement](https://github.com/MSKazemi/agent-movement) | [Review draft PR #2](https://github.com/MSKazemi/standards/pull/2) | **284** inventory rows (42 dated + 242 discovery candidates); unmerged PR (no file on `main` yet) |

**Cross-project references:** [Standards reuse and research matrix](projects/cross-project-standards.md).  
**Editorial controls:** [Verification and conformance methodology](docs/verification-methodology.md).

> Counts are **catalogue records, not distinct standards**; overlaps occur across projects. Provisional entries may be withdrawn, obsolete or incorrect. Each register is a research inventory, not a legal opinion, certification claim or software implementation status.

## How to read a register

Published international standards, IETF RFCs, W3C Recommendations, industry/community specifications, NIST/OWASP guidance, security benchmarks, unpublished drafts and laws are **different types of material**. A reference's presence means potential relevance, not automatic applicability. Check the exact edition and publisher before using the reference as a normative requirement; many ISO/IEC/IEEE/CIS texts are not freely redistributable.

**Core** and **Targeted** prioritize research effort; **Conditional** and **Scope-check** depend on capability, jurisdiction or deployment; **Watch** denotes emerging or adjacent material. These are not certification levels.

## Ownership and source of truth

- **This repository** owns public standards discovery metadata, comparative mapping and publisher verification notes.
- The individual software repositories own implementation, test results, design decisions, release gates and live issue tracking.
- Draft pull requests remain independent: this review branch does **not** merge NovaFabric or Agent Movement inventories.
- **No private implementation material or confidential security findings** belong in the public standards repository.

## Review and contribution

Start from [verification methodology](docs/verification-methodology.md). Verify specific identifiers and editions with primary issuing organizations; record the date and source; map only scoped, testable controls to the owning implementation. Do not reproduce copyright-protected standards or claim independent certification without evidence.

**Catalogued on 21 November 2026 (Europe/Rome).** The KubeIntellect content is proposed for review, with no runtime changes, no automatic compliance assertions and no merger of the other draft PRs.
