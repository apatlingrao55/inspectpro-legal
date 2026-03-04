---
status: complete
priority: p2
issue_id: "007"
tags: [code-review, security, privacy]
dependencies: []
---

# iCloud/Device Backup May Contradict Local-Only Claims

## Problem Statement

The Privacy Policy claims "We do NOT upload your data to any external servers" and "the App does not create external copies of your data" (IPP 5). However, unless the app sets the `NSURLIsExcludedFromBackupKey` flag on its data files, iOS will include them in iCloud backups by default. This means user data could be uploaded to Apple's servers, contradicting the local-only claims.

## Findings

**Source:** Security Sentinel agent

**Evidence:**
- `PRIVACY_POLICY.md` line 72: IPP 5 says "the App does not create external copies of your data"
- iOS default behavior: app data is included in iCloud backups unless explicitly excluded
- If iCloud backup is enabled, user inspection data, photos, and client info could be synced to Apple's servers

## Proposed Solutions

### Option A: Add device backup disclosure (Recommended)
Add: "Your device's backup settings (e.g., iCloud, Google backups) may include app data. This is controlled by your device settings, not by InspectPro."

- **Effort:** Small
- **Risk:** None

### Option B: Exclude data from backups in code AND disclose
Set `NSURLIsExcludedFromBackupKey` on data files and state this as a security measure.

- **Effort:** Medium (requires app code change)
- **Risk:** Low

## Acceptance Criteria

- [ ] Privacy Policy addresses device backup behavior
- [ ] No contradiction with local-only claims
- [ ] Markdown and HTML versions match

## Work Log

| Date | Action | Learnings |
|------|--------|-----------|
| 2026-03-04 | Created from code review | iOS iCloud backups can inadvertently upload "local-only" data |
