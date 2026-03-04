# Brainstorm: NZ/AU Legal Deep Dive for InspectPro

**Date:** 2026-03-03
**Status:** Complete
**Next step:** `/workflows:plan` to implement all changes

---

## What We're Building

A second-pass upgrade to InspectPro's legal documents addressing NZ/AU-specific gaps identified through repo analysis and best-practice research. The March 2026 upgrade established the foundation (CGA/ACL carve-outs, NZ governing law, Privacy Act 2020 IPPs, tiered liability). This pass fills the remaining gaps to achieve comprehensive NZ/AU market coverage.

## Why This Matters

- **CGA s43(2) business use acknowledgment** is the single biggest protection left on the table — it allows excluding CGA guarantees for professional/business users
- **Fair Trading Act 2022 unfair terms regime** could void the indemnification and termination clauses as currently written
- **NZS 4306:2005 / AS 4349.1** are the primary property inspection standards in NZ/AU — not disclaiming them risks implied compliance
- **AU privacy section** is significantly thinner than NZ, creating a gap for AU users
- No company identification (NZBN, address) despite consumer law expectations

## Key Decisions

### 1. Business Use Acknowledgment (CGA s43(2))
**Decision:** Soft representation clause — user represents they are acquiring the app primarily for business/professional purposes. No hard gate or UX change needed. Goes in ToS and EULA.

### 2. FTA Unfair Terms Fixes
**Decision:** Narrow both clauses:
- **Indemnification:** Limited to losses caused by user's breach of terms, negligence, or willful misconduct (not general use)
- **Termination:** Remove "any other reason at our sole discretion" — limit to cause (breach, harmful conduct, legal requirement)
- Apply to ToS, EULA, and index.html

### 3. Company Identification
**Decision:** Include in all documents:
- **Entity:** AI Consult Ltd
- **NZBN:** 9429052142376
- **Address:** 25 Edinburgh Avenue, Rosehill, Papakura 2113, New Zealand
- **Email:** dev@aiconsult.co.nz (unchanged)

### 4. Age Threshold
**Decision:** Align to 16 everywhere. Update Privacy Policy children's section from 13 to 16 to match ToS. Professional tool, NZ/AU primary market — COPPA (US, 13+) less relevant.

### 5. User Privacy Obligations
**Decision:** Add in Privacy Policy (Information You Provide section) and ToS (Professional Responsibility). Remind users they are the "agency" holding client personal information under Privacy Act 2020 and have their own obligations.

### 6. Inspection Standards Disclaimers
**Decision:** Add explicit NZS 4306:2005 and AS 4349.1 references in Professional Responsibility (ToS) and Fitness for Purpose Disclaimer (EULA). Disclaim that reports do not purport to comply with these standards unless the user independently ensures compliance.

### 7. AU Privacy Parity
**Decision:** Expand Australian Privacy section to enumerate relevant individual APPs (matching NZ IPP granularity). Add AU Notifiable Data Breaches (NDB) scheme under Part IIIC of Privacy Act 1988.

### 8. EULA Dispute Resolution
**Decision:** Add dispute resolution section to EULA mirroring the ToS 3-tier process.

### 9. Fair Trading Act Reference
**Decision:** Add FTA 1986 awareness in ToS (Acceptable Use or Professional Responsibility context).

### 10. Disputes Tribunal
**Decision:** Add note in dispute resolution about Disputes Tribunal as accessible option (threshold now $60,000 as of Jan 2026).

---

## All Changes by File

### TERMS_OF_USE.md
- [ ] Add business use acknowledgment clause (after Cost or in Agreement section)
- [ ] Add NZS 4306:2005 reference to Professional Responsibility
- [ ] Add user privacy obligations bullet to Professional Responsibility
- [ ] Narrow indemnification to breach/negligence/willful misconduct
- [ ] Remove "sole discretion" from termination — limit to cause
- [ ] Add Disputes Tribunal reference in Dispute Resolution
- [ ] Add Fair Trading Act 1986 reference
- [ ] Add NZBN + address to Contact Us
- [ ] Add AI Consult Ltd entity identification

### EULA.md
- [ ] Add business use acknowledgment clause
- [ ] Add NZS 4306:2005 + AS 4349.1 to Fitness for Purpose Disclaimer
- [ ] Narrow indemnification to breach/negligence/willful misconduct
- [ ] Narrow termination to cause only
- [ ] Add dispute resolution section (mirror ToS 3-tier)
- [ ] Add NZBN + address to Contact Us
- [ ] Add AI Consult Ltd entity identification

### PRIVACY_POLICY.md
- [ ] Align Children's Privacy to 16 (from 13)
- [ ] Add user privacy obligations note to Information You Provide
- [ ] Expand Australian Privacy section with individual APP mapping
- [ ] Add AU Notifiable Data Breaches (NDB) scheme section
- [ ] Add missing IPP 5 (security safeguards), IPP 12 (cross-border disclosure), IPP 13 (unique identifiers)
- [ ] Add explicit statement that users are the data holders for client information
- [ ] Add 30-day internal complaint response timeframe
- [ ] Add NZBN + address to Contact Us

### SUPPORT.md
- [ ] Add NZBN + address to Contact section

### index.html
- [ ] Mirror ALL above changes into corresponding HTML sections

## Resolved Questions

- **Business use acknowledgment approach:** Soft representation (no UX change)
- **FTA fix scope:** Narrow both indemnification and termination
- **Company identification:** NZBN 9429052142376, 25 Edinburgh Avenue, Rosehill, Papakura 2113, NZ
- **Age alignment:** 16 everywhere
- **User privacy obligations placement:** Privacy Policy + Professional Responsibility
- **Scope of this round:** Everything (high + medium + low priority)

## Open Questions

None — all decisions resolved.
