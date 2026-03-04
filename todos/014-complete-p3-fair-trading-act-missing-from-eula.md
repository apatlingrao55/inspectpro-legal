---
status: complete
priority: p3
issue_id: "014"
tags: [code-review, legal, consistency]
dependencies: []
---

# Fair Trading Act Reference Missing from EULA Disclaimer of Warranties

## Problem Statement

The ToS Disclaimer of Warranties includes: "Nothing in these Terms constitutes misleading or deceptive conduct for the purposes of the Fair Trading Act 1986 (NZ) or equivalent Australian state and territory fair trading legislation." The EULA's Disclaimer of Warranties does NOT include this reference.

## Findings

**Source:** Architecture Strategist agent

**Evidence:**
- `TERMS_OF_USE.md` line 111: Fair Trading Act reference present
- `EULA.md` lines 64-73: No Fair Trading Act reference

## Proposed Solutions

### Option A: Add Fair Trading Act reference to EULA (Recommended)
Add the same carve-out to the EULA Disclaimer of Warranties section.

## Acceptance Criteria

- [ ] EULA Disclaimer of Warranties includes Fair Trading Act reference
- [ ] Markdown and HTML versions match

## Work Log

| Date | Action | Learnings |
|------|--------|-----------|
| 2026-03-04 | Created from code review | FTA reference asymmetry between ToS and EULA |
