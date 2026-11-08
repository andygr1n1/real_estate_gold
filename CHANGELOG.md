# Changelog — filter rules

## 2026-11-08 (evening - Durlești removed)

**Supersedes earlier 2026-11-08 changes.** Durlești removed from search entirely (all property types, all statuses PASS/MAYBE/buffer).

- **R-EXCL-SUBURB**: Durlești now EXCLUDED (no exceptions). Revokes Nov 7 2026 suburb exception and Nov 8 morning homonymous street permission. Durlești was temporarily allowed 2026-11-07 to 2026-11-08 18:28; revoked 2026-11-08 18:28 Europe/Chisinau.
- **R-LOC**: Removed Durlești from acceptable locations. Priority: Centru, Rîșcani, Buiucani within 0–20 min walk of Valea Morilor/Komsomol lake. Acceptable: other Buiucani, Telecentru, Ciocana near Port Mall/Rîșcani edge.
- **R-BLACKLIST-CET1 boundary examples updated**: str. Tudor Vladimirescu and str. Nicolae Dimo in Durlești now EXCLUDED (R-EXCL-SUBURB suburb exclusion). Chișinău Rîșcani same streets remain EXCLUDED (R-BLACKLIST-CET1 CET-1 zone). Unclear locality → MAYBE until resolved; do NOT assume Chișinău.
- **Locality verification unchanged**: must verify locality/address from listing, not bare street name matching.
- **999.md search method updated**: sectors note changed from "ensure Durlești not omitted" to "Chișinău sectors only; suburbs excluded."
- Updated FILTERS.md R-EXCL-SUBURB, R-LOC, R-BLACKLIST-CET1 boundary examples, search method, Russian summary (districts, blacklist, search scope).
- **Historical note preserved**: Durlești temporary allowance 2026-11-07 to 2026-11-08 18:28 documented in changelog and rules (not erased).

All other filters unchanged: 2 price blocks, white €110k cap, elevator informational, year ≥2000, mansards/houses allowed, MAYBE publication with ≤10 separate quota, sources registry, Rîșcani CET-1 zone blacklist, etc.

## 2026-11-08

### MAYBE publication rules (major change)
- **MAYBE candidates now PUBLISHED** with literal tag MAYBE and specific reasons why uncertain (e.g. construction year ≥2000 not confirmed). Previous blanket "MAYBE not published/not buffer" removed consistently.
- **Verdict definitions**: PASS = fully verified; MAYBE = unknown/contradictory criterion but no confirmed mandatory violation; FAIL = confirmed violation, excluded.
- **For each published MAYBE**: include all material unknowns/conflicts, required verification steps; never fabricate facts or upgrade to PASS without verification.
- **R-BANDS quotas clarified**: PASS €40k–110k up to 10; PASS >€110k–140k up to 10; **MAYBE separate status group with own ≤10 quota TOTAL** across both price bands (shown with price band subdivisions as needed). MAYBE does NOT consume PASS quota. Leftovers buffered and published in chunks ≤10 at noon/evening.
- **Examples**: unknown year may now publish as MAYBE with clear note; known pre-2000 remains FAIL (R-YEAR).
- Reporting format updated: present PASS €40k–110k (≤10), PASS >€110k–140k (≤10), then MAYBE (≤10 total) with reasons/verification requirements.
- Updated FILTERS.md §11-12, AGENTS.md reporting format, Russian summary with MAYBE publication rules.

### Locality clarification (R-BLACKLIST-CET1)
- **str. Tudor Vladimirescu and str. Nicolae Dimo locality distinction**: these streets exist in BOTH Chișinău Rîșcani (EXCLUDED as part of CET-1 zone) and Durlești (ALLOWED subject to all other filters).
- Must verify locality/address from listing, not match bare street name. Ambiguous locality → MAYBE until resolved; never guess exemption.
- Boundary examples added: Chișinău Rîșcani Tudor Vladimirescu/Nicolae Dimo EXCLUDED (CET-1 zone); Durlești Tudor Vladimirescu/Nicolae Dimo ALLOWED (e.g. Tudor Vladimirescu 91/6 https://999.md/ro/105401431 — not excluded by street name alone, must satisfy all other filters).
- Fix corrects issue where scan wrongly held 29 Durlești ads due to bare street name matching without locality verification.
- Updated FILTERS.md R-BLACKLIST-CET1, Russian summary, .cursor/rules/real-estate-filters.mdc, templates/listing-check.md, listings/rejected.md (clarified Tudor Vladimirescu 3 is in Chișinău Rîșcani), AGENTS.md (added locality verification to Data honesty).

### Unchanged
All other Nov 7 rules intact: 2 price blocks with exact €110k boundary, white variant €110k cap, elevator informational, construction year ≥2000, mansards/houses allowed with verification, Durlești allowed, sources registry, etc.

## 2026-11-07 (source registry added)

- **SOURCES.md created**: Prioritized, owner-editable registry of real estate listing sources. Six sources listed with verified URLs (2026-11-07): 999.md (primary), Acces Imobil, Pro Imobil, Realist.md, Romanescu, All Invest Realty (AIR). Coverage details to be verified. Capital Imobil not added (domain unreachable).
- Search agent instructions: read SOURCES.md before each run, process enabled sources in priority order, log checked/skipped sources with reasons, deduplicate cross-site listings, continue on transient errors, never weaken filters.
- README.md, AGENTS.md, FILTERS.md updated to reference SOURCES.md.
- Owner can manually add/edit sources by updating SOURCES.md table.
- No filter rule changes; all criteria remain same (2 price blocks, white variant €110k cap, construction ≥2000, elevator informational, etc.).

## 2026-11-07 (evening update)

- **R-BANDS**: Changed from 4 price blocks to **2 price blocks**: €40,000–110,000 inclusive (first block), >€110,000–140,000 inclusive (second block). Exactly €110,000 belongs to the first block. Up to 10 listings per block. Reporting format updated in FILTERS.md and AGENTS.md.

## 2026-11-07

- **White variant price cap** (R-EXCL-UNFINISHED): asking price ≤€110,000 inclusive for white variant (variantă albă); white variant >€110k is FAIL even though general cap is €140k. Applies to apartments and houses, all locations. Uses asking price, not discounted offers.
- **Elevator requirement removed globally** (R-LIFT): lift presence is informational only; high floor (≥4) without lift is flagged but NEVER a hard exclusion in any district including Durlești.
- **Durlești explicitly allowed** (R-EXCL-SUBURB): exception to suburbs exclusion.
- **Priority location update** (R-LOC, R-LAKE added): Centru, Rîșcani, and Buiucani within ≈0–20 minute walk of Komsomol lake / Valea Morilor are priority. Other Buiucani and Telecentru acceptable. Durlești acceptable. Walking time for lake priority measured by actual routes, not straight-line distance. R-LAKE 20-minute priority overrides generic R-MICRO 5–10 minute rule.
- **Mansards now allowed** (R-MANSARD added; removed from R-EXCL-BASEMENT): flag for verification of roof condition, legal registration, cadastral compliance.
- **Single-storey private houses now allowed** (R-HOUSE added; removed from R-EXCL-BASEMENT): explicit exception to R-FLOOR (2–8 requirement) and R-LIFT. Flag for verification of legal status, cadastral registration, land ownership/rights.
- **Building age requirement** (R-YEAR added): construction year ≥2000 (inclusive) required for apartments and houses. Buildings constructed before 2000 excluded. Renovation in old building does not count. Unverified construction year → MAYBE, not PASS. Never invent/guess construction year. Commissioned status still required.
- **R-FLOOR updated**: floors 2–8 for apartments; single-storey houses explicit exception.
- **Search scope expanded**: 999.md search method updated to include house sale categories; ensure Durlești not omitted by sector queries. New parameters to flag: construction year (≥2000), mansard status, house type, roof condition, legal/cadastral registration.
- **Benchmark note added**: Matei Basarab 7/5 marked as historical reference only (35 m² below current R-AREA minimum; likely pre-2000 construction).
- **Cornului 9/3** (https://999.md/ro/105823314) added as user-designated MAYBE (§5a): 2+living, cadastral 93 m², 6/6, €135k (€1,452/m²) or €128k scenario (€1,376/m²). Pending verification: construction year ≥2000, mansard status, roof/legal/cadastral, on-site lift confirmation.
- **Zelinski 20 rejection reason updated**: now R-EXCL-BOTANICA (location) rather than R-LIFT.
- **Pandurilor 14 rejection clarified**: location unclear; previously flagged for no lift (no longer exclusion as of 2026-11-07).

## 2026-11-04

- Blacklist matching now covers Cyrillic / no-diacritic spellings (missed case: ул. Николай Димо 31/1, 999.md/ro/104146622).

## 2026-11-02
- Whole Botanica sector excluded (R-EXCL-BOTANICA); R-LOC/R-LIFT updated; Botanica listings removed from the Telegram buffer.
- CET-1 blacklist extended to the whole str. Nicolae Dimo (R-BLACKLIST-CET1); removed from the Telegram buffer.
- Minimum area 40 m² for all listings (R-AREA) and maximum €1,900/m² (R-PRICE-M2); applied retroactively to the Telegram buffer.
- CET-1 zone blacklisted (R-BLACKLIST-CET1): whole str. Tudor Vladimirescu + ~800 m around Termoelectrica Sursa 1. Tudor Vladimirescu 3 rejected (4 duplicate ads).

## 2026-11-01
- Price range widened to €40–140k (R-BUDGET); above €140k excluded. Reports split into 4 blocks: €40–60k, €60–75k, €75–105k, €105–140k (R-BANDS). Any number of rooms in all blocks (R-TYPE).
- Budget changed to €50–70k (R-BUDGET).
- Elevator rule added (R-LIFT): Botanica/Buiucani/Telecentru without lift only floors 2–3; Centru/Rîșcani forgiven.
- East Rîșcani blacklist added (R-BLACKLIST); 2 Florării 1 rejected. Zelinski 20, Pandurilor 14 rejected (R-LIFT).
- White variant now allowed (R-EXCL-UNFINISHED); grey variant still excluded.
- Promoted 999.md ads are ignored (R-EXCL-PROMO).
- AI-ready repo structure created (FILTERS.md, AGENTS.md, CLAUDE.md, Cursor rule, listings, template).

## 2026-10-31
- Micro-location rule added (R-MICRO). Pajurii 13/1 rejected.

## 2026-10-30
- Initial criteria: studio/1-room, floors 2–8, location priorities, exclusions.
