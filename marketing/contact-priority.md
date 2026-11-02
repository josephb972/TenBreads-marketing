# Contact routing (prospects.csv)

Each prospect has up to two email routes, both only if published on an official source (never guessed or pattern-built):
- **Named contact** (`email`, `email_status`): the best-fit person, in this order of preference: finance persona (CFO, VP Finance, FD, Financial Controller, AP Manager) > Ops / Supply Chain / F&B Director > other named executive (COO, CEO, MD).
- **Generic inbox** (`generic_email`, `generic_email_source`): a shared business inbox such as info@ or enquiries@. Never pr@, press@, sales@, giftcards@, rewards@ or venue-level addresses.

`contact_priority` (1 = contact first):
1. Named finance persona + published email
2. Named finance persona, no email (LinkedIn note)
3. Named Ops / Supply Chain / F&B persona
4. Named non-finance persona (CEO etc.)
5. No named contact (find Head of Procurement / Financial Controller / Ops Director on LinkedIn)

**Prospector:** if no finance persona is available, pick the next best named person per the order above, and record any published email for them plus any published generic inbox. Set both columns each run.

**Outreach Writer:** one draft per prospect, not two. Named person with a published email goes in To and the generic inbox in Cc; with only a generic inbox, To is the generic inbox and the greeting is "Hello" plus the company name. Eligible when score >= 3 and at least one of `email_status = published` or `generic_email` is set. UK recipients are corporate subscribers (PECR), but every email still carries the identity, address and STOP line.
