---
status: complete
priority: p1
issue_id: "002"
tags: [code-review, security, privacy, legal]
dependencies: []
---

# Data Collection Claims Contradict Local-Only Architecture

## Problem Statement

The Privacy Policy repeatedly and emphatically claims all data is local-only ("We do NOT upload your data to any external servers", "We do NOT have access to your inspection data"). However, the "Automatically Collected Information" section states:

- "Device Information: We **may collect** device type and operating system version for app compatibility purposes"
- "App Usage: Basic usage data for app compatibility purposes"

The phrase "We may collect" is ambiguous and directly contradicts the local-only claims. If the app truly collects device info, that data must go somewhere. If it stays on-device, then "we collect" is misleading.

## Findings

**Source:** Security Sentinel agent

**Evidence:**
- `PRIVACY_POLICY.md` lines 21-23: "We may collect" language
- `PRIVACY_POLICY.md` lines 27-33: emphatic local-only claims
- Same content in `index.html` lines 285-298

**Impact:** This contradiction could be challenged under:
- NZ Fair Trading Act 1986 s9 (misleading conduct)
- Australian Consumer Law s18 (misleading or deceptive conduct)
- NZ IPP 3 (collection must be necessary) and IPP 1 (purpose)

## Proposed Solutions

### Option A: Clarify as local-only reads (Recommended if app is truly offline)
Replace "We may collect device type and operating system version" with: "The App reads your device type and operating system version locally to ensure compatibility. This information is not transmitted to us or any third party."

Replace "Basic usage data for app compatibility purposes" with specific wording about what the app reads locally vs what it sends externally (if anything).

- **Pros:** Resolves contradiction, maintains strong local-only positioning
- **Cons:** Must verify the app truly sends nothing
- **Effort:** Small
- **Risk:** Low

### Option B: Disclose actual data transmission
If the app does use any analytics, crash reporting, or telemetry (even Apple's default crash reporting), disclose it explicitly.

- **Pros:** Legally accurate
- **Cons:** Weakens local-only messaging
- **Effort:** Medium (requires technical audit of app)
- **Risk:** Low

## Recommended Action

_To be filled during triage._

## Technical Details

**Affected files:**
- `PRIVACY_POLICY.md` (lines 21-23)
- `index.html` (lines 285-288)

## Acceptance Criteria

- [ ] No contradiction between "local-only" claims and data collection statements
- [ ] "We may collect" language replaced with precise wording
- [ ] "Basic usage data" defined specifically
- [ ] Markdown and HTML versions match

## Work Log

| Date | Action | Learnings |
|------|--------|-----------|
| 2026-03-04 | Created from code review | Ambiguous data collection language creates Fair Trading Act risk |
