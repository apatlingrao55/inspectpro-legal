# InspectPro Privacy Policy

**Version 2.0 — Last Updated: March 2026**

## Introduction

InspectPro ("we", "our", or "us") is committed to protecting your privacy. This Privacy Policy explains how we collect, use, and safeguard your information when you use our mobile application.

## Information We Collect

### Information You Provide
- **Account Information**: Email address and password when you create an account
- **Client Information**: Names, email addresses, phone numbers, and property addresses that you enter for inspection reports
- **Inspection Data**: Photos, notes, comments, and severity ratings you add during inspections
- **Inspector Information**: Your name as it appears on reports

### Automatically Collected Information
- **Device Information**: We may collect device type and operating system version for app compatibility purposes
- **App Usage**: Basic usage data for app compatibility purposes

## How We Store Your Data

### Inspection Data — Local Storage
- Inspection photos, client information, and report data are stored locally on your device
- **We do NOT upload your inspection data to any external servers**
- **We do NOT have access to your inspection content**
- You are responsible for backing up your own data

### Account & Subscription Data — Supabase
- Account credentials (email, encrypted password) are stored securely via **Supabase**, our authentication and database provider
- Company membership and subscription status are stored in Supabase's hosted PostgreSQL database
- Supabase processes data in accordance with their [Privacy Policy](https://supabase.com/privacy)
- Data is encrypted in transit (TLS) and at rest

### Subscription Status — Local Cache
- Your subscription status is cached locally on your device for offline access
- This cache is refreshed when the app connects to the internet

## Third-Party Services

The app uses the following third-party services:

### Supabase (Authentication & Database)
- **Purpose**: User authentication, company membership, and subscription verification
- **Data shared**: Email address, company association
- **Privacy policy**: [supabase.com/privacy](https://supabase.com/privacy)

### Stripe (Payment Processing)
- **Purpose**: Subscription billing and payment processing (via external website)
- **Data shared**: Payment is handled entirely through Stripe's hosted pages; we do not collect or store payment card details
- **Privacy policy**: [stripe.com/privacy](https://stripe.com/privacy)

## How We Use Your Information

Your information is used solely to:
- Create and generate inspection reports (local)
- Store your inspection history on your device (local)
- Authenticate your account (Supabase)
- Verify your company subscription status (Supabase)

## Data Sharing

**We do not sell, rent, or share your personal information with third parties.**

Your data only leaves your device when:
- You explicitly choose to share a PDF report via email, messaging, or other apps
- You sign in to your account (email sent to Supabase for authentication)
- Your subscription status is verified (company membership query sent to Supabase)

## Data Security

We implement appropriate security measures to protect your information:
- Inspection data remains on your device under your device's security protections
- Authentication tokens are encrypted using AES-256 encryption before storage
- Encryption keys are stored in the device's secure enclave (Expo SecureStore)
- All network communication uses HTTPS/TLS encryption

## Your Rights

You have the right to:
- **Access**: View all your data within the app
- **Delete**: Remove any inspection, photo, or client data at any time
- **Export**: Share your data via PDF reports
- **Account Deletion**: Request deletion of your account and associated data by contacting us
- **Uninstall**: Removing the app deletes all locally stored data

## Children's Privacy

InspectPro is not intended for use by children under 13. We do not knowingly collect information from children under 13.

## Changes to This Policy

We may update this Privacy Policy from time to time. We will notify you of any changes by posting the new Privacy Policy in the app, updating the "Last Updated" date, and requiring re-acceptance within the app.

## Data Retention

- **Local data** is retained on your device until you delete individual inspections, uninstall the application, or clear the app's data through device settings
- **Account data** is retained until you request account deletion
- **Subscription data** is retained as long as your company has an active subscription

## California Privacy Rights (CCPA)

California residents have additional rights:
- Right to know what personal information is collected
- Right to delete personal information
- Right to opt-out of sale of personal information (we do not sell your data)

## European Privacy Rights (GDPR)

European users have additional rights under GDPR:
- Right to access your data
- Right to rectification
- Right to erasure
- Right to data portability

Inspection data is stored locally on your device, giving you full control. Account data stored in Supabase can be deleted upon request.

## Contact Us

If you have questions about this Privacy Policy or our privacy practices, please contact us at:

**Email**: dev@aiconsult.co.nz

---

By using InspectPro, you agree to the collection and use of information in accordance with this Privacy Policy.
