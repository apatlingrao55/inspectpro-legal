# Brainstorm: Risk Mitigation & Disclaimer Strengthening (NZ/AU)

**Date:** 2026-03-03
**Status:** Draft
**Scope:** Legal docs only (NZ/AU markets). App UX and business actions captured as notes.

## What We're Building

Targeted strengthening of InspectPro's legal docs to better separate the app from inspector professional judgment, add a recommended PDF report disclaimer, future-proof third-party data disclaimers, and add a professional qualification warranty clause.

## Why This Approach

InspectPro operates in the NZ/AU property inspection market where leaky homes litigation creates a long liability tail. The existing docs disclaim fitness for purpose and reference NZS 4306:2005, but the language can be strengthened to make the app's role unmistakable: it captures and formats observations, nothing more.

## Key Decisions

### 1. Strengthen Professional Responsibility & Fitness for Purpose

**What:** Tighten existing sections (not new sections) to explicitly state the app's role is limited to capturing and formatting inspector observations.

**Current language (ToS Professional Responsibility):**
> "The App is a documentation tool to assist with property inspections"
> "The App does not replace professional judgment, expertise, or the services of a qualified building inspector"

**Strengthen to include:**
- The App captures and formats the inspector's observations. It does not assess, certify, guarantee, or warrant anything about the property.
- All professional opinions, conclusions, and assessments in a report are the inspector's alone.
- The App does not verify the accuracy, completeness, or professional standard of any content entered by the user.
- Explicit weathertightness mention: the App makes no representation about a property's weathertightness or compliance with the Building Code.

**Current language (EULA Fitness for Purpose Disclaimer):**
> "The App is a property inspection documentation tool only."

**Strengthen to include:**
- Same "captures and formats observations" distinction.
- Add explicit weathertightness non-warranty.
- Add: no output of the App constitutes a building report, compliance certificate, or professional assessment under any legislation or standard.

**Files:** TERMS_OF_USE.md, EULA.md, index.html

**Note:** Also fix asymmetry — add AS 4349.1 reference to ToS Professional Responsibility (currently only in EULA).

### 2. Recommended PDF Report Disclaimer Text

**What:** Write the exact disclaimer wording that should appear on every generated PDF report. This serves as a spec for the iOS app implementation.

**Recommended text:**

> **Disclaimer:** This report reflects the professional observations of the inspector named above, made on the date of inspection stated. It was prepared using InspectPro, a documentation and reporting tool only. InspectPro does not assess, certify, guarantee, or warrant the condition, safety, weathertightness, or compliance of the property. This report does not constitute a warranty or guarantee of the property's condition. All opinions, conclusions, and recommendations are those of the inspector alone. Any reliance on this report is at the reader's own risk. The inspector's qualifications, licensing, and professional indemnity insurance should be verified independently.

**Format:** Should appear in a visually distinct footer/box on every page or on the final page of every PDF.

**Not a legal doc change** — captured here as a reference spec for the iOS app.

### 3. Third-Party Data Disclaimer (Future-Proofing)

**What:** Add a new section to the ToS for when external data sources (council records, LINZ, property databases) are integrated.

**Status:** The app does not currently integrate with any external databases. This is pure future-proofing.

**Language to add (new section in ToS, near Third-Party Services):**

> If the App displays data sourced from third parties (including but not limited to local council records, Land Information New Zealand (LINZ), or property information databases), that data is provided for reference only. We do not verify, warrant, or guarantee the accuracy, completeness, or currency of any third-party data. You must independently verify any third-party data before relying on it in a professional capacity.

**Files:** TERMS_OF_USE.md, index.html

### 4. Professional Qualification Warranty Clause

**What:** Add a clause where users represent they hold appropriate professional qualifications, licensing, and insurance for their jurisdiction. Strengthens the existing Business Use Acknowledgment.

**Language to add (new subsection under or after Business Use Acknowledgment):**

> By using the App for property inspection purposes, you represent and warrant that:
> - You hold the professional qualifications, certifications, or licences required in your jurisdiction to conduct property inspections
> - You maintain appropriate professional indemnity insurance for the inspection services you provide
> - You are solely responsible for ensuring that your inspection practices comply with all applicable laws, regulations, and professional standards
>
> InspectPro does not verify your qualifications, licensing, or insurance status. You indemnify InspectPro against any claims arising from your representation of professional status.

**Files:** TERMS_OF_USE.md, EULA.md, index.html

## What We're NOT Changing

- **App UX flows** (active disclaimers, onboarding verification) — out of scope for this repo
- **Privacy Policy** — no changes needed for these items
- **Copyright takedown / content moderation** — already covered in previous brainstorm
- **Clickwrap acceptance** — already implemented in previous brainstorm

## Files Affected

| File | Changes |
|------|---------|
| `TERMS_OF_USE.md` | Professional Responsibility (strengthen), new Third-Party Data section, new Professional Qualification Warranty, AS 4349.1 addition |
| `EULA.md` | Fitness for Purpose Disclaimer (strengthen), new Professional Qualification Warranty |
| `index.html` | Mirror all changes |

## Recommended Business Actions

These are not legal doc changes but are captured here as follow-up action items:

### A. Get Weathertightness Disclaimer Reviewed by NZ Construction Law Specialist

**Priority:** High. The weathertightness/leaky homes liability tail is the single highest risk area for a NZ property inspection app. A one-time legal review of the strengthened disclaimer language (items 1 and 2 above) by a specialist construction lawyer is the most cost-effective risk mitigation available.

**Estimated cost:** $500-$2,000 for a targeted review of specific clauses.

### B. Carry Professional Indemnity Insurance as Developer

**Priority:** Medium. Won't prevent claims but provides coverage if one lands. Solo NZ developer rough cost: $500-$1,500/year. Consider obtaining before App Store launch or first commercial user.

### C. Implement Active Disclaimers in iOS App

**Priority:** Medium. Surface warnings at the point where inspectors fill in high-risk sections (weathertightness, structural, electrical). Require tap-through acknowledgment before completing those fields. Log acknowledgment with timestamp, same as clickwrap acceptance.

### D. Implement Inspector Qualification Verification in iOS App

**Priority:** Medium. Onboarding flow requiring inspectors to confirm qualifications and insurance. Creates a record that the user represented themselves as a licensed professional. Shifts professional liability chain onto them.

## Open Questions

None — all decisions resolved during brainstorm dialogue.
