---
title: "feat: NZ/AU Legal Deep Dive — Second-Pass Upgrade"
type: feat
status: completed
date: 2026-03-03
brainstorm: docs/brainstorms/2026-03-03-nz-au-legal-deep-dive-brainstorm.md
---

# feat: NZ/AU Legal Deep Dive — Second-Pass Upgrade

## Overview

Second-pass upgrade to InspectPro's legal documents addressing NZ/AU-specific gaps identified through repo analysis and best-practice research. The March 2026 first pass established the foundation (CGA/ACL carve-outs, NZ governing law, Privacy Act 2020 IPPs, tiered liability). This pass fills the remaining gaps: CGA s43(2) business use acknowledgment, FTA unfair terms fixes, inspection standard disclaimers, AU privacy parity, company identification, and consistency fixes.

## Problem Statement / Motivation

1. **CGA s43(2) gap** — InspectPro is a professional tool, but the docs don't leverage the CGA business-use exclusion. This is the single biggest protection left on the table.
2. **FTA unfair terms risk** — The indemnification clause covers "your use of the App" (too broad) and termination allows "sole discretion" (could be voided under the Fair Trading Act 2022 unfair terms regime).
3. **No inspection standards disclaimers** — NZS 4306:2005 and AS 4349.1 are the primary property inspection standards. Without disclaiming them, users or third parties could assume reports comply.
4. **AU privacy imbalance** — NZ Privacy Act gets 11 individually-mapped IPPs; AU gets 3 bullet points. No AU Notifiable Data Breaches scheme mentioned.
5. **No company identification** — No NZBN, no physical address, despite NZ/AU consumer law expectations.
6. **Age inconsistency** — ToS says 16+, Privacy Policy says 13+.
7. **EULA missing dispute resolution** — Inconsistency with ToS.

## Proposed Solution

Apply targeted edits to all 5 files (TERMS_OF_USE.md, EULA.md, PRIVACY_POLICY.md, SUPPORT.md, index.html). Each change is an edit to existing text or an insertion at a specific location. No new files created (aside from this plan).

## Technical Considerations

- **File ordering matters**: Edit .md files first (ToS → EULA → Privacy → Support), then mirror ALL changes into index.html last
- **index.html mirroring rules**: Use existing patterns — `<h2>` for sections, `<ul>/<ol>` for lists, `<p><strong>Label:</strong> text</p>` for bold labels, `class="legal-caps"` for ALL-CAPS disclaimers, `mailto:` links for emails, `#anchor` links for internal cross-references (not .md file paths)
- **Survival clauses**: Must be updated in both ToS and EULA whenever new surviving sections are added
- **No breaking changes**: All edits are additive or narrowing (more protective, not less)

## Acceptance Criteria

- [x]Business use acknowledgment clause present in ToS and EULA (CGA s43(2))
- [x]Indemnification narrowed to breach/negligence/willful misconduct in both ToS and EULA
- [x]Termination "sole discretion" removed from ToS; replaced with cause-based grounds
- [x]NZS 4306:2005 referenced in ToS Professional Responsibility
- [x]AS 4349.1 referenced in EULA Fitness for Purpose Disclaimer
- [x]User privacy obligations added to ToS Professional Responsibility and Privacy Policy
- [x]Australian Privacy section expanded with individual APP mapping (parity with NZ IPPs)
- [x]AU Notifiable Data Breaches scheme added to Privacy Policy
- [x]Missing NZ IPPs (5, 12, 13) added to Privacy Policy
- [x]Explicit statement that users are data holders for client information
- [x]Children's Privacy aligned to 16 in Privacy Policy
- [x]EULA has dispute resolution section mirroring ToS 3-tier process
- [x]EULA Survival clause updated to include Dispute Resolution
- [x]NZBN (9429052142376) and address (25 Edinburgh Avenue, Rosehill, Papakura 2113, NZ) in all Contact Us sections
- [x]AI Consult Ltd entity identification in Agreement/intro sections
- [x]Fair Trading Act 1986 referenced in ToS
- [x]Disputes Tribunal $60,000 threshold noted in ToS dispute resolution
- [x]30-day internal complaint response timeframe in Privacy Policy
- [x]index.html mirrors ALL above changes
- [x]No "sole discretion" language remains anywhere
- [x]No "children under 13" language remains anywhere
- [x]NZBN appears in all 5 files (4 .md + 1 .html with 4 sections)

---

## Implementation Plan

### Phase 1: TERMS_OF_USE.md

**File:** `TERMS_OF_USE.md` (164 lines)

#### 1.1 Add entity identification to Agreement section (line 7)
**Current:** `...InspectPro ("the App")...`
**After intro paragraph, add:** "InspectPro is developed and operated by AI Consult Ltd (NZBN: 9429052142376), New Zealand."

#### 1.2 Add business use acknowledgment (after Cost section, ~line 26)
**Insert new section:**
```markdown
## Business Use Acknowledgment

By using the App, you represent and warrant that you are acquiring the App primarily for business or professional purposes and not for personal, domestic, or household use. To the extent permitted by section 43(2) of the Consumer Guarantees Act 1993 (NZ), the consumer guarantees under that Act do not apply to the supply of the App where it is acquired for business purposes.
```

#### 1.3 Add NZS 4306:2005 reference to Professional Responsibility (~line 59)
**Current line 59:** `- The App does not certify the condition, safety, or compliance of any property under the Building Act 2004 or any other legislation`
**Replace with:** `- The App does not certify the condition, safety, or compliance of any property under the Building Act 2004, NZS 4306:2005 (Residential Property Inspection), or any other legislation or standard`

#### 1.4 Add user privacy obligations bullet to Professional Responsibility (~line 62)
**After last bullet, add new bullet:**
```markdown
- If you enter personal information about third parties (such as clients) into the App, you are responsible for ensuring your collection and use of that information complies with the Privacy Act 2020 (NZ), the Privacy Act 1988 (Cth), and any other applicable privacy legislation
```

#### 1.5 Add Fair Trading Act reference (after Acceptable Use, ~line 46)
**After Acceptable Use section, add new bullet or note.** Alternatively, add to the CGA/ACL carve-out paragraph in Disclaimer of Warranties (~line 78):
**After the existing CGA/ACL bold paragraph, add:**
```markdown
Nothing in these Terms constitutes misleading or deceptive conduct for the purposes of the Fair Trading Act 1986 (NZ) or equivalent Australian state and territory fair trading legislation.
```

#### 1.6 Narrow indemnification (~lines 100-109)
**Current first bullet:** `- Your use of the App`
**Replace with:** `- Your use of the App in breach of these Terms or applicable law`

**Add after final bullet and before survival sentence:**
```markdown

Notwithstanding the above, you are not required to indemnify us to the extent that a claim arises from our own negligence, wilful misconduct, or breach of these Terms.
```

#### 1.7 Narrow termination (~lines 119-124)
**Current:**
```markdown
We may terminate or suspend your access to the App at any time, without prior notice, for:
- Violation of these Terms
- Conduct that we determine is harmful to other users or the App
- Any other reason at our sole discretion
```
**Replace with:**
```markdown
We may terminate or suspend your access to the App at any time for:
- Violation of these Terms
- Conduct that we reasonably determine is harmful to other users or the App
- A legal or regulatory requirement that compels us to do so
- Discontinuation of the App (with 30 days' notice where practicable)
```

#### 1.8 Add Disputes Tribunal reference to Dispute Resolution (~line 145)
**After step 3 (Court proceedings), add:**
```markdown

For disputes involving claims under NZ$60,000, either party may also refer the matter to the Disputes Tribunal of New Zealand.
```

#### 1.9 Update Contact Us with NZBN + address (~lines 155-159)
**Current:**
```markdown
## Contact Us

If you have questions about these Terms, please contact us at:

**Email**: dev@aiconsult.co.nz
```
**Replace with:**
```markdown
## Contact Us

InspectPro is operated by AI Consult Ltd.

**NZBN**: 9429052142376
**Address**: 25 Edinburgh Avenue, Rosehill, Papakura 2113, New Zealand
**Email**: dev@aiconsult.co.nz
```

---

### Phase 2: EULA.md

**File:** `EULA.md` (126 lines)

#### 2.1 Add entity identification to Agreement section (~line 7)
**Current:** `...InspectPro ("we", "our", or "us")...`
**After intro paragraph, add:** "InspectPro is developed and operated by AI Consult Ltd (NZBN: 9429052142376), New Zealand."

#### 2.2 Add business use acknowledgment (after Cost section, ~line 56)
**Insert new section (same as ToS, substituting "this EULA" for "these Terms"):**
```markdown
## Business Use Acknowledgment

By using the App, you represent and warrant that you are acquiring the App primarily for business or professional purposes and not for personal, domestic, or household use. To the extent permitted by section 43(2) of the Consumer Guarantees Act 1993 (NZ), the consumer guarantees under that Act do not apply to the supply of the App where it is acquired for business purposes.
```

#### 2.3 Add AS 4349.1 + NZS 4306:2005 to Fitness for Purpose Disclaimer (~line 61)
**Current:** `...under the Building Act 2004 or any other legislation.`
**Replace with:** `...under the Building Act 2004 (NZ), NZS 4306:2005 (Residential Property Inspection), AS 4349.1 (Inspection of Buildings), or any other legislation or standard.`

#### 2.4 Narrow indemnification (~lines 83-92)
**Same changes as ToS Phase 1.6:**
- First bullet: `- Your use of the App` → `- Your use of the App in breach of this EULA or applicable law`
- Add carve-out paragraph before survival sentence

#### 2.5 Narrow termination (~line 94-99)
**Current:** "Your rights under this EULA will terminate automatically if you fail to comply with any of its terms."
**Add after this sentence:**
```
We may also terminate this EULA if we discontinue the App (with 30 days' notice where practicable) or if required by law.
```

#### 2.6 Add Dispute Resolution section (between Governing Law and Severability, ~line 108)
**Insert new section mirroring ToS:**
```markdown
## Dispute Resolution

Any dispute arising from this EULA or your use of the App shall be resolved through the following process:

1. **Informal resolution.** The parties will first attempt to resolve the dispute through good faith negotiation for a period of 30 days from written notice of the dispute.
2. **Mediation.** If the dispute is not resolved informally, either party may refer the dispute to mediation administered by the Resolution Institute (or its successor) under its mediation rules. The mediation will take place in New Zealand. The costs of mediation will be shared equally.
3. **Court proceedings.** If mediation does not resolve the dispute, either party may commence proceedings in the courts of New Zealand.

For disputes involving claims under NZ$60,000, either party may also refer the matter to the Disputes Tribunal of New Zealand.
```

#### 2.7 Update Survival clause (~line 103)
**Current:** `...Disclaimer of Warranties, Fitness for Purpose Disclaimer, Limitation of Liability, Australian Consumer Law Notice, Indemnification, Governing Law, and Severability.`
**Replace with:** `...Disclaimer of Warranties, Fitness for Purpose Disclaimer, Limitation of Liability, Australian Consumer Law Notice, Indemnification, Governing Law, Dispute Resolution, and Severability.`

#### 2.8 Update Contact Us with NZBN + address (~lines 117-121)
**Same pattern as ToS Phase 1.9.**

---

### Phase 3: PRIVACY_POLICY.md

**File:** `PRIVACY_POLICY.md` (172 lines)

#### 3.1 Add entity identification to Introduction (~line 6)
**After intro paragraph, add:** "InspectPro is developed and operated by AI Consult Ltd (NZBN: 9429052142376), New Zealand."

#### 3.2 Add user privacy obligations note to Information You Provide (~line 14)
**After the three existing bullet points (Client Information, Inspection Data, Inspector Information), add:**
```markdown

**Your obligations:** When you enter personal information about third parties (such as clients) into the App, you become the holder of that information. You are responsible for ensuring your collection, storage, and use of that information complies with the Privacy Act 2020 (NZ), the Privacy Act 1988 (Cth), and any other applicable privacy legislation. We do not access or process this information on your behalf.
```

#### 3.3 Add explicit data holder statement to How We Store Your Data (~line 22)
**After existing bullet list, add:**
```markdown

**Important:** Because all data is stored locally on your device and we do not have access to it, you — not InspectPro — are the holder and controller of the personal information entered into the App.
```

#### 3.4 Add missing IPPs to NZ Privacy Act section (~lines 57-71)
**After IPP 4 (Storage and security, ~line 65), insert:**
```markdown
- **Security safeguards (IPP 5):** We design the App to support the security of personal information stored on your device. We do not transmit personal information over the internet, and the App does not create external copies of your data.
```

**After IPP 11 (Disclosure, ~line 77), insert:**
```markdown
- **Disclosure outside New Zealand (IPP 12):** We do not disclose personal information to any recipient outside New Zealand. Data only leaves your device when you choose to share a report, at which point you control the recipient.
- **Unique identifiers (IPP 13):** The App does not assign unique identifiers to users derived from government-issued identifiers. Any internal identifiers used for inspection records are generated locally on your device.
```

#### 3.5 Expand Australian Privacy section (~lines 84-92)
**Replace entire section with APP-level detail:**
```markdown
## Australian Privacy

If you are located in Australia, the Australian Privacy Principles (APPs) under the Privacy Act 1988 (Cth) apply. We are committed to compliance with the APPs, including:

- **Open and transparent management (APP 1):** This Privacy Policy describes how we manage personal information. We do not hold personal information on our servers.
- **Anonymity and pseudonymity (APP 2):** You may use the App without identifying yourself to us. We do not require account registration.
- **Collection of solicited personal information (APP 3):** We collect only the minimum information necessary for the App's functionality (device type and OS version for compatibility).
- **Dealing with unsolicited personal information (APP 4):** We do not receive unsolicited personal information as all data is stored locally on your device.
- **Notification of collection (APP 5):** This Privacy Policy serves as notification of any information we collect.
- **Use or disclosure (APP 6):** We do not use or disclose personal information for any purpose other than App compatibility.
- **Direct marketing (APP 7):** We do not use personal information for direct marketing purposes.
- **Cross-border disclosure (APP 8):** We do not disclose personal information to overseas recipients.
- **Adoption, use, or disclosure of government related identifiers (APP 9):** The App does not collect, use, or disclose government-related identifiers.
- **Quality of personal information (APP 10):** We rely on you to provide accurate information within the App. You can update information at any time.
- **Security of personal information (APP 11):** All personal information is stored locally on your device under your device's security protections. We do not transmit or store your data on external servers.
- **Access to personal information (APP 12):** You can access all your personal information directly within the App at any time.
- **Correction of personal information (APP 13):** You can correct any personal information directly within the App at any time.

If you believe we have breached the APPs, you may lodge a complaint with us at dev@aiconsult.co.nz. We will respond to your complaint within 30 days. If you are not satisfied with our response, you may lodge a complaint with the Office of the Australian Information Commissioner (OAIC) at [www.oaic.gov.au](https://www.oaic.gov.au).
```

#### 3.6 Add AU Notifiable Data Breaches section (after Australian Privacy section)
```markdown
## Australian Notifiable Data Breaches

Under Part IIIC of the Privacy Act 1988 (Cth), we are required to notify the Australian Information Commissioner and affected individuals of any eligible data breach that is likely to result in serious harm. Given that all data is stored locally on your device and we do not have access to your data, the risk of an eligible breach on our part is extremely limited. However, if we become aware of any breach that meets the threshold, we will:

1. Notify the Office of the Australian Information Commissioner as soon as practicable
2. Notify affected individuals as soon as practicable
3. Provide details of the breach, the information involved, and recommended steps
```

#### 3.7 Align Children's Privacy to 16 (~line 96)
**Current:** `InspectPro is not intended for use by children under 13. We do not knowingly collect information from children under 13.`
**Replace with:** `InspectPro is not intended for use by children under 16. We do not knowingly collect information from children under 16. The App is designed for professional use by property inspection professionals.`

#### 3.8 Add 30-day complaint response timeframe
Already incorporated in expanded Australian Privacy section (3.5). Also add to NZ section — after the Notifiable Privacy Breaches section, and to the Privacy Commissioner Contact Information section:
**In Privacy Commissioner Contact Information (~line 159), update intro:**
**Current:** `If you have concerns about our handling of your personal information, please contact us first at dev@aiconsult.co.nz. If you are not satisfied with our response, you may contact the relevant authority:`
**Replace with:** `If you have concerns about our handling of your personal information, please contact us first at dev@aiconsult.co.nz. We will respond within 30 days. If you are not satisfied with our response, you may contact the relevant authority:`

#### 3.9 Update Contact Us with NZBN + address (~lines 163-167)
**Same pattern as ToS Phase 1.9.**

---

### Phase 4: SUPPORT.md

**File:** `SUPPORT.md` (55 lines)

#### 4.1 Update Contact Us with NZBN + address (~lines 3-7)
**Current:**
```markdown
## Contact Us

For questions, bug reports, or feature requests, reach out to us at:

**Email**: dev@aiconsult.co.nz
```
**Replace with:**
```markdown
## Contact Us

InspectPro is operated by AI Consult Ltd.

**NZBN**: 9429052142376
**Address**: 25 Edinburgh Avenue, Rosehill, Papakura 2113, New Zealand
**Email**: dev@aiconsult.co.nz
```

---

### Phase 5: index.html

**File:** `index.html` (560 lines)

Mirror ALL changes from Phases 1-4 into corresponding HTML sections using existing patterns:

#### 5.1 ToS section (~lines 56-207)
- Add entity identification after intro paragraph
- Add Business Use Acknowledgment `<h2>` section after Cost
- Update Professional Responsibility `<ul>` with NZS 4306 and privacy obligations bullets
- Add Fair Trading Act paragraph after CGA/ACL carve-out
- Update Indemnification list and add carve-out paragraph
- Update Termination list (remove "sole discretion", add cause-based grounds)
- Add Disputes Tribunal paragraph after Dispute Resolution ordered list
- Update Contact Us with NZBN + address

#### 5.2 Privacy Policy section (~lines 209-381)
- Add entity identification after intro paragraph
- Add user privacy obligations paragraph after Information You Provide
- Add data holder statement after How We Store Your Data
- Add IPPs 5, 12, 13 to NZ Privacy Act list
- Replace Australian Privacy section with full APP mapping
- Add AU Notifiable Data Breaches section
- Update Children's Privacy from 13 to 16
- Update complaint response timeframe to 30 days
- Update Contact Us with NZBN + address

#### 5.3 EULA section (~lines 383-493)
- Add entity identification after intro paragraph
- Add Business Use Acknowledgment `<h2>` section after Cost
- Update Fitness for Purpose Disclaimer with AS 4349.1 + NZS 4306
- Update Indemnification list and add carve-out paragraph
- Update Termination with discontinuation/legal requirement grounds
- Add Dispute Resolution `<h2>` section with `<ol>` + Disputes Tribunal note
- Update Survival clause to include Dispute Resolution
- Update Contact Us with NZBN + address

#### 5.4 Support section (~lines 495-554)
- Update Contact Us with NZBN + address

## Dependencies & Risks

- **No external dependencies** — all changes are to static legal content
- **Risk: CGA s43(2) wording** — The business use acknowledgment should be reviewed by a NZ lawyer before relying on it to exclude CGA guarantees. The soft representation is standard practice but not a guaranteed defence.
- **Risk: Indemnification narrowing** — Making the carve-out too broad could undermine the indemnification's purpose. The current approach (carve-out for our own negligence/misconduct) is proportionate.
- **Consistency risk** — 5 files must stay in sync. Edit .md files first, then mirror to HTML.

## References & Research

### Internal References
- Brainstorm: `docs/brainstorms/2026-03-03-nz-au-legal-deep-dive-brainstorm.md`
- Current files: `TERMS_OF_USE.md`, `EULA.md`, `PRIVACY_POLICY.md`, `SUPPORT.md`, `index.html`

### Key Statutes Referenced
- Consumer Guarantees Act 1993 (NZ) — s43(2) business use exclusion
- Fair Trading Act 1986 (NZ) — unfair contract terms (Part 3A)
- Privacy Act 2020 (NZ) — IPPs 1-13, Part 6 notifiable breaches
- Privacy Act 1988 (Cth) — APPs 1-13, Part IIIC notifiable data breaches
- Building Act 2004 (NZ)
- NZS 4306:2005 — Residential Property Inspection
- AS 4349.1 — Inspection of Buildings

### Company Details
- Entity: AI Consult Ltd
- NZBN: 9429052142376
- Address: 25 Edinburgh Avenue, Rosehill, Papakura 2113, New Zealand
- Email: dev@aiconsult.co.nz
