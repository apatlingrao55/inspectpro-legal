---
status: complete
priority: p1
issue_id: "001"
tags: [code-review, legal, factual-error]
dependencies: []
---

# Disputes Tribunal Threshold Should Be NZ$60,000

## Problem Statement

All legal documents state "For disputes involving claims under NZ$30,000" for the Disputes Tribunal. However, the Disputes Tribunal Amendment Act 2025 raised the jurisdictional limit from $30,000 to $60,000, effective 24 January 2026. Since these documents are dated March 2026, they contain an incorrect figure on the day of publication.

The PR description correctly mentions "$60,000 threshold" but the implementation used $30,000 (likely from the indemnity audit brainstorm which incorrectly "corrected" it).

## Findings

**Source:** Architecture Strategist agent, cross-referenced with NZ legislation

**Evidence:**
- `TERMS_OF_USE.md` line 195: `"For disputes involving claims under NZ$30,000"`
- `EULA.md` line 144: `"For disputes involving claims under NZ$30,000"`
- `index.html` line 244: `"For disputes involving claims under NZ$30,000"` (ToS section)
- `index.html` line 602: `"For disputes involving claims under NZ$30,000"` (EULA section)

**References:**
- Disputes Tribunal Amendment Act 2025 (NZ)
- [McVeagh Fleming: New $60,000 Disputes Tribunal limit](https://www.mcveaghfleming.co.nz/articles/what-the-new-60-000-disputes-tribunal-limit-means-for-you)

## Proposed Solutions

### Option A: Update to $60,000 (Recommended)
Change all four occurrences from `NZ$30,000` to `NZ$60,000`.

- **Pros:** Factually correct, simple fix
- **Cons:** None
- **Effort:** Small
- **Risk:** None

## Recommended Action

_To be filled during triage._

## Technical Details

**Affected files:**
- `TERMS_OF_USE.md` (line 195)
- `EULA.md` (line 144)
- `index.html` (lines 244, 602)

## Acceptance Criteria

- [ ] All 4 occurrences of NZ$30,000 changed to NZ$60,000
- [ ] Markdown and HTML versions match

## Work Log

| Date | Action | Learnings |
|------|--------|-----------|
| 2026-03-04 | Created from code review | Disputes Tribunal threshold was raised effective 24 Jan 2026 |
