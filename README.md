# Standards — technical reference register

A version-aware, public index of **standards, specifications, protocols, guidance, and regulatory references** relevant to open-source engineering and research projects.

## Start here

**Using standards for NovaFabric?** Read the [plain-English NovaFabric quick start](docs/novafabric-start-here.md) first. It answers three questions: **what to verify now, what to consider later, and the first three concrete engineering jobs.** The full list of 264 references is supporting research, **not** 264 mandatory features or conformance claims.

## Project registers

| Project | Register | Scope |
|---|---|---|
| [YazSes](https://github.com/MSKazemi/yazses) | [YazSes standards and applicability](projects/yazses.md) | Offline dictation, ASR/audio, multilingual text, accessibility, privacy/security, AI, open-source supply chains, desktop/agent interoperability, optional XR and biosignals |
| [NovaFabric](https://github.com/MSKazemi/novafabric) | [NovaFabric standards and regulatory landscape](projects/novafabric.md) | AI agent run evidence, cryptographic verification, provenance, replay, governance, privacy, identity, supply-chain integrity, regulated sectors and scientific archiving |

The YazSes register contains **98 reference entries across 10 categories**, and the NovaFabric register contains **264 reference entries across 14 categories** (227 initial references + 37 additional candidates), based on research dated **2026-11-21**. Counts are per-project; overlapping references may appear in more than one register.

## How to use the registers

The [standards adoption workflow](docs/how-to-use-standards.md) explains how to assess legal applicability, choose a versioned technical profile, create independent conformance tests, and make appropriately scoped claims. The [adoption record template](templates/standard-adoption-record.md) is reusable across projects. NovaFabric also has a [prioritized workplan](projects/novafabric-standards-adoption-plan.md) and [filterable CSV](data/novafabric-standards.csv). Research priorities are not product task urgency or proof of compliance.

## How to interpret the lists

A listing indicates **potential relevance**, not mandatory applicability or certification. Engineering standards, voluntary frameworks, operating-system API specifications, and law/regulation are identified separately. Requirements change with jurisdiction, edition, product claims, and deployment context; check official sources before adopting a requirement. Some ISO/IEC/IEEE standard texts must be purchased under the publisher's terms; this repository links to official landing pages and **does not reproduce copyrighted standards**.

For each project, document a standard's scope, edition, applicability, mapped feature, implementation evidence, tests, known gaps, and review status. The presence of a reference does **not** mean compliance or testing is complete.

## Project ownership and source of truth

- **This repository** is the home for the cross-domain standards index and the per-project YazSes and NovaFabric applicability inventories.
- **[YazSes](https://github.com/MSKazemi/yazses)** remains the source of truth for actual software behavior, tests, ADRs, research protocols and implementation decisions, including [AGENTS.md](https://github.com/MSKazemi/yazses/blob/main/AGENTS.md).
- **[NovaFabric](https://github.com/MSKazemi/novafabric)** remains the source of truth for shipped software behavior, tests and conformance claims, including its [standards-conformance reference](https://github.com/MSKazemi/novafabric/blob/main/docs/standards-conformance.md).
- Proposed engineering work should link existing project issues rather than duplicating their tracking here.
- No private business or confidential material should be included in this public repository.

## Contribution / review

Before updating a reference, check the publisher's catalogue and the latest edition; prefer an official landing page to a direct PDF, distinguish **official standard** from **community specification**, and use dated verification notes. Do not make legal, medical, security or accessibility certification claims without scope-specific documented evidence.

This repository is an informational research catalogue, not legal advice.
