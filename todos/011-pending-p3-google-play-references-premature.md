---
status: pending
priority: p3
issue_id: "011"
tags: [code-review, legal, consistency]
dependencies: []
---

# EULA References Google Play but App Is iOS-Only

## Problem Statement

The EULA includes Google Play compliance language (License Grant, Apple and Google Play Compliance section) but the Support page explicitly states "InspectPro is currently available on iOS only." This is contradictory and could confuse users.

## Findings

**Source:** Architecture Strategist agent, Simplicity Reviewer agent, own analysis

**Evidence:**
- `EULA.md` lines 16, 18-26: Google Play references
- `SUPPORT.md` line 26: "currently available on iOS only"
- `index.html` lines 485, 487-495, 649-650: Same contradiction

## Proposed Solutions

### Option A: Remove Google Play references (Simpler)
Remove Google Play language until Android launch. Add it back when needed.

### Option B: Add caveat to EULA
Add a note: "Google Play distribution provisions apply when the App becomes available on Android."

## Acceptance Criteria

- [ ] No contradiction between EULA platform coverage and Support page

## Work Log

| Date | Action | Learnings |
|------|--------|-----------|
| 2026-03-04 | Created from code review | YAGNI: preparing for platform that doesn't exist yet |
