---
title: "feat: Risk Mitigation & Disclaimer Strengthening (NZ/AU)"
type: feat
status: completed
date: 2026-03-03
brainstorm: docs/brainstorms/2026-03-03-risk-mitigation-disclaimers-brainstorm.md
---

# feat: Risk Mitigation & Disclaimer Strengthening (NZ/AU)

## Overview

Strengthen InspectPro's legal docs to explicitly separate the app from inspector professional judgment, add a third-party data disclaimer, add a professional qualification warranty, write a recommended PDF report disclaimer, and fix an AS 4349.1 reference asymmetry. Scoped to NZ/AU markets, legal docs only.

## Acceptance Criteria

### 1. Strengthen Professional Responsibility (ToS)

- [x] `TERMS_OF_USE.md` lines 68-76: Replace the current Professional Responsibility section with strengthened version:

```markdown
## Professional Responsibility

- The App captures and formats the inspector's observations. It does not assess, certify, guarantee, or warrant anything about the condition, safety, weathertightness, or compliance of any property
- The App does not replace professional judgment, expertise, or the services of a qualified building inspector
- The App does not certify the condition, safety, or compliance of any property under the Building Act 2004, NZS 4306:2005 (Residential Property Inspection), AS 4349.1 (Inspection of Buildings), or any other legislation or standard
- No output of the App constitutes a building report, compliance certificate, or professional assessment under any legislation or standard
- The App is not a substitute for independent professional advice, and no output of the App should be treated as such
- All professional opinions, conclusions, and assessments contained in a report are the inspector's alone
- The App does not verify the accuracy, completeness, or professional standard of any content entered by the user
- You are responsible for the accuracy and completeness of your inspection reports
- We do not guarantee that reports created with the App will meet specific professional standards or legal requirements
- The App makes no representation about a property's weathertightness or compliance with the New Zealand Building Code or any Australian building standard
- If you enter personal information about third parties (such as clients) into the App, you are responsible for ensuring your collection and use of that information complies with the Privacy Act 2020 (NZ), the Privacy Act 1988 (Cth), and any other applicable privacy legislation
```

- [x] `index.html`: Mirror the strengthened Professional Responsibility section

### 2. Strengthen Fitness for Purpose Disclaimer (EULA)

- [x] `EULA.md` line 66-68: Replace the current Fitness for Purpose Disclaimer with strengthened version:

```markdown
## Fitness for Purpose Disclaimer

The App is a property inspection documentation tool only. It captures and formats the inspector's observations. It does not assess, certify, guarantee, or warrant anything about the condition, safety, weathertightness, or compliance of any property.

The App is not a substitute for the services of a qualified building inspector, engineer, or other professional. The App does not certify the condition, safety, or compliance of any property under the Building Act 2004 (NZ), NZS 4306:2005 (Residential Property Inspection), AS 4349.1 (Inspection of Buildings), or any other legislation or standard.

No output of the App constitutes a building report, compliance certificate, or professional assessment under any legislation or standard. No output of the App should be treated as independent professional advice. All professional opinions, conclusions, and assessments contained in a report are the inspector's alone.

The App makes no representation about a property's weathertightness or compliance with the New Zealand Building Code or any Australian building standard.
```

- [x] `index.html`: Mirror the strengthened Fitness for Purpose Disclaimer

### 3. Add Third-Party Data Disclaimer (ToS)

- [x] `TERMS_OF_USE.md`: Add a new section after "Third-Party Services" (line 52) titled "Third-Party Data":

```markdown
## Third-Party Data

If the App displays data sourced from third parties (including but not limited to local council records, Land Information New Zealand (LINZ), or property information databases), that data is provided for reference only. We do not verify, warrant, or guarantee the accuracy, completeness, or currency of any third-party data. You must independently verify any third-party data before relying on it in a professional capacity.
```

- [x] `index.html`: Mirror this new section

### 4. Add Professional Qualification Warranty (ToS and EULA)

- [x] `TERMS_OF_USE.md`: Add a new section after "Business Use Acknowledgment" (line 32) titled "Professional Qualification Warranty":

```markdown
## Professional Qualification Warranty

By using the App for property inspection purposes, you represent and warrant that:
- You hold the professional qualifications, certifications, or licences required in your jurisdiction to conduct property inspections
- You maintain appropriate professional indemnity insurance for the inspection services you provide
- You are solely responsible for ensuring that your inspection practices comply with all applicable laws, regulations, and professional standards

InspectPro does not verify your qualifications, licensing, or insurance status. You indemnify InspectPro against any claims arising from your representation of professional status.
```

- [x] `EULA.md`: Add matching section after "Business Use Acknowledgment" (line 53):

```markdown
## Professional Qualification Warranty

By using the App for property inspection purposes, you represent and warrant that:
- You hold the professional qualifications, certifications, or licences required in your jurisdiction to conduct property inspections
- You maintain appropriate professional indemnity insurance for the inspection services you provide
- You are solely responsible for ensuring that your inspection practices comply with all applicable laws, regulations, and professional standards

InspectPro does not verify your qualifications, licensing, or insurance status. You indemnify InspectPro against any claims arising from your representation of professional status.
```

- [x] `index.html`: Mirror both new sections

### 5. Recommended PDF Report Disclaimer Text

- [x] Add a new file `REPORT_DISCLAIMER.md` containing the recommended PDF report disclaimer text as a spec for the iOS app:

```markdown
# InspectPro — Recommended PDF Report Disclaimer

**Purpose:** This text should appear on every PDF report generated by InspectPro, in a visually distinct footer or box.

## Disclaimer Text

**Disclaimer:** This report reflects the professional observations of the inspector named above, made on the date of inspection stated. It was prepared using InspectPro, a documentation and reporting tool only. InspectPro does not assess, certify, guarantee, or warrant the condition, safety, weathertightness, or compliance of the property. This report does not constitute a warranty or guarantee of the property's condition. All opinions, conclusions, and recommendations are those of the inspector alone. Any reliance on this report is at the reader's own risk. The inspector's qualifications, licensing, and professional indemnity insurance should be verified independently.
```

## Implementation Order

1. **Professional Qualification Warranty** — new section in both ToS and EULA (after Business Use Acknowledgment)
2. **Third-Party Data Disclaimer** — new section in ToS (after Third-Party Services)
3. **Professional Responsibility strengthening** — replace existing ToS section
4. **Fitness for Purpose strengthening** — replace existing EULA section
5. **PDF Report Disclaimer** — new reference file
6. **index.html sync** — mirror ALL changes (do last, all at once)

## Files Affected

| File | Sections Changed |
|------|-----------------|
| `TERMS_OF_USE.md` | New Professional Qualification Warranty, new Third-Party Data, Professional Responsibility (rewritten) |
| `EULA.md` | New Professional Qualification Warranty, Fitness for Purpose Disclaimer (rewritten) |
| `index.html` | All corresponding HTML sections |
| `REPORT_DISCLAIMER.md` | New file — PDF disclaimer spec |

## Convention Notes

- Markdown files are source of truth; `index.html` must mirror ALL changes
- HTML patterns: `<h2>` for sections, `<ul>/<ol>` for lists, `<p><strong>Label:</strong> text</p>` for bold labels
- Conventional commits: `feat:` prefix

## References

- Brainstorm: `docs/brainstorms/2026-03-03-risk-mitigation-disclaimers-brainstorm.md`
- Building Act 2004 (NZ)
- NZS 4306:2005 (Residential Property Inspection)
- AS 4349.1 (Inspection of Buildings)
- New Zealand Building Code (Schedule 1, Building Regulations 1992)
