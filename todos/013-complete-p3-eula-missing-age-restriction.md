---
status: complete
priority: p3
issue_id: "013"
tags: [code-review, legal, consistency]
dependencies: []
---

# EULA Missing Age Restriction Section

## Problem Statement

The ToS has an "Age Restriction" section (line 43-45) requiring users to be at least 16. The Privacy Policy mentions children under 16 (line 124). But the EULA — the first document users accept — has no age eligibility requirement.

## Findings

**Source:** Own analysis

**Evidence:**
- `TERMS_OF_USE.md` lines 43-45: Age Restriction section
- `PRIVACY_POLICY.md` line 124: Children's Privacy (under 16)
- `EULA.md`: No age restriction mentioned

## Proposed Solutions

### Option A: Add Age Restriction section to EULA
Add equivalent age restriction language to EULA.

### Option B: Cross-reference ToS
Add: "Eligibility requirements, including age restrictions, are set out in the Terms of Use."

## Acceptance Criteria

- [ ] EULA addresses user age eligibility (directly or by reference)

## Work Log

| Date | Action | Learnings |
|------|--------|-----------|
| 2026-03-04 | Created from code review | EULA is missing age restriction present in ToS and Privacy Policy |
