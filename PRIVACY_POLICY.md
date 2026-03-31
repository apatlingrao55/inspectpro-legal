# InspectPro Privacy Policy

**Version 3.0 — Last Updated: March 2026**

This Privacy Policy explains how InspectPro ("we", "our", "us") — operated by aiconsult.co.nz — collects, stores, uses, and discloses your personal information. This policy is written in accordance with the **New Zealand Privacy Act 2020** and its 13 Information Privacy Principles (IPPs).

By using InspectPro, you acknowledge that you have read and understood this Privacy Policy.

---

## 1. Who This Policy Applies To

This policy applies to:
- **Solo inspectors** who subscribe directly to InspectPro
- **Enterprise users** who access InspectPro through a company or team subscription

References to "you" and "your" include both solo and enterprise users.

---

## 2. What Personal Information We Collect

We only collect personal information that is necessary to provide the InspectPro service (IPP 1).

### 2.1 Account Information
- **Email address** — required to create an account, authenticate your identity, and manage your subscription
- **Password** — stored as a hashed credential; we never store your password in plain text
- **Inspector name** — as you enter it for use on reports (optional, but used on reports if provided)

### 2.2 Client and Inspection Data (entered by you)
- Client names, email addresses, phone numbers, and property addresses
- Inspection photos, notes, comments, severity ratings, and recommendations
- Company association and subscription membership (for enterprise accounts)

This data is entered by you to produce inspection reports. Providing it is at your discretion.

### 2.3 Subscription and Billing Data
- Subscription status and renewal dates
- Payment processing is handled entirely by Stripe. We do not collect or store payment card numbers (see Section 6.2)

### 2.4 Device and Usage Information
- Device type and operating system version, collected solely for app compatibility purposes
- We do not collect location data, advertising identifiers, or behavioural tracking data

---

## 3. Why We Collect This Information and How It Is Used (IPP 3, IPP 10)

We collect personal information only for the following purposes:

| Data | Purpose | Legal basis |
|------|---------|------------|
| Email address and password | Account authentication and subscription management | Contract performance |
| Client and inspection data | Generating inspection reports on your device | Contract performance |
| Photos and notes | Local report creation and backend data recovery backup (see Section 4) | Contract performance |
| Subscription status | Verifying your access to the service | Contract performance |
| Device information | App compatibility and troubleshooting | Legitimate interest |

We will not use your personal information for any purpose other than those listed above without your explicit consent.

---

## 4. How and Where Your Data Is Stored

InspectPro uses a **hybrid storage model**. Your device is the primary location for your data. Supabase cloud infrastructure is used in limited, specific circumstances described below.

### 4.1 Device (Primary Storage)
All inspection data — including photos, notes, client details, report history, and subscription cache — is stored **locally on your device** as the primary copy. This data is under your direct control.

- You can delete individual inspections, photos, or client records at any time within the app
- Uninstalling the app removes all locally stored data
- We recommend maintaining your own device backups via iCloud or iTunes as an additional precaution

### 4.2 Supabase — Data Loss Recovery Backup
To protect you from data loss in the event of device failure, theft, or replacement, InspectPro automatically syncs your inspection data — including **compressed photos, notes, and report content** — to our Supabase-hosted backend.

**Important:** This sync exists solely as a data loss recovery mechanism. It is not general cloud storage. The primary copy of your data remains on your device. Supabase is used only to restore your data if your device is lost or damaged.

- Synced data is encrypted in transit (TLS) and at rest
- Synced data is scoped to your account and not accessible to other users
- Supabase hosts infrastructure in the United States and Europe (see Section 5 — Offshore Data)

### 4.3 Supabase — Account and Subscription Data
Your account credentials (email, encrypted password hash) and subscription/membership status are stored in Supabase's hosted PostgreSQL database. This is required to authenticate your account and verify your subscription.

- Subscription status is also cached locally on your device (including plan type, status, and expiry date) for offline access
- This cache is refreshed when the app connects to the internet

### 4.4 Supabase — Temporary PDF Storage (Approval and Delivery Workflows)
When you use the **Approval Workflow** (submit for manager approval) or **Send to Client** features, a finalised PDF report is temporarily uploaded to Supabase Storage to facilitate delivery.

These uploads are:
- Always **user-initiated** — only triggered when you explicitly use these features
- **Scoped to your company account** — not visible to other accounts
- Accessible only via **time-limited signed URLs**
- **Automatically deleted** on a fixed schedule:
  - Approval Workflow PDFs: deleted **72 hours** after upload
  - Send to Client PDFs: deleted **7 days** after upload

PDF reports may contain client names, property addresses, photos, notes, severity ratings, and recommendations.

---

## 5. Offshore Data Transfer (IPP 13)

Some of your personal information is transferred to and stored offshore, via our third-party service providers. Before any offshore transfer, we take reasonable steps to ensure that the recipient country or organisation provides comparable privacy protections to those required under the New Zealand Privacy Act 2020.

| Provider | Data transferred | Location |
|----------|-----------------|----------|
| Supabase | Account data, backup data, temporary PDFs | United States, Europe |
| Stripe | Payment processing (handled on Stripe's infrastructure) | United States |

**Supabase** participates in industry-standard data protection frameworks. Their privacy policy is available at [supabase.com/privacy](https://supabase.com/privacy).

**Stripe** maintains SOC 2 Type II certification and PCI-DSS compliance. Their privacy policy is available at [stripe.com/privacy](https://stripe.com/privacy).

---

## 6. Third-Party Services

### 6.1 Supabase (Authentication, Database, Storage, and Backup)
- **Purpose:** Account authentication, subscription verification, data loss recovery backup, and temporary PDF storage for Approval Workflow and Send to Client features
- **Data shared:** Email address, encrypted password hash, subscription status, compressed inspection data and photos (backup only), and temporary PDF uploads
- **Privacy policy:** [supabase.com/privacy](https://supabase.com/privacy)

### 6.2 Stripe (Payment Processing)
- **Purpose:** Subscription billing and payment processing
- **How it works:** Payment is handled on Stripe's hosted pages. We do not collect, process, or store your payment card details. Stripe receives your payment information directly.
- **Privacy policy:** [stripe.com/privacy](https://stripe.com/privacy)

---

## 7. Data Sharing and Disclosure (IPP 11)

**We do not sell, rent, or share your personal information with third parties for marketing or commercial purposes.**

Your data is only disclosed in the following circumstances:

- **To Supabase** — as described in Section 4 (storage, backup, authentication, temporary PDFs)
- **To Stripe** — for payment processing when you subscribe or manage your billing
- **By you** — when you explicitly share a PDF report via email, messaging, or other apps on your device
- **If required by law** — in response to a valid legal obligation, court order, or request from a regulatory authority with jurisdiction over our business
- **To protect rights or safety** — if we reasonably believe disclosure is necessary to prevent harm or investigate unlawful activity

---

## 8. Data Security (IPP 5)

We implement reasonable security safeguards appropriate to the sensitivity of the information:

- **Local device storage:** Protected by your device's built-in security (iOS encryption, biometric lock)
- **Authentication tokens:** Encrypted using AES-256 before storage, with keys held in the device's Secure Enclave (Expo SecureStore)
- **Network communication:** All data transfers use HTTPS/TLS encryption
- **Supabase backup data:** Encrypted in transit and at rest; scoped to your account
- **Temporary PDFs:** Scoped to your company account; accessible only via time-limited signed URLs; auto-deleted after 72 hours or 7 days as applicable

Despite our best efforts, no system is completely secure. If you become aware of any security issue, please contact our Privacy Officer immediately.

---

## 9. Data Accuracy (IPP 8)

We take reasonable steps to ensure that personal information we hold about you is accurate, up to date, complete, and not misleading. Inspection data and client information is entered by you and is within your direct control to update. If you believe any account information we hold is inaccurate, you have the right to request correction (see Section 10).

---

## 10. Your Rights Under the NZ Privacy Act 2020

You have the following rights in relation to personal information we hold about you:

### Right to Access (IPP 6)
You may request access to the personal information we hold about you. Inspection data, client data, and report history are accessible directly within the app. For account data stored in Supabase, contact our Privacy Officer and we will respond within 20 working days as required by the Privacy Act 2020.

### Right to Correction (IPP 7)
You may request that we correct any personal information we hold about you that is inaccurate, misleading, incomplete, or out of date. We will either make the correction or, if we disagree, attach a note of your requested correction to the record. Contact our Privacy Officer to make a correction request.

### Right to Delete
- You may delete any inspection, photo, client record, or account at any time within the app
- Account data held in Supabase will be deleted within 30 days of a verified deletion request
- Local device data is deleted when you remove records in-app, clear app data, or uninstall the app

### Right to Complain
If you believe we have breached the Privacy Act 2020, you may:
1. Contact our Privacy Officer (details below) — we will acknowledge your complaint within 5 working days and respond within 20 working days
2. If you are not satisfied with our response, complain to the **New Zealand Privacy Commissioner** at [privacy.org.nz](https://www.privacy.org.nz) or call **0800 803 909**

---

## 11. Data Retention (IPP 9)

We do not retain personal information longer than necessary for the purposes for which it was collected.

| Data type | Retention period |
|-----------|-----------------|
| Local inspection data | Until you delete it or uninstall the app |
| Supabase backup data (inspection data and photos) | Until you request account deletion |
| Account data (email, credentials) | Until you request account deletion, then deleted within 30 days |
| Subscription/billing history | Up to 7 years for financial compliance (NZ tax law) |
| Approval Workflow PDFs | Auto-deleted 72 hours after upload |
| Send to Client PDFs | Auto-deleted 7 days after upload |
| Device subscription cache | Until refreshed or app uninstalled |

---

## 12. Unique Identifiers (IPP 12)

We do not collect or use government-issued identifiers such as IRD numbers, driver licence numbers, or passport numbers. Your account is identified by your email address and an internally generated user ID.

---

## 13. Enterprise Accounts

If you access InspectPro through a company or team subscription:
- Your account is associated with your company's subscription in our database
- Company administrators may have access to subscription and account membership data
- Inspection data and reports remain under your individual account control unless your organisation's workflow requires otherwise
- If your employment or company relationship ends, contact our Privacy Officer regarding access to data associated with your account

---

## 14. Children's Privacy

InspectPro is designed for professional use and is not intended for use by individuals under 18 years of age. We do not knowingly collect personal information from anyone under 18.

---

## 15. Changes to This Policy

We may update this Privacy Policy from time to time. When we make material changes, we will:
- Post the updated policy in the app
- Update the "Last Updated" date at the top of this document
- Notify you within the app and require re-acceptance of material changes

We encourage you to review this policy periodically. Continued use of the app after notification of changes constitutes acceptance of the updated policy.

---

## 16. Contact — Privacy Officer

If you have questions, concerns, or requests regarding this Privacy Policy or how we handle your personal information, please contact:

**Privacy Officer**
InspectPro / aiconsult.co.nz
**Email:** privacy@aiconsult.co.nz

We aim to respond to all privacy queries within 5 working days and to resolve complaints within 20 working days.

**New Zealand Privacy Commissioner** (if unresolved):
Website: [privacy.org.nz](https://www.privacy.org.nz)
Phone: 0800 803 909

---

*This Privacy Policy was prepared in accordance with the New Zealand Privacy Act 2020 and its 13 Information Privacy Principles. Last reviewed: March 2026.*
