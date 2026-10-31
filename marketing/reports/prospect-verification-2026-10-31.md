# Prospect verification — 2026-10-31

Prospector run: re-checked the 15 existing rows in `prospects.csv` against their source pages, looked for finance contacts and published emails on official sources, and added 9 operators (24 rows total).

## Result in one line
No finance-persona email is published on any official source I could reach, so every row stays `email_status = none` and Outreach Writer still has nothing eligible. Finance contacts were found for 5 rows.

## Official general addresses found (NOT entered in the CSV)
These are shared inboxes, not finance contacts. I left them out so Outreach Writer cannot draft a CFO pitch to a generic inbox. Your call whether to use any.

| Company | Address | Where it appears | Why not entered |
|---|---|---|---|
| Upham Inns | info@uphaminns.co.uk | uphaminns.co.uk/contact, labelled Head Office | General inbox; named person is Executive Chairman |
| Hawksmoor | enquiries@hawksmoor.com | hawksmoor.com/contact | General enquiries |
| Bartolotta | info@, pr@, sales@, giftcards@, rewards@ bartolottas.com | bartolottas.com/contact | General; pr@ is the PR agency's media line. Joanne Reardon's page lists no email |
| Union Square Hospitality Group | info@ushg.com, press@ushg.com | ushg.com team and about pages | General/press. The info@ link points to info@ushgnyc.com, so the page is inconsistent |
| Tattu (Permanently Unique) | leeds@, london@, manchester@, birmingham@, edinburgh@ tattu.co.uk | tattu.co.uk/contact | Venue-level inboxes |

No emails were published for Starbird, Burger & Lobster, Comptoir (RNS lists only the LSEG RNS line), Coppa (RNS lists only its PR agency, Alma), Campana, or Clermont. Pages with no email at all: Starbird contact, Burger & Lobster contact.

## Existing 15 rows: what changed
| Company | Outcome |
|---|---|
| Starbird | Verified CFO (NRN, 1 May 2026). Units corrected 20 → 17 (end of 2025). 36-unit Texas deal confirmed. Score stays 5 |
| Hawksmoor | 15 restaurants verified. Boston opening and CFO name (McLauchlan) were not on the page, removed. Score 4 → 3 |
| Bartolotta | Joanne Reardon confirmed on the official team page. Official site says 18 restaurants and catering facilities (was 17). Bunker CFO release is 2022, current status unverified |
| Burger & Lobster | Verified. Page says 11 UK sites; official site lists 10. A third-party site names a Group CFO (Olivier Mougin); not official, so not entered |
| SMR Capital | Verified deal (9 Apr 2026). Named Muhammad Ali Akbar (Managing Partner) and Jason Gilbert (Operating Partner). Open unit count unknown |
| C&M Foods | Verified acquisition (9 Sep 2026). No executives named on page |
| Permanently Unique | Verified £25m facility. Adam Jones (co-founder) named. Unit count still unknown |
| Chestnut | 24 pubs verified (Aug 2025). A later source says 26. Garrath Fulford CFO appears only in search snippets (my fetch of that page was blocked) |
| Upham Inns | Verified 28-unit estate. No finance director on page (a third-party site lists one, not used) |
| B Wild Investments | **Out of range:** says it is on track to operate 70 restaurants. Score 2 → 1, do not pursue |
| Original ChopShop | Verified 28 Sep 2026 CEO change and 30 units. No CFO named |
| Clermont | Verified Andy Goss (17 Nov 2025, 14 hotels). Official site did not resolve from this session |
| Red Door Brands | **Only partly verified.** Source returned 503; a syndicated copy confirms the COO headline (17 Apr 2026) but not the ~20 units, the brand list or the Matadoor Chapter 11 claim. Treat those as unverified |
| Hand Picked Hotels | Source returned 503 and the official contact page 403. Search results support the Feb 2026 hires and 21 hotels. Group CFO exists but is unnamed |
| Craveable | Verified as stale (CFO release dated 26 Jul 2016). Kept at score 1 |

## New rows (9)
Comptoir Group (27 restaurants, finance director handover Oct 2026), Coppa Collective (24, CFO Sharon Badelek, April 2026 acquisitions), Campana (23 Taco Bell UK sites, FD David Morgan), Union Square Hospitality Group (CFO Tiffany Daniele; unit count unverified), Vandelay Hospitality Group (23), Buzzworks (22, Scotland), Harts Group (count unknown), Esperto Hospitality Group (count unknown), PJW Restaurant Group (26 units but a 2021 source, stale).

Three finance contacts are on strong triggers: Comptoir, Coppa and Campana. All three are score 5 but have no email.

## Considered and excluded
- Beckford Group: 7 sites, below the 8-unit floor.
- Firebirds Wood Fired Grill: about 70 restaurants.
- Wingstop UKI (Alistair Fraser, Group FD, Feb 2026): no site count found.
- Gusto: only a 2017 source found.
- Dishoom: no restaurant count or executives on the page fetched.

## Gaps and next steps
- Several finance roles (Hawksmoor, Burger & Lobster, Chestnut, Upham, Hand Picked) could only be confirmed from third-party sites or not at all. A Companies House or LinkedIn check would help, but neither gives an official-source email.
- Fewer than 10 new rows: searches returned few 8-35 unit operators with a dated finance trigger. Targets for the next run: UK pub and hotel groups with Companies House accounts and US multi-concept groups from state business journals.
- Fetch failures: pulse.bot (503, two rows), Chestnut contact page (404), Clermont (host did not resolve), Hand Picked (403), mca-insight (405). If the Clermont domain needs allowing in the session's network settings, the Clermont finance and email check can be redone.
