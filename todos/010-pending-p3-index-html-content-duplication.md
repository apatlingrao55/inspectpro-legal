---
status: pending
priority: p3
issue_id: "010"
tags: [code-review, architecture, maintenance]
dependencies: []
---

# index.html Manually Duplicates All Markdown Content

## Problem Statement

The entire legal content exists in two places: the markdown files AND hardcoded in `index.html` (~690 lines). Every future edit requires updating both locations, and drift is virtually guaranteed over time.

## Findings

**Source:** Architecture Strategist agent, Simplicity Reviewer agent, Agent-Native Reviewer agent

**Current sync status:** Content is perfectly synchronized as of this PR. But this is fragile.

## Proposed Solutions

### Option A: Static site generator (Recommended)
Use Jekyll (GitHub Pages supports natively) or a simple build script to generate `index.html` from the markdown files.

### Option B: Client-side rendering
Use a lightweight markdown-to-HTML library (e.g., marked.js) at runtime.

### Option C: Accept the duplication
Keep manual sync but add a comment at the top of `index.html` noting it must match the markdown files.

## Acceptance Criteria

- [ ] Single source of truth for legal content established (or duplication risk documented)

## Work Log

| Date | Action | Learnings |
|------|--------|-----------|
| 2026-03-04 | Created from code review | Manual content duplication is a maintenance risk |
