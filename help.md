# SheetLedger – User Guide & Help

[ Auf Deutsch anzeigen 🇩🇪 ](help-de)

---

### ⚡ 1. App Startup & Connection Resilience
* **Startup Synchronization:** SheetLedger syncs your local state with your cloud ledger upon initialization.
* **Google API Quota Limitations:** Google Sheets APIs enforce strict per-minute usage limits worldwide. If your local ledger experiences high-volume batched operations, sync requests might be queued and slightly delayed.
* **Connection Failures:** If a sync or Google Drive authorization fails due to transient network congestion or API rate-limiting, **do not panic**. Your local data is completely safe. Simply wait a few moments and try again.

### 💎 2. Subscription Tiers & Google Sheets Quotas
To prevent a single user from exhausting our global API traffic allocation and to guarantee service stability for everyone, **the maximum number of concurrently linked Google Sheets is restricted based on your subscription tier (Free vs. Premium)**. Please check the in-app **Subscription panel** to view your current linked sheet limits.

### ✈️ 3. True Offline Capability (Local-First)
* **Zero Network Dependency:** SheetLedger is built as a pure local-first application. You can view, add, or edit your financial records anywhere—even on a plane or deep underground with zero connectivity.
* **Auto-Resumption:** Once your device re-establishes a network connection, our internal state machine will automatically resume in the background and safely upload your cached modifications to the cloud.

### ⚠️ 4. Crucial: Do Not Manually Edit the Google Sheets Document
* **Cryptographic & Structural Integrity:** The linked Google Sheets document acts as an encrypted storage backend. SheetLedger enforces strict cryptographic validation and relational schema checks.
* **Data Corruption Risk:** **Never manually insert, delete, or modify rows, cells, or columns directly inside the Google Sheets web/mobile interface.** Manual interference will break the data consistency verification hash, causing the app to flag the ledger as corrupted to protect your financial security. All operations must be performed via the SheetLedger app runtime.

### 👥 5. Multi-Device Synchronization
You can securely log in with your personal Google Account on multiple devices (e.g., your Android phone and tablet) simultaneously. The local-first architecture ensures all devices safely converge on the same ledger state via the cloud.

### 🤝 6. Secure Multi-User Collaboration (Shared Ledgers)
SheetLedger natively supports distributed multiplayer bookkeeping with industry-grade access control:
1. **How to Share:** Simply use the official Google Drive/Sheets interface to share your spreadsheet document with your partners, family members, or business associates via their Google Accounts.
2. **Linking the App:** Have them open SheetLedger on their devices and link to that exact same shared Google Sheet.
3. **Identity-Based Security:** To prevent unauthorized tampering, **all transaction logs are tied to the creator's unique Google Account ID**. While multiple users can view and collaborate within the same shared ledger, our state machine strictly verifies identities—records created by one Google ID cannot be modified or forged by another, ensuring mathematical tamper-proofing.

---
© 2026 gophini. Built for ultimate financial sovereignty.  
Need technical assistance? Reach out to: **gophini.support@gmail.com**
