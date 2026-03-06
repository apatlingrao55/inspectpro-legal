---
status: complete
priority: p2
issue_id: "009"
tags: [code-review, legal, consumer-law]
dependencies: []
---

# License Grant "Personal or Professional" Weakens CGA s43(2) Business Use Claim

## Problem Statement

The Business Use Acknowledgment invokes CGA s43(2) to exclude consumer guarantees for business users. However, the license grant in both ToS (line 18) and EULA (line 16) says "personal or professional use," explicitly contemplating non-business use. This undermines the s43(2) claim because the app itself acknowledges it may be used for non-business purposes.

## Findings

**Source:** Security Sentinel agent

**Evidence:**
- `TERMS_OF_USE.md` line 18: "personal or professional use"
- `EULA.md` line 16: "any compatible mobile device that you own or control" (no personal/professional distinction)
- `TERMS_OF_USE.md` line 32: CGA s43(2) business use acknowledgment
- `EULA.md` line 53: Same acknowledgment

## Proposed Solutions

### Option A: Remove "personal or" from ToS license grant (Recommended)
Change "personal or professional use" to "professional use" in ToS line 18. The EULA already avoids this wording.

- **Effort:** Small
- **Risk:** Low

### Option B: Add business-use checkbox at onboarding
Strengthen the s43(2) representation with an explicit in-app acknowledgment.

- **Effort:** Medium (requires app code change)
- **Risk:** None

## Acceptance Criteria

- [ ] License grant language does not contradict CGA s43(2) business use claim
- [ ] Markdown and HTML versions match

## Work Log

| Date | Action | Learnings |
|------|--------|-----------|
| 2026-03-04 | Created from code review | "Personal or" language explicitly undermines business-use exclusion |
