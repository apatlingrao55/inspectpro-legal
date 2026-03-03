# Brainstorm: App Developer Indemnity & Legal Audit (NZ/AU Focus)

**Date:** 2026-03-03
**Status:** Draft
**Scope:** NZ and AU markets only

## What We're Building

Targeted amendments to the existing InspectPro legal docs (ToS, EULA, Privacy Policy) to strengthen enforceability, fix errors, and align with NZ/AU legal best practices for app developers.

## Why This Approach

The existing docs are comprehensive (upgraded March 2026) but an audit against app developer indemnity best practices revealed specific gaps. Targeted amendments preserve the existing structure while fixing issues.

## Key Decisions

### 1. Fix Disputes Tribunal Threshold
- **Current:** NZ$60,000 (incorrect)
- **Correct:** NZ$30,000 (Disputes Tribunal Act 1988, updated 2022)
- **Files:** ToS line 159, EULA line 125
- **Action:** Change NZ$60,000 → NZ$30,000 in both documents and index.html

### 2. Update Acceptance Language (Browsewrap → Clickwrap)
- **Current:** "By downloading, installing, or using the App, you agree..."
- **Change to:** Language referencing explicit in-app acceptance (tap "I Agree" or check acceptance box)
- **Files:** ToS lines 7, 179; EULA lines 9, 145; index.html
- **Rationale:** Browsewrap is legally weak in NZ/AU. Clickwrap (explicit user action) creates stronger evidence of agreement, especially important given NZ Fair Trading Act unfair terms scrutiny and Disputes Tribunal claims.

### 3. Add Clickwrap Implementation Guidance
- **Add a note in the ToS** (near "Agreement to Terms" or "Changes to Terms") specifying:
  - Acceptance must be via explicit tap or unchecked checkbox
  - Full terms link must be visible at acceptance point
  - Backend must log: timestamp, user/device ID, terms version accepted
  - Sign-up/continue button disabled until acceptance
  - Re-consent required for material changes
  - Every terms version archived with date
- **Purpose:** Serves as a spec for the iOS app implementation

### 4. Add Terms Versioning
- **Add version numbers** to all three documents (e.g., "Version 1.0 — March 2026")
- **Add version history section** at the bottom of each document
- **Supports:** The 30-day advance notice commitment, legal auditability, and clickwrap re-consent tracking
- **Files:** ToS, EULA, Privacy Policy, index.html

### 5. Strengthen Indemnity Clause
- **Current coverage:** Breach, violations, content, third-party reliance + developer fault carve-out
- **Strengthen with explicit sub-categories:**
  - User misuse of the App
  - Infringing content created by the user
  - Violations of Terms or applicable law
  - Third-party claims arising from user's inspection reports
- **Explicit exclusions (what indemnity does NOT cover):**
  - Developer's own negligence or wilful misconduct (already present)
  - Non-excludable consumer guarantees under CGA 1993 or ACL
  - Regulatory action by Commerce Commission, ACCC, or Privacy Commissioner
- **Files:** ToS lines 109-120, EULA lines 89-100, index.html

### 6. Add Future-Proofing Note for Content Moderation/Takedown
- **Add brief section** to ToS (near "User Content" or "Acceptable Use"):
  - If cloud features, content sharing, or user accounts are introduced, a content moderation policy, copyright takedown process, and right-to-remove clause will be added
  - No current need (offline-only, local storage)
- **Files:** ToS, index.html

## What We're NOT Changing

- **Copyright takedown / DMCA process:** Not needed for offline-only architecture
- **Right to remove content:** Cannot remove local-only content; not applicable
- **Standalone AUP:** Acceptable use embedded in ToS is sufficient (no user accounts, no UGC sharing)
- **CCPA / GDPR sections:** Out of scope for this NZ/AU-focused audit (existing coverage retained as-is)
- **Overall document structure:** Keeping current section ordering

## Files Affected

| File | Changes |
|------|---------|
| `TERMS_OF_USE.md` | Acceptance language, clickwrap guidance, indemnity strengthening, DT threshold, terms versioning, future-proofing note |
| `EULA.md` | Acceptance language, indemnity strengthening, DT threshold, terms versioning |
| `PRIVACY_POLICY.md` | Terms versioning only |
| `index.html` | Mirror all changes above |

## Open Questions

None — all decisions resolved during brainstorm dialogue.
