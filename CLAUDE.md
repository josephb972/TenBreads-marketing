# Tenbreads — Project Context

Persistent context for Claude Code sessions. Read this before making product, copy, pricing, or branding decisions.

## Identity
- **Name:** Tenbreads (formerly **Tenmils** — the rebrand is complete; never reintroduce "Tenmils" in user-facing copy, metadata, or logs)
- **Tagline:** Automated B2B Foodservice Invoice Auditor & Recovery Engine
- **Monogram:** TB
- **Core value prop:** Cross-references every food & beverage delivery invoice line-by-line against a restaurant group's contracted price agreements, catches distributor margin creep and uncontracted substitutions, drafts credit claim packets, and tracks credits until they hit the bank.
- **Operator one-liner:** "You pay 150 distributor invoices a week across 5–100 locations. We catch the $0.18/lb price drift, substituted SKUs, and bogus drop fees your AP team doesn't have 40 hours a week to find — and we get your money back."

## Ideal Customer Profile
- **Who:** Multi-unit hospitality operators, restaurant groups, franchise collectives, gastropub operators, boutique hotel F&B groups.
- **Footprint:** 5 to 100+ locations; sweet spot **8–35 units**.
- **Not 1-unit independents:** too little invoice volume, no master purchasing contract.
- **Not 1,000+ unit chains (McDonald's, Darden):** they have in-house AP audit teams and custom EDI pipelines.
- **Distributors audited**
  - US: Sysco, US Foods, Performance Food Group (PFG), Gordon Food Service (GFS), Cheney Brothers
  - UK: Brakes, Bidfood, Reynolds, Direct Seafoods, Booker

### Buyer personas
| Persona | What they care about |
|---|---|
| CFO / VP Finance | Prime margin preservation. Restaurant net margins are 3–7%, so recovered overcharges (~$80k/yr for a 12-unit group) drop straight to the bottom line. |
| Ops Director / Head of Supply Chain | Signs vendor price master contracts; hates reps quietly moving margins. |
| Executive Chef / F&B Director | Approves substitutions on the dock without seeing the billed markup. |
| AP & Finance Managers | Buried under 150+ PDFs/scans a week; no time to verify line pricing. |

## Problems solved
1. **Contract price creep** — e.g. chicken breast contracted at $3.80/lb drifts to $3.94, then $4.15.
2. **Unauthorized SKU substitution** — out-of-stock item swapped for an alternative billed at spot price ($41.80/cs vs $32.50 contracted) despite price protection.
3. **Ghost surcharges & split-case adders** — fuel/drop fees ($45/drop), pallet fees, split-case fees despite "all-in delivered pricing".
4. **Catch-weight discrepancies** — meat, seafood, cheese billed at gross container weight instead of net delivered weight.
5. **Missing promised credits** — driver's handwritten credit memo never appears on the monthly vendor statement.

## How it works (4-step workflow)
```
[Distributor Invoices] ──┐
                         ├──► [Tenbreads Engine] ──► [Dispute Claim Packet] ──► [Distributor Credit]
[Contract Price Matrix] ──┘     (3-way line match)      (one-click email)         (reconciled & billed)
```
1. **Ingestion & baseline:** operator uploads signed contract / master price schedule once per renewal cycle. Invoices arrive via email forwarding, PDF upload, or EDI/folder sync.
2. **3-way line-by-line match:** extract item codes, pack sizes, UOM, delivered weights, billed unit rates; compare against contract rates, allowed-substitution rules, and approved freight/fuel adders.
3. **Dispute claim generation:** audit report with exact variance (e.g. *Line 4: billed $12.50/lb vs contract $10.84/lb = $74.70 variance*) plus a formal Dispute Claim Memo to the distributor's Claims & Order Desk citing contract clause §4.2, invoice number, and credit owed.
4. **Credit reconciliation:** claim status pipeline **Drafted → Dispatched → Vendor Acknowledged → Credit Note Issued & Reconciled**.

## Business model
| Track | Model | Details |
|---|---|---|
| A | **Free 90-day lookback audit** (hook) | Free historical audit of 90 days of invoices for one distributor account. Shows concrete recoverable dollars (e.g. $4,500) on the prospect's own invoices to remove CFO skepticism. Then they choose Contingency or SaaS. |
| B | **Contingency — 25% success fee** | 25% of credits actually booked by the distributor. $0 out of pocket (e.g. $10,000 found → client keeps $7,500, Tenbreads earns $2,500). |
| C | **SaaS retainer** | Flat monthly, continuous auditing. 5–15 units: **$500/mo**. 16–40 units: **$950/mo**. 40+ units: custom quote by invoice volume. Pitch: at $15k/mo overcharges, 25% = $3,750/mo vs $500 flat. |
| D | **Hybrid (recommended standard)** | ~**$299/mo** base + **12–15%** contingency on recovered cash. Recurring revenue covers infra; upside on big catches. |

**Contingency payment safeguards** (anti-circumvention):
- Operator's card is authorized on file via **Stripe** when a claim packet is generated.
- The 25% fee is finalized when the distributor issues the credit memo or applies credit to the statement.
- Claim packets carry **digital tracking codes** matched against incoming distributor credit notes / monthly vendor statements to detect offline settlement.

## Unit economics (12-unit group, Sysco account)
| Metric | Value |
|---|---|
| Weekly spend / location | ~$7,500 (≈$90,000/week across group) |
| Annual food purchasing | ~$4.68M |
| Avg industry leakage rate | 1.8% of invoice total |
| Annual margin leakage | $84,240 |
| SaaS cost ($500/mo) | $6,000/yr |
| Net operator savings | $78,240 |
| ROI | ~14.0x (gross recovery ÷ cost; net-of-cost ratio is ~13.0x) |

## Global applicability
Same mechanics worldwide: US contracted line matrices (Sysco, US Foods, PFG) and UK nominated supply agreements (Brakes, Bidfood, Reynolds, Booker). UK pain points are identical — signed-in-grease delivery notes, weekly price file changes, unapplied credit notes. The product supports multi-currency (**$, £, €**) and localized claim formatting.

## Engineering state
- **Backend:** Cloud Firestore. Dedicated database `ai-studio-tenmils-c4bf1bcd-9d1d-4f33-8c6a-64f1e56ae5ed` provisioned (Firebase ToS verified via `GetFirebaseTos`); `firestore.rules` deployed via RPC. (The database ID retains the legacy "tenmils" slug — it is an immutable resource ID, not a branding leftover.)
- **Rebrand to Tenbreads (done):** branding, schema.org definitions, metadata tags, logos, TB monograms, footers, modals, server logs, and Launch HQ references.
- **UI — Section 2:** replaced the heavy pill button with clean inline text navigation ("How the audit works →"). Keep this style for similar secondary links.
- **Repo status:** this repository currently holds project context only; the application code (built in AI Studio) has not been imported yet.

## Conventions for Claude
- Use "Tenbreads" everywhere; monogram "TB".
- Keep copy operator-facing and dollar-concrete (cents/lb, $/case, $/drop); avoid generic "AI" fluff.
- Money handling: support $, £, €; never hard-code USD.
- Never commit secrets (Stripe keys, Firebase service accounts, `.env`).
- Standing owner preference: do everything possible autonomously. When the owner must choose, ask with a multiple-choice question (AskUserQuestion). When a task needs the owner and cannot be done by Claude, give a clear step-by-step guide.
