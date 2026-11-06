# Dockett — Project Brief

Use together with the *Aquila Digital — Mobile & Web App Build Standards*. This brief is the product source of truth; anything not listed under Confirmed is not decided.

## 1. Project overview
Dockett is an application for Aquila Digital LLC. Photograph a receipt and the app reads the store, date and total on the device, reminds you before the return window closes, and keeps the warranty paperwork together.

- **Platform scope:** iOS (assumed: see below).
- **Primary users:** Anyone who buys things and needs to return or claim warranty on them later.
- **Primary user outcome:** When a return or warranty claim comes up, find the receipt in seconds and know the deadline.

## 2. Confirmed requirements
- Standalone app (selected from the 2026-10-14 brainstorm).
- Core loop: photograph receipt → on-device OCR extracts store, date and total → return-window reminder → warranty paperwork kept with the receipt.
- Privacy positioning: receipt data stays on the phone.

## 3. Reasonable assumptions (change freely)
- iOS first, SwiftUI, iOS 17+ (matches the existing Aquila Digital app portfolio).
- Apple Vision / VisionKit for on-device text recognition; no server and no third-party OCR.
- Local storage only; local notifications for reminders; no account.
- OCR output is untrusted: the user confirms or edits every extracted field before it is saved.

## 4. Open questions (decide before building the affected part)
- How is the return window set: typed per receipt, picked from common presets, or both?
- Warranty paperwork: photos only, or PDFs and manuals too?
- Backup and device-to-device sync (iCloud?) vs. strictly local: this changes the privacy claim.
- Export format (PDF / CSV) and whether export is in v1.
- Pricing model (free tier limits, subscription or one-time purchase).
- Retention: keep receipt images forever, or offer auto-delete after the warranty ends?

## 5. Out of scope
- Bank, email or card auto-import.
- Store loyalty or retailer integrations.
- Expense reports and accounting features.

## 6. Project context
| Item | Value |
|---|---|
| Project type | Mobile app |
| Platform | Swift / SwiftUI, iPhone (assumed) |
| Backend | NONE |
| Database | LOCAL (SwiftData or SQLite: to decide) |
| Authentication | NONE |
| Hosting / deployment | App Store |
| Analytics | NONE |
| AI / ML | LOCAL (OCR). No cloud model. |
| Sensitive data classes | DOCUMENTS and FINANCIAL (receipt images, purchase totals). No location, no contacts. |
| Data processing location | ON-DEVICE |

## 7. Documents to keep (per the build standards)
README.md · SECURITY.md · ARCHITECTURE.md · PRIVACY.md · TESTING.md · CHANGELOG.md · .env.example (names only)
