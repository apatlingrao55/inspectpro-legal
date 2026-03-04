---
status: complete
priority: p2
issue_id: "005"
tags: [code-review, legal, privacy]
dependencies: []
---

# Privacy Policy Change Mechanism Inconsistent with ToS Re-Acceptance

## Problem Statement

The Terms of Use has a strong consent mechanism: "If we make material changes to these Terms, you will be asked to review and re-accept the updated version before continuing to use the App" (line 163). But the Privacy Policy uses the weaker "Your continued use of the App after the notice period constitutes acceptance" (line 128).

For privacy-sensitive changes, the re-acceptance approach is legally stronger and more aligned with NZ Privacy Act expectations.

## Findings

**Source:** Security Sentinel agent

**Evidence:**
- `TERMS_OF_USE.md` line 163: re-acceptance mechanism (strong)
- `PRIVACY_POLICY.md` line 128: continued-use acceptance (weak)

## Proposed Solutions

### Option A: Align Privacy Policy with ToS re-acceptance (Recommended)
Add similar re-acceptance language to the Privacy Policy for material changes.

- **Effort:** Small
- **Risk:** None

## Acceptance Criteria

- [ ] Privacy Policy specifies re-acceptance for material changes
- [ ] Markdown and HTML versions match

## Work Log

| Date | Action | Learnings |
|------|--------|-----------|
| 2026-03-04 | Created from code review | Inconsistent consent mechanisms across documents |
