# Standards register — schema, verification and conformance discipline

**Date:** 2026-11-21. This public repository is a **discovery and traceability catalogue**, not an independent certification authority.

## Normalized record expectations

For a new inventory, preserve:
- `id`: stable unique local identifier;
- `reference`: issuing body's identifier and official title;
- `family`: subject grouping;
- `kind`: `international_standard`, `ietf_rfc`, `w3c_recommendation`, `industry_protocol`, `draft_or_emerging`, `framework_guidance`, `security_benchmark`, `legislation` etc.;
- `reported_edition`: **snapshot**, not automatically current;
- `research_tier`: Core / Targeted / Conditional / Watch / Scope-check (not a claim of obligation);
- `component`: surface potentially affected;
- `kubeintellect_rationale`: author-written applicability description;
- `source_url`: official exact document when verified, otherwise clearly marked catalogue/search page;
- `source_link_type`: how directly the link supports the row;
- `verification_status`: whether identifier, edition and content were checked;
- `verified_at`: individually reviewed ISO-8601 date only.

Existing project catalogues differ in schema. Do not re-write historical rows or manufacture uniform versions. A later migration may create a normalized index with per-project applicability as a relation and maintain original project datasets as immutable inputs.

## Publisher and copyright rules

For normative requirements, consult the **specific** document and edition at an issuing body's site (ISO, IEC, IEEE, IETF RFC Editor, W3C, ETSI, NIST, CNCF, OASIS, OMG, Ecma, EU EUR-Lex, etc.). Publisher searches and catalogue pages are *leads*, not validation of specific titles or current editions. A secondary blog is only supporting context. Proprietary standard text and paid benchmark control wording must not be reproduced; record identifiers, own short summaries, and publisher links instead.

Distinguish final standards from Internet-Drafts and proposed ISO projects, historical practices from current obligations, and laws from technical requirements. ISO standards may be voluntary; statutory obligations vary by product, role, jurisdiction and applicability date.

## Practical verification checklist

1. Resolve official identifier, title, part, publication status and latest adopted edition; check withdrawn/superseded versions.
2. Find the most specific official URL, confirm it supports the named part and note the date actually inspected.
3. Compare scoped feature against the standard's stated coverage; remove irrelevant or duplicate candidate entries.
4. Classify the requirement's nature: law, contractual promise, normative protocol behavior, voluntary control or experiment guidance.
5. For implementation claims, link to specific code, configuration and test evidence in the owning project; include its branch/commit and observed result.
6. Record the negative/failure cases; avoid inferring correctness from passing happy-path demos.
7. Review licensing, publication restrictions and confidentiality before copying any evidence to a public repo.
8. Review periodically or when a relevant standard changes; never automatically overwrite a historical version snapshot with today's edition.

## Conformance evidence ladder

| Level | Evidence | Valid statement |
| --- | --- | --- |
| 0. Listed | Candidate source in inventory | Relevant for investigation |
| 1. Verified reference | Primary source, exact edition and applicability reviewed | Reference verified for scope |
| 2. Requirements mapped | Scoped clauses, control owners and verification procedure | Control design mapped |
| 3. Implementation linked | Versioned code/config and tests | Implementation evidence documented |
| 4. Tested | Test logs, negative cases and reviewer | Verified against declared test scope |
| 5. Independently assessed | Accredited or appropriately qualified independent assessment if applicable | Only claim assessment within exact documented scope |

This is an internal evidence taxonomy for the registry, **not** a standards body's formal certification scale.

## Potential CI for the standards repository

Automate CSV parsing, required fields, uniqueness, valid URL syntax, allowed type and tier values, and relative Markdown links. A later job can watch release feeds for publisher changes, but it must flag candidates for **human review** rather than silently updating editions or asserting normative verification. Source correctness, legal applicability, and official conformance require separate assessment.

## Disclosure and security

The standards repo is **public**. Do not import private repository URLs, unpublished experimental designs, vulnerable code locations, private issues, credentials, unpublished measurements or proprietary standards bodies' texts. A generic standards-to-control scenario may be public while the specific weakness it was motivated by remains confidential.

## Relevant draft catalogues

- [Agent Movement draft PR #2](https://github.com/MSKazemi/standards/pull/2)
- [NovaFabric draft PR #1](https://github.com/MSKazemi/standards/pull/1)
- [KubeIntellect catalogue](../projects/kubeintellect.md)
- [KubeIntellect traceability](../projects/kubeintellect-traceability.md)
