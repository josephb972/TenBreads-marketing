# Marketing config

Single source of truth for agent settings. Agents must read this first.

| Setting | Value |
|---|---|
| Sending domain | `elevatia.dev` (interim; swap when a Tenbreads domain is ready) |
| Sender name | Joseph at Tenbreads |
| Sender address | tenbreads@elevatia.dev |
| Reply-to | tenbreads@elevatia.dev |
| Physical mailing address (required in every email footer) | 119B Kenton Road, Harrow, HA3 0AZ, United Kingdom |
| Unsubscribe line | "Reply STOP and I won't email you again." |
| Daily draft cap | 15 |
| Auto-send | ON for outreach touches 1-3 (owner approved 2026-11-21). Replies to prospects stay Gmail drafts. |
| Daily send cap | 15 (same as the draft cap) |
| Public posting | OFF (drafts only) |
| Regions | US and UK from day one (review UK drafts for £ and PECR) |
| Currencies | $, £, € (match the prospect's region) |

## Hard rules for every agent
1. If any `TODO` above is unresolved, the Outreach Writer must not create drafts; it records the blocker in the digest instead.
2. Brand is **Tenbreads** (monogram TB). Never write the former name. Domain `elevatia.dev` is only the mail/hosting domain; the brand in copy is Tenbreads.
3. Never invent contacts, emails, customers, testimonials or results. Illustrative numbers from `icp.md` must be labeled "illustrative example".
4. Never post or spend. Outreach touches 1-3 may be sent automatically, only after brand-guard PASS, and never to an address in suppression.csv or to a prospect who has replied. Replies to prospects are drafts only.
5. Commit and push your outputs before finishing; the container is ephemeral.

## Mail account
Agents use the Gmail account `tenbreads@elevatia.dev` (connector must be connected to this account, not a personal one). Verify with the Gmail profile before creating drafts; if the connected account differs, write the blocker to `marketing/drafts/BLOCKED.md` and stop.
