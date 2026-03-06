---
status: complete
priority: p2
issue_id: "006"
tags: [code-review, legal]
dependencies: []
---

# ToS Survival Clause Missing "Professional Responsibility"

## Problem Statement

The EULA survival clause correctly includes "Fitness for Purpose Disclaimer" (its equivalent section). However, the ToS survival clause does NOT include "Professional Responsibility" — the analogous section that disclaims the app's role in property assessment. These disclaimers are equally important to survive termination.

## Findings

**Source:** Architecture Strategist agent

**Evidence:**
- `TERMS_OF_USE.md` line 181: Lists "Disclaimer of Warranties, Limitation of Liability, Australian Consumer Law Notice, Indemnification, Governing Law, Dispute Resolution, and Severability" — missing "Professional Responsibility"
- `EULA.md` line 130: Correctly includes "Fitness for Purpose Disclaimer"
- `index.html` line 232: Same as markdown ToS

## Proposed Solutions

### Option A: Add "Professional Responsibility" to ToS survival clause (Recommended)
Update to: "Professional Responsibility, Disclaimer of Warranties, Limitation of Liability, Australian Consumer Law Notice, Indemnification, Governing Law, Dispute Resolution, and Severability."

- **Effort:** Small
- **Risk:** None

## Acceptance Criteria

- [ ] ToS survival clause includes "Professional Responsibility"
- [ ] Markdown and HTML versions match

## Work Log

| Date | Action | Learnings |
|------|--------|-----------|
| 2026-03-04 | Created from code review | Survival clauses should list all protective sections |
