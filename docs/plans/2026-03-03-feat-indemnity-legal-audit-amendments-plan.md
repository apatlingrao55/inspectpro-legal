---
title: "feat: Indemnity & Legal Audit Amendments (NZ/AU)"
type: feat
status: completed
date: 2026-03-03
brainstorm: docs/brainstorms/2026-03-03-indemnity-legal-audit-brainstorm.md
---

# feat: Indemnity & Legal Audit Amendments (NZ/AU)

## Overview

Targeted amendments to InspectPro's legal docs (ToS, EULA, Privacy Policy, index.html) to fix an incorrect statutory threshold, strengthen clickwrap enforceability, add terms versioning, harden the indemnity clause, and add a future-proofing note for content moderation. Scoped to NZ/AU markets only.

## Acceptance Criteria

### 1. Fix Disputes Tribunal Threshold

- [x] `TERMS_OF_USE.md` line 159: Change `NZ$60,000` → `NZ$30,000`
- [x] `EULA.md` line 125: Change `NZ$60,000` → `NZ$30,000`
- [x] `index.html`: Mirror both changes in the rendered HTML

### 2. Update Acceptance Language (Browsewrap → Clickwrap)

- [x] `TERMS_OF_USE.md` line 7 ("Agreement to Terms"): Replace "By downloading, installing, or using InspectPro ("the App"), you agree to be bound by these Terms of Use ("Terms")." with language referencing explicit in-app acceptance:

```markdown
By tapping "I Agree", checking the acceptance checkbox, or otherwise explicitly accepting these Terms within the App, you agree to be bound by these Terms of Use ("Terms"). A link to the full text of these Terms is provided at the point of acceptance. If you do not agree to these Terms, do not use the App.
```

- [x] `TERMS_OF_USE.md` line 179 (closing statement): Update to match:

```markdown
By accepting these Terms within the App, you acknowledge that you have read, understood, and agree to be bound by these Terms of Use.
```

- [x] `EULA.md` line 9: Replace "By downloading, installing, or using the App, you agree to be bound by the terms of this EULA. If you do not agree, do not use the App." with:

```markdown
By tapping "I Agree", checking the acceptance checkbox, or otherwise explicitly accepting this EULA within the App, you agree to be bound by the terms of this EULA. A link to the full text of this EULA is provided at the point of acceptance. If you do not agree, do not use the App.
```

- [x] `EULA.md` line 145 (closing statement): Update to match:

```markdown
By accepting this EULA within the App, you acknowledge that you have read, understood, and agree to be bound by this End User License Agreement.
```

- [x] `index.html`: Mirror all acceptance language changes

### 3. Add Clickwrap Implementation Guidance

- [x] `TERMS_OF_USE.md`: Add a new subsection under "Changes to Terms" titled "Acceptance and Record-Keeping" with the following developer-facing requirements:

```markdown
## Acceptance and Record-Keeping

Acceptance of these Terms is recorded within the App. When you accept these Terms, the following information is logged:
- The date and time of acceptance
- The version of the Terms accepted
- A device identifier

If we make material changes to these Terms, you will be asked to review and re-accept the updated version before continuing to use the App. Previous versions of these Terms are archived and available upon request.
```

- [x] `index.html`: Mirror this new section

### 4. Add Terms Versioning

- [x] `TERMS_OF_USE.md`: Add version number below the "Last Updated" line:

```markdown
**Last Updated: March 2026**
**Version: 1.0**
```

- [x] `TERMS_OF_USE.md`: Add version history section before "Contact Us":

```markdown
## Version History

| Version | Date | Description |
|---------|------|-------------|
| 1.0 | March 2026 | Initial publication with NZ/AU legal compliance |
```

- [x] `EULA.md`: Add version number below "Last Updated":

```markdown
**Last Updated: March 2026**
**Version: 1.0**
```

- [x] `EULA.md`: Add version history section before "Contact Us":

```markdown
## Version History

| Version | Date | Description |
|---------|------|-------------|
| 1.0 | March 2026 | Initial publication with NZ/AU legal compliance |
```

- [x] `PRIVACY_POLICY.md`: Add version number below "Last Updated":

```markdown
**Last Updated: March 2026**
**Version: 1.0**
```

- [x] `PRIVACY_POLICY.md`: Add version history section before "Contact Us":

```markdown
## Version History

| Version | Date | Description |
|---------|------|-------------|
| 1.0 | March 2026 | Initial publication with NZ/AU legal compliance |
```

- [x] `index.html`: Mirror all version numbers and version history tables

### 5. Strengthen Indemnity Clause

- [x] `TERMS_OF_USE.md` lines 109-120: Replace current indemnity section with strengthened version:

```markdown
## Indemnification

You agree to indemnify, defend, and hold harmless InspectPro and its developers from any claims, damages, losses, liabilities, and reasonable legal fees and expenses arising from:
- Your misuse of the App or use in a manner not authorised by these Terms
- Your breach of these Terms or applicable law
- Content you create, share, or distribute using the App, including any infringing, defamatory, or unlawful content
- Third-party claims arising from inspection reports or documentation you produce using the App
- Your violation of any rights of another party

**Exclusions.** You are not required to indemnify us to the extent that a claim arises from:
- Our own negligence, wilful misconduct, or breach of these Terms
- Any non-excludable consumer guarantee under the Consumer Guarantees Act 1993 (NZ) or the Australian Consumer Law
- Regulatory action taken against us by the Commerce Commission (NZ), the Australian Competition and Consumer Commission (ACCC), the Office of the Privacy Commissioner (NZ), or the Office of the Australian Information Commissioner (OAIC)

This indemnification obligation survives the termination of these Terms and your use of the App.
```

- [x] `EULA.md` lines 89-100: Replace with matching strengthened version (substituting "this EULA" for "these Terms")

- [x] `index.html`: Mirror both strengthened indemnity sections

### 6. Add Future-Proofing Note for Content Moderation

- [x] `TERMS_OF_USE.md`: Add a new section after "Acceptable Use" titled "Content Moderation":

```markdown
## Content Moderation

InspectPro currently operates as an offline, local-only application. All content you create is stored on your device and is not shared through our services.

If we introduce cloud storage, content sharing, or user account features in the future, we will implement appropriate content moderation policies, including a copyright notice-and-takedown process and a right to remove user content. These policies will be added to these Terms before any such features are made available, and you will be notified in accordance with our Changes to Terms process.
```

- [x] `index.html`: Mirror this new section

## Implementation Order

1. **Disputes Tribunal fix** — smallest change, immediate correctness fix
2. **Terms versioning** — adds version numbers to all docs (needed before acceptance language references versions)
3. **Acceptance language** — update browsewrap → clickwrap language
4. **Clickwrap guidance** — add the acceptance and record-keeping section
5. **Indemnity strengthening** — replace indemnity sections in ToS and EULA
6. **Future-proofing note** — add content moderation section to ToS
7. **index.html sync** — mirror ALL changes to the HTML site (do this last, all at once)

## Files Affected

| File | Sections Changed |
|------|-----------------|
| `TERMS_OF_USE.md` | Agreement to Terms, Changes to Terms (new subsection), Indemnification, Dispute Resolution, new Content Moderation section, version header, new Version History section, closing statement |
| `EULA.md` | Agreement, Indemnification, Dispute Resolution, version header, new Version History section, closing statement |
| `PRIVACY_POLICY.md` | Version header, new Version History section |
| `index.html` | All corresponding HTML sections |

## Convention Notes

- Markdown files are source of truth; `index.html` must mirror ALL changes
- HTML patterns: `<h2>` for sections, `<ul>/<ol>` for lists, `<p><strong>Label:</strong> text</p>` for bold labels, `class="legal-caps"` for ALL-CAPS disclaimers
- Conventional commits: `feat:` prefix
- All docs must include NZBN, physical address, and `dev@aiconsult.co.nz`

## References

- Brainstorm: `docs/brainstorms/2026-03-03-indemnity-legal-audit-brainstorm.md`
- Disputes Tribunal Act 1988 (NZ) — jurisdiction limit NZ$30,000
- Consumer Guarantees Act 1993 (NZ) — s43(2) business use exclusion
- Fair Trading Act 1986 (NZ) — unfair terms provisions
- Privacy Act 2020 (NZ) — Part 6 notifiable breaches
- Australian Consumer Law (Schedule 2, Competition and Consumer Act 2010)
