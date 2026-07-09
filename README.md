# Real Estate Investment Platform

A single-file, self-contained web app for screening and tracking Southern California rental real estate. Cash-flow first: negative leverage (cap rate below debt cost) is treated as disqualifying, and every rent figure is an estimate until verified against current market comps.

Built to publish to a public URL (GitHub Pages) and share with partners.

## Tabs

- **Analyze** — underwrite a new acquisition (up to 6 units + ADU), grade it 1-10, and see the deal solver and break-even gauge.
- **Portfolio** — track owned properties: purchase data, financing, rents, PITI (editable to match your mortgage statement), NOI, cash flow, cap rate, CoC, DSCR, equity, and loan paydown, with portfolio-level KPIs and multiple portfolios.
- **Deal Log** — history of screened deals with verdicts; push whatever is open in Analyze straight in.
- **Compare** — side-by-side comparison of saved deals.
- **Comps** — neighborhood rent-comp tracker to verify assumptions.
- **Settings** — editable underwriting defaults, plus JSON backup/restore and CSV export.

## Data & privacy

All data is stored **locally in your browser** (localStorage). Publishing the site shares the *tool*, not your data — each visitor sees an empty app. To move your data between devices or hand a partner a copy, use **Settings → Backup all (JSON)** and **Restore**. Per-tab **Export CSV** is available on the Portfolio, Deal Log, and Comps tabs.

## Underwriting defaults (editable in Settings)

| Input | Default |
|---|---|
| Down payment | 50% |
| Interest rate | 7.37% |
| Loan term | 30 yrs |
| Vacancy | 5% |
| Property tax | 1.2% |
| Insurance | $1,500/yr |
| Property management | 0% (self-managed) |
| Maintenance | 1% of price/yr |
| Closing costs | 2.5% |

## Deploy to GitHub Pages

1. Create a new GitHub repository (e.g. `re-platform`).
2. Upload the contents of this folder (`index.html`, `vi.html`, `README.md`) to the repo root.
3. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, pick `main` and `/ (root)`, Save.
4. Your app goes live at `https://<your-username>.github.io/re-platform/` within a minute or two.
5. `index.html` is the whole app. It is **bilingual** — a Tiếng Việt / EN button in the tab bar toggles the entire UI between English and Vietnamese (your choice is remembered). The old `vi.html` is no longer needed.

No build step, no dependencies, works offline once loaded.

## Status

- **Milestone 1 (done):** combined 5-tab shell, analyzer preserved as-is, native Portfolio tab, Deal Log (seeded), Comps, Settings, JSON/CSV export-import.
- **Milestone 2a (done):** portfolio Detail view (specs, tenants, documents with cloud-URL + local-folder modes), and inline SVG charts (revenue vs expenses, cash flow).
- **Milestone 2b (done):** built-in English/Vietnamese language toggle (one bilingual file, 194 mapped terms).
- **Next:** optional number-font refinement and final polish.

## Disclaimer

Screening aid only. Not financial, tax, or investment advice. Verify all figures independently.

## Changelog

### v1.2 — Jul 2026
- New **REPS Hours Log** tab for Real Estate Professional Status tracking: color-coded live counter toward 750 hours **per tax year**, category breakdown, Excel/Google-Sheets **CSV export**, and a per-row **stopwatch** (press Time on an entry to clock it live).
- Entries capture Date, Category (Rental Operations, Acquisition, Leasing & Tenant Placement, Development, Construction), Activity notes, **Property** tag, and Hours:Minutes. Add/remove custom property names right on the tab.
- **Analyze grade** now uses banded scoring scales for Cash flow and Debt Safety (DSCR).
- REPS data included in JSON backup.

### v1.1 — Jul 2026
- New **Team** tab: A-List key contacts (realtors/wholesalers, GCs, lenders, PMs, architects) with region coverage, plus region-based **Contractors** (plumber, electrician, handyman, flooring, cabinet, roofing, windows, painter). Regions are editable (LA + OC to start).
- New **Margin Deal Calculator** tab (Springboard to Wealth / Thach Nguyen framework, LA/OC-adjusted): color-coded strategy — Pass < 10%, Wholesale 10–15%, Fix & Flip 15–20%, Buy & Hold/BRRR 20%+; pull-from-Analyze, 70% rule max offer, log to Deal Log.
- **Dark mode** toggle (top of the tab bar), remembered per browser.
- Portfolio: **editable PITI** (manual override), **current equity** in Loan Life & Progress, added **rental income** and **operating expenses** columns, removed CoC column, full-word labels, and polished, centered, symmetrical tables with a paydown progress bar.
- Numerals set in tabular-sans for clean column alignment.

### v1.0 — Jul 2026
- Initial combined platform: **Analyze** (deal underwriting + grade), **Portfolio** tracker (per-property editor, tenants, documents, charts), **Deal Log**, **Compare**, **Comps**, **Settings** (editable underwriting defaults, JSON backup/restore, CSV export).
- Bilingual **English / Tiếng Việt** toggle. Self-contained single file, GitHub Pages ready.
