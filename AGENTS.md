# AGENTS.md — instructions for AI agents (Cursor, Codex, Claude, Grok Bot)

## Purpose
This repo holds Andrew Grini's apartment-search rules for Chișinău, Moldova, plus the shortlist and rejected listings. `FILTERS.md` is the **single source of truth** for filter rules. `SOURCES.md` is the **prioritized source registry** for listing sources.

## Mandatory workflow
1. **Always read `FILTERS.md` before evaluating any listing.** Never rely on memory of the rules.
2. **Always read `SOURCES.md` before searching.** Process enabled sources in priority order; log checked/skipped sources with reasons.
3. Evaluate every listing against **every** rule (use `templates/listing-check.md`).
4. Output a verdict **PASS / MAYBE / FAIL** and cite the specific rule IDs (e.g. `FAIL: R-FLOOR, R-BLACKLIST`).
5. Check `listings/rejected.md` first — never re-propose a rejected listing.
6. Ignore promoted/boosted 999.md ads (R-EXCL-PROMO). Deduplicate the same flat across agencies and across sources.

## Data honesty
- Never invent numbers. Every figure must come from a listing or comparable you actually opened.
- Label estimates explicitly (e.g. "estimate: deals close 5–10% below asking").
- Unknown fields stay unknown/blank — do not guess (except R-LIFT: unknown lift in ≤5 floors = no lift).
- **Verify locality/address from listing text**, not just street name. Same street names exist in multiple localities (e.g. Tudor Vladimirescu in Chișinău Rîșcani, in Durlești, etc.). Ambiguous locality → MAYBE until resolved; do NOT assume Chișinău; never guess exemption.

## Language
Reply to Andrew in **Russian**. Repo files are in English.

## When Andrew gives a new rule or rejects a listing — same change:
- Update the rule in `FILTERS.md` (with a stable rule ID and the date).
- Add rejected listings to both `FILTERS.md` §5 and `listings/rejected.md` (address, link, reason with rule ID, date).
- User-designated MAYBE listings go to `FILTERS.md` §5a and `listings/shortlist.md` with clear verification requirements.
- Add a dated entry to `CHANGELOG.md`.
- Keep `listings/shortlist.md` in sync (move rejected items out, update statuses).

## Reporting format

Always organize into the 2 price blocks from R-BANDS (€40k–110k inclusive, >€110k–140k inclusive). Present in this order:
1. **PASS €40k–110k** (up to 10) — ranked best first
2. **PASS >€110k–140k** (up to 10) — ranked best first
3. **MAYBE across both bands** (up to 10 TOTAL) — shown with price band subdivisions as needed; ranked best potential first

MAYBE has its own independent ≤10 quota; does NOT consume PASS quota. Each section starts with a one-line summary (scanned / PASS count / MAYBE count). Nothing above €140k.

### MAYBE publication (added 2026-11-08)
**MAYBE candidates are PUBLISHED** with literal tag **MAYBE** and specific reasons:
- PASS = fully verified
- MAYBE = unknown/contradictory criterion but no confirmed violation; published with reasons
- FAIL = confirmed violation; excluded

For each MAYBE: include all material unknowns/conflicts, required verification, never fabricate facts. Unknown year may publish as MAYBE; known pre-2000 remains FAIL.

### Per listing
**Status PASS/MAYBE** · price block · link · price · m² · €/m² · street + number · floor/total · lift yes/no/unknown · building type/series/year · layout · condition · nearest main road/park/university · risks · fair price + opening offer · comparison with benchmark (Matei Basarab 7/5) · verdict with rule IDs.

**For MAYBE:** add specific reasons why MAYBE (e.g. "year unverified — must confirm ≥2000"), required verification, material unknowns.
