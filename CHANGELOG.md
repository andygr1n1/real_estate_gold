# Changelog — filter rules

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
