---
status: complete
priority: p2
issue_id: "004"
tags: [code-review, legal, professionalism]
dependencies: []
---

# dev@ Email Inappropriate for Legal/Privacy Contact

## Problem Statement

The email `dev@aiconsult.co.nz` is used as the sole contact point for privacy complaints, legal disputes, regulatory correspondence, and GDPR data subject requests. A `dev@` prefix signals a developer/technical address, not a legal or compliance function.

## Findings

**Source:** Security Sentinel agent + own analysis

**Evidence:**
- Used 13+ times across all legal files and index.html
- Used for: Privacy Commissioner escalation path, AU APP breach complaints (30-day response), GDPR DSARs, dispute resolution notices

**Risk:** A privacy commissioner or regulator sending formal correspondence to a `dev@` address may question whether the entity takes privacy seriously.

## Proposed Solutions

### Option A: Create dedicated privacy/legal address (Recommended)
Create `privacy@aiconsult.co.nz` or `legal@aiconsult.co.nz` for legal documents. Keep `dev@` for bug reports in SUPPORT.md.

- **Effort:** Small
- **Risk:** None

### Option B: Use contact@ as general-purpose
Use `contact@aiconsult.co.nz` across all documents.

- **Effort:** Small
- **Risk:** None

## Acceptance Criteria

- [ ] Legal documents use appropriate non-dev@ email
- [ ] SUPPORT.md can keep dev@ for bug reports
- [ ] All 13+ occurrences updated consistently

## Work Log

| Date | Action | Learnings |
|------|--------|-----------|
| 2026-03-04 | Created from code review | dev@ prefix inappropriate for legal/regulatory contact |
