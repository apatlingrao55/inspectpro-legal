---
status: complete
priority: p3
issue_id: "015"
tags: [code-review, legal, privacy, australian]
dependencies: []
---

# APP 1 Bullet Point Should Be More Substantive

## Problem Statement

The Australian Privacy Principles APP 1 statement says: "This Privacy Policy describes how we manage personal information. We do not hold personal information on our servers." This is a vague summary that doesn't adequately address the specific sub-requirements of APP 1.4.

## Findings

**Source:** Security Sentinel agent

OAIC guidance says APP 1 compliance requires the policy to address: kinds of info collected, purposes, how collected, complaint process, overseas recipients.

## Proposed Solutions

### Option A: Expand APP 1 bullet
Replace with: "This Privacy Policy describes how we manage personal information, including the kinds of information we collect, how we collect and use it, how you may access or correct it, how you may complain, and how we deal with complaints."

## Acceptance Criteria

- [ ] APP 1 bullet addresses specific sub-requirements
- [ ] Markdown and HTML versions match

## Work Log

| Date | Action | Learnings |
|------|--------|-----------|
| 2026-03-04 | Created from code review | APP 1 requires specific sub-requirement coverage |
