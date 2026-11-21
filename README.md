# Standards — technical reference register

A version-aware, public index of **standards, specifications, protocols, guidance, and regulatory references** relevant to open-source engineering and research projects.

## Project registers

| Project | Register | Scope |
|---|---|---|
| [YazSes](https://github.com/MSKazemi/yazses) | [YazSes standards and applicability](projects/yazses.md) | Offline dictation, ASR/audio, multilingual text, accessibility, privacy/security, AI, open-source supply chains, desktop/agent interoperability, optional XR and biosignals |
| **Agent Movement (research)** | [Agent Movement standards register](projects/agent-movement.md) · [284-entry CSV](data/agent-movement-standards.csv) | Agent-to-agent/tool protocols, continuity, compatibility, delegated authorization, identity, cryptography, provenance, distributed systems, cloud/edge, AI governance, robotics and regulatory references |

The YazSes register currently contains **98 reference entries across 10 categories**, originally researched on **2026-11-21**.

The Agent Movement register contains **284 catalog entries** (42 previously version-tracked references plus 242 additional discovery candidates across 16 topical groups), assembled on **2026-11-21**. Many added entries remain **unverified for exact current edition and maturity**; the list is a research inventory, not a certification or 284 unique normative standards. See its [verification backlog](projects/agent-movement-verification.md).

## How to interpret the lists

A listing indicates **potential relevance**, not mandatory applicability or certification. Engineering standards, voluntary frameworks, operating-system API specifications, and law/regulation are identified separately. Requirements change with jurisdiction, edition, product claims, and deployment context; check official sources before adopting a requirement. Some ISO/IEC/IEEE standard texts must be purchased under the publisher's terms; this repository links to official landing pages and **does not reproduce copyrighted standards**.

For each project, document a standard's scope, edition, applicability, mapped feature, implementation evidence, tests, known gaps, and review status. The presence of a reference does **not** mean compliance or testing is complete.

## Project ownership and source of truth

- **This repository** is the home for the cross-domain standards index and project-specific applicability inventories, including YazSes and Agent Movement.
- **[YazSes](https://github.com/MSKazemi/yazses)** remains the source of truth for actual software behavior, tests, ADRs, research protocols and implementation decisions, including [AGENTS.md](https://github.com/MSKazemi/yazses/blob/main/AGENTS.md).
- Proposed engineering work should link existing YazSes issues rather than duplicating their tracking here.
- No private business or confidential material should be included in this public repository.

## Contribution / review

Before updating a reference, check the publisher's catalogue and the latest edition; prefer an official landing page to a direct PDF, distinguish **official standard** from **community specification**, and use dated verification notes. Do not make legal, medical, security or accessibility certification claims without scope-specific documented evidence.

This repository is an informational research catalogue, not legal advice.
