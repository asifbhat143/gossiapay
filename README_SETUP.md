# GossiaPay Starter — Darasgah Gossia Dasilpura

## What this starter does
- Responsive mobile-friendly prototype with the chosen name.
- Demo household register and contribution options ₹200/₹300/₹400/₹500.
- Demo payment recording, ₹6,000/month teacher salary reminder, CSV export.
- Can be hosted as a static web app and installed from a supported mobile browser once hosted over HTTPS.

## What it does NOT do yet
- No secure household/admin login or OTP.
- No cloud database; demo data is saved only in the current browser.
- No real UPI AutoPay mandate, payment debit, bank connection, or payment notifications.
- Do not use this prototype to collect or store real household personal data.

## First deployment: free static hosting
1. Extract this ZIP on a computer.
2. Create a GitHub account if you do not have one, then create a new private or public repository named `gossiapay`.
3. Upload `index.html`, `manifest.json`, and `sw.js` to the repository root.
4. In repository Settings, open Pages, select deploy from branch, choose `main` and `/ (root)`, then save.
5. Once the HTTPS site is live, open it on Android Chrome and use the browser menu → **Install app** or **Add to Home screen**.
6. Test only with fake/demo data.

## Next production steps
1. **Bank/provider check first:** ask the bank and prospective payment provider whether a committee/religious educational institution can collect these contributions and which account/KYC documents are required. Prefer a dedicated committee/institution account; do not assume a personal account is eligible.
2. Choose a provider that explicitly supports UPI AutoPay mandates and recurring collections for this type of organisation. Fees, eligibility and settlement rules vary.
3. Build a secure backend (for example Firebase) with:
   - admin and household roles;
   - phone OTP authentication;
   - household records and monthly dues;
   - immutable payment ledger;
   - audit logs and consent records;
   - server-side payment-provider API calls and verified webhooks.
4. Implement mandate creation only through the provider's approved flow. Every household must review and approve its own mandate. Never collect UPI PINs, OTPs, or banking passwords in this app.
5. Test mandate approval, scheduled debit, success/failure webhooks, cancellation, refunds, reconciliation and access permissions before real launch.
6. Publish privacy notice, support contact and data retention policy.

## Important design decision
The monthly contribution amount is a household-selected amount (₹200/₹300/₹400/₹500). The user must approve the exact mandate amount/frequency in their UPI app. The app should not silently change it.
