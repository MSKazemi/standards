# Standard adoption / conformance assessment record

> Copy this template into **the owning project's repository** for an actual decision. This public standards repository holds the reference register, not unpublished customer data, detailed exploits, confidential architecture or raw compliance artefacts.

## Identity and ownership

| Field | Value |
|---|---|
| Record ID | `STD-ADOPT-<project>-<id>` |
| Project / repository | |
| Standard / profile / clause identifiers | |
| Official publisher URL | |
| Edition / publication stage / last verified | |
| Discovery register entry ID | |
| Applicable product version / commit | |
| Maintainer role / reviewer | |
| Status / last reviewed at | |
| Related architecture decisions / issues / PRs | |

## 1. Applicability decision

**Decision:** `unassessed | applicable | conditional | informative | not-applicable | defer`

- Use case, user/customer and value:
- Product component, data types and deployment modes:
- Geography and legal applicability (qualified counsel if needed):
- Threat or failure mode this reference helps address:
- Scope boundaries and explicit non-goals:
- Reason for decision and alternatives considered:

## 2. Claim and technical profile

**Proposed precise, testable claim** (avoid broad “compliant with” language):

> [Object/output] implements [edition + selected mechanism/profile] in [specific product version], subject to [explicit constraints].

- Exact identifiers, optional sections and message/profile details:
- Chosen algorithms and their compatibility implications:
- Input, output, schema and trust boundaries:
- Existing shipped path / evidence (rechecked against source code):
- Required changes, dependencies, defaults and offline impact:
- Licensed-text handling (do not paste copyrighted normative sections):

## 3. Requirement-to-evidence crosswalk

| Requirement ID | Reference clause/profile | Code path or component | Positive test | Negative test | External oracle | Evidence path | Result |
|---|---|---|---|---|---|---|---|
| R-001 | | | | | | | `not-run` |

**Use an independent verifier** for portable formats when available; test intentional corruption, wrong keys, missing material, bad trust chains and version skew, not just happy paths. Regulatory mapping must use wording “evidence relevant to,” never imply an audit verdict.

## 4. Reproducibility record

- Repo commit/tag and product version:
- Test dependencies and verifier versions:
- Exact command(s) and working directory:
- Expected outputs and success/failure criteria:
- Actual output, exit code, logs and links (attach after execution):
- Input fixtures and cryptographic digests:
- Real environment vs mock / simulation / fixture:
- Offline/no-network test status:
- Compatibility and rollback result:
- Performance/resource effect:
- Security/privacy/redaction check:
- False-positive / false-negative limitations:
- Independent reviewer sign-off, if performed:

## 5. Engineering and release decisions

**Implementation state:** `unverified | planned | experimental | works-today | deprecated`  
**Verification state:** `not-tested | test-failed | internal-only | independently-reproduced | externally-assessed`

Do not mark `works-today` or `independently-reproduced` without an exact, reproducible evidence link. Do not equate these with certification.

- ADR/RFC required? Why?
- Issue/PR already exists? (deduplicate)
- Merge/release gate and acceptance criteria:
- Proposed effort range / resource needs:
- Owner-approved priority and target window (blank until approved):
- Dependencies and blocked risks:
- Review on issuer update / product release / discovered vulnerability:
- External certification/legal review (only if separately required):

## 6. Final review decision

**Decision:** `accept-for-implementation | implemented-and-verified | defer | reject | revise`

- What the evidence proves:
- What the evidence **does not** prove:
- Reviewer, date and source of approval:
- Next version check / trigger:
