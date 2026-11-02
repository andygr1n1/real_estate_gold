# Changelog — filter rules

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
