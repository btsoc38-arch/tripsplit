# TripSplit ✈️

A mobile-first Progressive Web App (PWA) for splitting bills on trips and group gatherings. Built as a single HTML file — no backend, no accounts, no build step. All data stays on your device.

**Live app:** `https://btsoc38-arch.github.io/tripsplit/`

## Features

- **Multiple trips** — each trip keeps its own people, currencies, expenses, and settlement history
- **Flexible splits** — split any expense evenly, by percentage, by portions/shares, or by exact amounts
- **Multi-currency** — pick a main settlement currency and a destination country; log each expense in whichever currency you paid in (60+ world currencies supported)
- **Two settlement modes** — convert everything to the main currency using your own exchange rates, or settle each currency separately with no conversion at all
- **Simplified who-pays-who** — debts are collapsed into the minimum number of payments (if A owes B and C owes A, C just pays B directly)
- **Settle & track** — confirm payments as they happen; settled debts disappear while the trip keeps going, with full settlement history and undo
- **Receipt photos** — snap a photo per expense straight from the camera (auto-compressed, stored in IndexedDB)
- **Expense dates** — every expense is dated and the list sorts newest first
- **Export** — copy a plain-text summary to share in chat, or download a multi-sheet Excel workbook (expenses, per-person shares, balances, outstanding payments, settlement history, exchange rates)

## Install on iPhone

1. Open the live URL in **Safari**
2. Tap **Share** → **Add to Home Screen**
3. The app opens full-screen with its own icon, like a native app

Works on Android too: open in Chrome → menu → **Add to Home screen**.

## How data is stored

- Trip data → browser `localStorage`
- Receipt photos → browser IndexedDB
- Nothing leaves your device; there is no server

⚠️ Clearing your browser's website data will erase the app's data. Use **Export Excel** at the end of each trip as a backup.

Each person who installs the app has their own separate data — nominate one record keeper per trip and share results via the summary or Excel export.

## Tech

- Single-file vanilla HTML/CSS/JavaScript — no framework, no build
- [SheetJS](https://sheetjs.com/) (via CDN) for Excel export
- Greedy debt-simplification algorithm for minimal settlement payments
- Images compressed client-side via Canvas before storage

## Updating the app

Replace `index.html` in this repo with a new version — the same URL and home-screen icon pick up the update on next load.
