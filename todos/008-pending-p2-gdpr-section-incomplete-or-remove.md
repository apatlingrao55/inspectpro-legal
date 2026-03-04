---
status: pending
priority: p2
issue_id: "008"
tags: [code-review, legal, privacy, gdpr]
dependencies: []
---

# GDPR Section Either Incomplete or Should Be Removed

## Problem Statement

The GDPR section has multiple gaps (no Article 27 EU representative, no NZ adequacy citation, consent basis issues). Meanwhile, the app is a free, offline NZ app targeting NZ/AU markets with no server-side data processing — GDPR applicability is questionable.

Two valid approaches exist: fix the gaps or remove the section entirely.

## Findings

**Source:** Security Sentinel agent (gaps), Simplicity Reviewer agent (remove entirely)

**Evidence (if keeping):**
- No EU/UK representative designated (Article 27 requirement)
- No NZ adequacy decision cited (European Commission Decision 2013/65/EU)
- No retention period for company-held data (Article 13(2)(a))
- Consent (Article 6(1)(a)) listed alongside Contract (6(1)(b)) — confuses legal basis

**Evidence (for removal):**
- App targets NZ/AU only, is offline, stores nothing on servers
- GDPR applies when offering goods/services to EU residents or monitoring behavior — unlikely for this app
- Section admits: "we are not required to appoint a Data Protection Officer"

## Proposed Solutions

### Option A: Remove GDPR section entirely (Simpler)
The app does not target EU users. Remove the GDPR section (~30 lines in Privacy Policy, ~30 in index.html). Add it back if the app expands to EU markets.

- **Effort:** Small
- **Risk:** Low (app is not in EU market)

### Option B: Fix GDPR gaps (More protective)
Add Article 27 exemption statement, cite NZ adequacy decision, fix consent basis, add retention periods.

- **Effort:** Medium
- **Risk:** None

## Acceptance Criteria

- [ ] GDPR section either removed or completed with all required elements
- [ ] If removed: CCPA section also removed (same rationale)
- [ ] Markdown and HTML versions match

## Work Log

| Date | Action | Learnings |
|------|--------|-----------|
| 2026-03-04 | Created from code review | GDPR section has gaps; questionable applicability for NZ/AU offline app |
