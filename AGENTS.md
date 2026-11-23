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

Always organize into the single price band from R-BANDS (€80k–159k inclusive). Present in this order:
1. **PASS** (up to 10) — ranked best first
2. **MAYBE** (up to 10 TOTAL) — ranked best potential first

MAYBE has its own independent ≤10 quota; does NOT consume PASS quota. Each section starts with a one-line summary (scanned / PASS count / MAYBE count). Nothing above €159k or below €80k.

### MAYBE publication (added 2026-11-08)
**MAYBE candidates are PUBLISHED** with literal tag **MAYBE** and specific reasons:
- PASS = fully verified
- MAYBE = unknown/contradictory criterion but no confirmed violation; published with reasons
- FAIL = confirmed violation; excluded

For each MAYBE: include all material unknowns/conflicts, required verification, never fabricate facts. Unknown year may publish as MAYBE; known pre-2000 remains FAIL.

### Per listing
**Status PASS/MAYBE** · price block · link · price · m² · €/m² · street + number · floor/total · lift yes/no/unknown · building type/series/year · layout · condition · nearest main road/park/university · risks · fair price + opening offer (based on real comparables per R-PRICE) · verdict with rule IDs.

**For MAYBE:** add specific reasons why MAYBE (e.g. "year unverified — must confirm ≥2000"), required verification, material unknowns.

- **R-ALBA-IULIA**: any listing on str. Alba Iulia (Chișinău) is MAYBE at most, never PASS; always include the note «Алба Юлия — вне основной зоны (Скулянка/Буюканы)». See FILTERS.md R-LOC.
- **R-WHITE** (added 2026-11-23): white variant (variantă albă / белый вариант) listings have additional constraints beyond standard filters: asking ≤€100k, new stock only (commissioned or commissioning by ~31.01.2027), floors 1–10 inclusive (floor 1 allowed for white only), area ≥50 m² (instead of ≥55 m²), location restricted to Centru/near-centre, Komsomol lake/Valea Morilor, near Botanical Garden (~≤1.5 km), bd. Moscova, str. Kiev (elsewhere FAIL, unclear distance MAYBE with map check). Rank white variant closer to centre first. Non-white listings unchanged. See FILTERS.md R-WHITE.

## Empty results handling (added 2026-11-20)

**Morning run (~09:00):** When the daily morning search finds NO fresh eligible PASS or MAYBE listings, post ONE short plain-text Russian message to the Telegram channel stating:
- No new results under current filters
- One-line filter summary (€80–159k, ≥55 m², ≤€2200/m², этаж от 2-го, Центр, Рышкановка (без Старой Почты), Ботаника (без Малой/Большой Малины), озеро Комсомольское + вся ул. Алба Юлия (только MAYBE))
- One-line coverage summary (sources and pages scanned; honest if partial)

Do NOT post this message if the run itself failed (report failure in Grok Bot chat instead). The message adds nothing to posted_ids.

**Buffer runs (12:00/19:00):** Empty buffer => no message (unchanged).
