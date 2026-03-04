---
status: pending
priority: p3
issue_id: "012"
tags: [code-review, security, privacy]
dependencies: []
---

# Physical Address May Be Residential

## Problem Statement

The address "25 Edinburgh Avenue, Rosehill, Papakura 2113" appears 12+ times across all legal documents and index.html. If this is a residential address, publishing it on public-facing legal documents creates personal safety and privacy risks.

## Findings

**Source:** Security Sentinel agent

NZ company law requires a registered office address (Companies Act 1993), but there is no requirement to publish a residential address on consumer-facing legal documents. A registered office service or PO Box would satisfy the requirement.

## Proposed Solutions

### Option A: Use a virtual office / registered office service address
### Option B: Use a PO Box for consumer-facing documents
### Option C: Confirm it is a commercial address and accept

## Acceptance Criteria

- [ ] Address verified as appropriate for public-facing legal documents

## Work Log

| Date | Action | Learnings |
|------|--------|-----------|
| 2026-03-04 | Created from code review | Residential address exposure creates safety risks |
