# Agent Movement standards inventory — verification and maintenance backlog

**Compiled:** 2026-11-21 (Europe/Rome). **Status:** proposed editorial QA and research follow-up; **not a claim of standards compliance or independent source validation**.

## Current scope

- **Canonical machine-readable inventory:** [284-entry CSV](../data/agent-movement-standards.csv).
- **Browsable public register:** [Agent Movement](agent-movement.md).
- **Inherited historical snapshot:** 42 earlier research rows with their recorded access dates and release/version metadata. Do not call their versions current without rechecking.
- **Expansion:** 242 candidate entries in 16 groups, each deliberately marked `not individually version-verified`. A source URL on a row may be a general catalogue rather than exact part/edition.
- **Public disclosure boundary:** copy only standards metadata and newly authored neutral descriptions; retain internal implementation research, private issues, detailed technical plans, credentials, partner information and unpublished results in their authorized repositories.

## Highest-priority editorial work

### P1: structure and source correctness

- [ ] Validate that CSV has exactly 12 columns, 284 data rows and 284 unique stable IDs.
- [ ] Check for overlapping entries that refer to the same standard with different IDs (e.g. a reference in both the 42-row earlier tracker and 242-row discovery list).
- [ ] Verify all link targets are live, official, and relevant to the stated reference. Do **not** mark a catalogue search page as a verified particular edition.
- [ ] For each proposed ISO/IEC, IEEE, OMG, IEC and IETF reference, confirm the **actual identifier, official title, publication or draft state, revision/part and corrigenda** with the publishing body. Remove or correct invalid names/dates.
- [ ] Explicitly distinguish draft Internet-Drafts / draft ISO projects from published standards, and preserve revisions that became obsolete, archived or withdrawn.
- [ ] Record the date and primary source used for **each individual verification**; do not bulk-stamp `accessed`.

### P2: usability and cross-project reuse

- [ ] Develop a normalized cross-project taxonomy, with stable standard IDs and many-to-many project applicability mappings, without discarding the source register's history.
- [ ] Group standards into foundational, applicable-to-current-scope, contingent-on-future-capability, emerging/watch and out-of-scope categories; avoid asserting universal mandatory compliance.
- [ ] Add an evidence matrix: reference → scoped clauses → feature/interface → owning implementation → test → observed result → risk and outstanding gap.
- [ ] Use official references in all normative documentation and preserve historical version snapshots rather than silently overwriting past facts.
- [ ] Evaluate lightweight CI for CSV schema, duplicate ID, link syntax and Markdown relative-link integrity. **No CI or validation pipeline is established by this research inventory.**

### P3: research comparisons and standards strategy

- [ ] Compare standards and protocols that enable **delegation**, **serialization**, **durability**, **authorization**, **provenance**, **revocation**, **robotic communication** and **physical safety** with tasks they do not solve.
- [ ] Preregister falsifiers for exclusive ownership transfer, stale-executor fencing, uncertain external effects and incomplete independent evidence; existing standard publication does not prove those properties.
- [ ] Review whether each category represents a standards-alignment need, an interoperability experiment, a risk/governance question, or merely background context.
- [ ] Engage relevant specification bodies only after confirming the actual technical gap and a reproducible result; do not assert a novel standardization need merely because an acronym is absent.

## Verification record

| Check | As of 2026-11-21 | Notes |
| --- | --- | --- |
| Source CSV formatting | Parsed during transfer, 284 rows and 12 fields per row | Validated in transfer logic; independently rerun after merge |
| Stable row identifiers | No duplicate IDs found in transfer | Semantic duplicates may remain |
| Public exposure scan | No private repository URL or obvious credential marker found in transferred CSV | Not a full provenance/rights/security audit |
| Documentation creation | Public register generated from the CSV | All 284 records represented |
| External official URLs | **Not individually verified** for all 284 | Requires primary-source audit |
| Released versions and maturity | **Not independently refreshed** | Per-entry checks required |
| Legal and conformity interpretations | **Not assessed** | Context- and jurisdiction-dependent |
| CI, test suite and license clearance | **Not established** | Do not infer certification or redistribution rights |

This backlog is intentionally **standards-specific**. The source scientific project, its code, controlled effects and evaluation results remain separate and are not copied or published through this register.
