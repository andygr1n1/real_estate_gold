# FILTERS.md — Chișinău apartment search rules (single source of truth)

Owner: Andrew Grini · Last updated: 2026-11-23 17:04

Every listing must be checked against **every** rule below. Verdicts cite rule IDs.
Verdict scale:
- **PASS** (all hard rules met, fully verified)
- **MAYBE** (unknown/contradictory criterion but no confirmed mandatory violation; published with specific reasons why uncertain)
- **FAIL** (any hard rule confirmed violated; excluded from publication)

---

## 1. Budget & type

- **R-BUDGET** (updated 2026-11-23) — Asking price **€80,000–159,000 inclusive**. Anything above €159k or below €80k is excluded immediately. **White variant (variantă albă)** listings have additional constraints under R-WHITE (price cap €100k, new stock only, floors 1–10, area ≥50 m², location restrictions).
- **R-BANDS** (updated 2026-11-21) — Every report uses **ONE single price band**: **€80,000–159,000 inclusive**.
  
  **Quotas per batch** (updated 2026-11-18):
  - **PASS**: up to 10 listings
  - **MAYBE (separate status group)**: up to 10 listings TOTAL
  
  MAYBE has its own independent ≤10 quota; MAYBE does NOT consume PASS quota. Leftovers buffered and published in chunks ≤10 at noon/evening. Each section starts with a one-line summary: listings scanned, PASS count, MAYBE count. Rank PASS first (best first), then MAYBE (best potential first). Empty → say "нет подходящих".
  
  **Historical note:** Was €40,000–140,000 with 2 price blocks (€40k–110k, >€110k–140k) until 2026-11-18; superseded by single band €80,000–160,000 (2026-11-18), then €80,000–100,000 (2026-11-19), then €80,000–120,000 (2026-11-20), then €80,000–159,000 (2026-11-21 20:21).
- **R-TYPE** (updated 2026-11-01) — Any number of rooms in all price blocks (studio, 1, 2, 3+ rooms). Always state the room count.
- **R-LAYOUT** — Logical layout: own kitchen, own bathroom, hallway, no walk-through rooms.
- **R-AREA** (updated 2026-11-20) — Total area **≥ 55 m²** for every listing, any room count. Anything below 55 m² is **FAIL** immediately. Unknown area → verdict **MAYBE** with area verification required. (Note: was ≥40 m² until 2026-11-08 18:32, then ≥45 m² until 2026-11-20 00:46; superseded by ≥55 m².)
- **R-PRICE-M2** (updated 2026-11-20) — Asking price per m² **≤ €2,200/m²** (price ÷ total area). Anything above €2,200/m² is excluded immediately. (Note: was ≤€1,900/m² until 2026-11-18, then ≤€2,100/m² until 2026-11-20; superseded by ≤€2,200/m².)

## 2. Floors & elevator

- **R-FLOOR** (updated 2026-11-21) — For **apartments**: floor **≥2** (second floor and above). Never ground floor (floor 1). No upper floor limit. For **single-storey houses**: explicit exception to the floor ≥2 requirement.
- **R-LIFT** (updated 2026-11-07):
  - Lift presence (yes/no/unknown) is **informational only**.
  - High floor (≥4) without a lift is **flagged** as a practical concern, but **NEVER a hard exclusion**.
  - Unknown lift in a building of ≤5 floors = **no lift** (for flagging purposes).
- **R-TOPFLOOR** — Top floor is always flagged (roof risk).

## 3. Always excluded

- **R-EXCL-HOSTEL** — Hostel units (cămin / gostinka / shared kitchen or bath).
- **R-EXCL-BASEMENT** — Soclu, demisol, semi-basement, "pe sol".
- **R-EXCL-UNFINISHED / R-WHITE** (updated 2026-11-23) — **Grey variant** (no finishing at all) is excluded. **White variant (variantă albă / белый вариант)** is ALLOWED with the following mandatory constraints (R-WHITE):
  
  - **R-WHITE-PRICE** (2026-11-23): Asking price **≤€100,000 inclusive** (general €80k minimum unchanged). White variant asking >€100k is **FAIL**, even though the general budget cap is €159,000. Uses asking price (not hypothetical discounted offers).
  
  - **R-WHITE-NEW** (2026-11-23): **New stock only**. Building must be commissioned OR have evidence of commissioning within approximately 2 months (by ~31 January 2027). Known later commissioning date → **FAIL**. Uncommissioned with unknown date → **MAYBE** with commissioning verification required.
  
  - **R-WHITE-FLOOR** (2026-11-23): Floors **1–10 inclusive**. Floor 1 (ground floor) is ALLOWED for white variant only (exception to general R-FLOOR ≥2 rule). Floor >10 → **FAIL**. Soclu/demisol/pe sol (semi-basement) → **FAIL** (R-EXCL-BASEMENT).
  
  - **R-WHITE-AREA** (2026-11-23): Total area **≥50 m²** (instead of general ≥55 m² rule). Known <50 m² → **FAIL**. Unknown area → **MAYBE** with area verification required.
  
  - **R-WHITE-LOC** (2026-11-23): **Location restrictions for white variant**. ONLY the following locations are acceptable for white variant:
    - **Centru / near-centre**
    - **Komsomol lake / Valea Morilor area** (R-LAKE ~0–20 min walk)
    - **Near Botanical Garden** (Grădina Botanică, approximately ≤1.5 km)
    - **bd. Moscova**
    - **str. Kiev**
    
    White variant elsewhere → **FAIL**. Unclear distance to allowed zones → **MAYBE** with map check required. Rank white variant listings closer to centre first.
  
  - **Other rules still apply**: R-BLACKLIST (all streets/areas/buildings), R-PRICE-M2 (≤€2,200/m²), no grey variant, R-YEAR (≥2000 AND commissioned, old housing stock excluded), etc.
  
  - **Unknown finish rule** (added 2026-11-17, updated 2026-11-23): If finishing is not explicitly stated, finish type is UNKNOWN → verdict **MAYBE** with verification requirement «уточнить отделку: белый вариант >€100k или вне зоны = FAIL», not FAIL. Only an explicitly stated white variant violating R-WHITE is FAIL.
  
  - **Non-white listings** (ready/finished apartments) are unchanged: €80k–159k, ≥55 m², floor ≥2 (no floor 1), all R-LOC locations allowed, etc.
  
  - For white variant, add an estimated renovation budget (label it as an estimate).
  
  - **Historical note**: White variant cap was €110,000 from 2026-11-07 to 2026-11-08 18:32; superseded by €90,000 cap 2026-11-08 18:32; superseded by comprehensive R-WHITE rules (€100k cap, new stock only, floors 1–10, area ≥50 m², location restrictions) 2026-11-23 17:04.
- **R-EXCL-NEWBUILD** — New builds not yet commissioned.
- **R-EXCL-SUBURB** (updated 2026-11-08) — Suburbs (Durlești, Codru, Stăuceni, Ialoveni, Sîngera, etc.) are excluded. **No exceptions.** (Note: Durlești was temporarily allowed 2026-11-07 to 2026-11-08; revoked 2026-11-08 18:28.)
- **R-EXCL-PROMO** — Promoted/boosted ads on 999.md are ignored (not counted in results).

## 3a. Building age & special property types

- **R-YEAR / R-EXCL-OLD-STOCK** (updated 2026-11-22) — **OLD HOUSING STOCK EXCLUDED ENTIRELY.** Only buildings constructed in **2000 or later (≥2000)** AND commissioned are eligible for both apartments and houses. Any building constructed before 2000 is **FAIL** immediately. Any Soviet-era or typical series building is **FAIL** immediately. Renovation in an old building does NOT count. Unverified construction year with no old-stock indication → verdict **MAYBE** (must verify ≥2000), never PASS. Never invent or guess a construction year. Flag building-age checks. Commissioned status required (R-EXCL-NEWBUILD).
  
  **Pre-2000 series exception REVOKED (2026-11-22 20:52):** Exception for Stalinka, seria 102 (cotileț), seria 143, Czech series/project, and individual projects was **superseded and revoked** as of 2026-11-22 20:52. These building types are now **FAIL** (old housing stock excluded).
  
  **Historical note:** Buildings ≥2000 have always been required. Exception for pre-2000 series was added 2026-11-15 (Stalinka, seria 102), extended 2026-11-18 23:18 (seria 143, Czech series, individual projects), then **revoked entirely 2026-11-22 20:52** — all pre-2000 buildings now excluded without exception.
- **R-MANSARD** (added 2026-11-07) — **Mansards are now ALLOWED**. Flag for verification: roof condition, legal registration, cadastral compliance.
- **R-HOUSE** (added 2026-11-07) — **Single-storey private houses are now ALLOWED**. Explicit exception to R-FLOOR (floor ≥2 requirement) and R-LIFT. Flag for verification: legal status, cadastral registration, land ownership/rights.

## 4. Location

- **R-LOC** (updated 2026-11-21) — **ONLY** the following locations are acceptable:
  - **Centru** (whole sector)
  - **Rîșcani / Рышкановка (whole sector)** EXCEPT **Poșta Veche**, which remains excluded
  - **Buiucani area around Komsomol lake / Valea Morilor** — approximately 0–20 minute actual walking route, including adjacent parts of Buiucani (R-LAKE)
  - **Whole Botanica sector** (added 2026-11-21 23:06) EXCEPT **Malaia Malina and Bolșaia Malina** (micro-districts and streets), **str. Sarmizegetusa** (whole street, all house numbers), and **str. Nicolae Titulescu** (whole street, all house numbers), which are blacklisted (R-BLACKLIST). All other Botanica locations evaluated by standard filters; PASS possible.
  - **Whole str. Alba Iulia, Chișinău** (added 2026-11-21 20:21) — every building on str. Alba Iulia in Chișinău (Buiucani/Sculeanca included) is location-OK regardless of distance from the lake (R-ALBA-IULIA). **Alba Iulia listings are ALWAYS MAYBE at best, never PASS**, and are published with the literal note «Алба Юлия — вне основной зоны (Скулянка/Буюканы)». Other R-* rules still apply (a confirmed violation is still FAIL). Alba Iulia streets in suburbs/other localities remain excluded (R-EXCL-SUBURB).
  
  **Everything else is EXCLUDED**, including:
  - **Poșta Veche** (part of Rîșcani sector but specifically excluded)
  - Other parts of Buiucani (outside the ~0–20 min lake area)
  - **Telecentru** (previously acceptable; excluded as of 2026-11-18)
  - **All Ciocana** (including former Port Mall/Rîșcani edge exception, revoked 2026-11-12)
  - All suburbs (Durlești, Codru, Stăuceni, Ialoveni, Sîngera, etc.) (R-EXCL-SUBURB)
  
  Unclear micro-district (e.g. only 'Rîșcani' without street/map) → verdict **MAYBE** with map check until resolved.
  
  **Historical note:** Telecentru, other Buiucani, and Ciocana near Port Mall were acceptable until 2026-11-18; whole Rîșcani sector was acceptable until 2026-11-19, then restricted to Rîșcanovca neighbourhood only (2026-11-19), then expanded to whole Rîșcani sector except Poșta Veche (2026-11-20).
- **R-LAKE** (added 2026-11-07) — Buiucani within ≈0–20 minute walk of Komsomol lake / Valea Morilor has **priority** status. Walking time is measured by actual routes, not straight-line distance. This explicit 20-minute lake priority overrides the generic 5–10 minute R-MICRO rule for these areas.
- **R-EXCL-BOTANICA** (superseded 2026-11-21 23:06) — **Botanica sector is now ALLOWED** (added to R-LOC 2026-11-21 23:06), except Malaia Malina and Bolșaia Malina micro-districts/streets (blacklisted R-BLACKLIST). All other Botanica locations evaluated by standard filters; PASS possible. Historical note: whole Botanica was excluded 2026-11-02 to 2026-11-21 23:06.
  - **Poșta Veche** excluded (part of Rîșcani sector but specifically excluded in R-LOC).
  - **Ciocana** excluded entirely as of 2026-11-18.
  - Verify the real address from the listing text, not just the sector field.
- **R-MICRO** — Within ≈5–10 min walk of:
  - a main road/boulevard (bd. Moscova, Alecu Russo, Kiev, Ștefan cel Mare, Dacia, Decebal, Ion Creangă, Calea Ieșilor, Mircea cel Bătrân, etc.), or
  - a park (Valea Morilor, Râșcani / La Izvor, Central Park, Valea Trandafirilor, Dendrarium, Lacul Dimo), or
  - a university (USM, UTM, ASEM, USMF, Pedagogical University).
  - Remote inner-block / outskirt streets are excluded.
  - Note: The explicit R-LAKE 20-minute priority for Buiucani near Valea Morilor / Komsomol lake takes precedence over this generic 5–10 minute rule.
- **R-BLACKLIST / R-BLACKLIST-BUILDING** (updated 2026-11-22) — The following streets, areas, and buildings are excluded entirely (all apartments and houses, all statuses including buffer):
  
  **Streets:**
  - **str. Drumul Viilor** (added 2026-11-13)
  - **str. Valea Dicescu** (added 2026-11-15)
  - **str. Calea Ieșilor** (added 2026-11-15)
  - **str. Grădinilor** (added 2026-11-15)
  - **str. Pajurii** (Chișinău, Rîșcani; all house numbers, apartments and houses; variants Pajurii/Păjurii/Пажурий) (added 2026-11-21 21:00)
  - **str. Ceucari** (Chișinău, Rîșcani; all house numbers, apartments and houses; variants Ceucari/Чеукарь) (added 2026-11-21 21:09)
  - **str. Braniștii** (Chișinău, Rîșcani; all house numbers, apartments and houses; variants Braniștii/Branistii/Брэништий/Браништий) (added 2026-11-21 21:09)
  - **bd./str. Gagarin** (Chișinău, Centru; all house numbers, apartments and houses; variants Iuri Gagarin/Gagarin/Гагарина) (added 2026-11-21 21:21)
  - **str. Tudor Vladimirescu** (Chișinău, Rîșcani; all house numbers, apartments and houses; variants Тудор Владимиреску) (added 2026-11-21 21:21; re-blacklisted, was removed 2026-11-19)
  - **șos. Muncești** (Chișinău; all house numbers, apartments and houses; variants Мунчешть/Muncesti/Munceşti) (added 2026-11-22 19:46)
  - **str. Sarmizegetusa** (Chișinău, Botanica; all house numbers, apartments and houses; variants Сармизеджетуса/Сармизегетуса/Sarmisegetusa) (added 2026-11-23 09:50)
  - **str. Nicolae Titulescu** (Chișinău, Botanica; all house numbers, apartments and houses; variants Николае Титулеску/N. Titulescu) (added 2026-11-23 09:53)
  
  **Areas:**
  - **Malaia Malina / Bolșaia Malina** (Chișinău, Botanica; whole micro-districts and streets named after them, apartments and houses; variants Малая Малина/Большая Малина/Malina Mică/Malina Mare) (added 2026-11-21 23:06). Unclear address → MAYBE with map check.
  
  **Buildings:**
  - **bd. Dacia 59** (Chișinău, Botanica; complex Edera Home; any apartment in this building, all statuses) (added 2026-11-22 21:30). Only this building number; other bd. Dacia numbers evaluated normally. Dacia 59/x that names Edera Home → FAIL; unclear → MAYBE with check.
  
  **Historical note:** East Rîșcani pocket (str. Florării, str-la Florării, str. Pajurii, str. Forăriei, str. Zimbrului) was excluded from 2026-11-01 to 2026-11-20; removed from blacklist 2026-11-20 (now evaluated by standard filters). str. Pajurii re-blacklisted 2026-11-21 21:00. str. Tudor Vladimirescu was in CET-1 zone blacklist 2026-11-02 to 2026-11-19, removed 2026-11-19, re-blacklisted 2026-11-21 21:21.
- **R-CET1-INFO** (updated 2026-11-21) — CET-1 (Termoelectrica Sursa 1) proximity **is informational only** and NOT an exclusion. All addresses previously excluded under the CET-1 zone rule are now evaluated by standard filters. Proximity to CET-1 (≈47.0331, 28.8635) should be flagged as "близко к ТЭЦ-1" for informational purposes. Reasons for CET-1 concern: plant can burn fuel oil (păcură), gas filters reported non-compliant (UTM study), planned ~250 MW new plant construction on site, weak liquidity.
  - **Locality clarification**: str. Tudor Vladimirescu and str. Nicolae Dimo exist in multiple localities. **Must verify locality/address from listing, not match bare street name.** Unclear locality → verdict MAYBE until resolved; do NOT assume Chișinău.
  - **All addresses now evaluated by standard filters**: str. Nicolae Dimo (Chișinău Rîșcani) and all addresses within ~800 m of CET-1 are now judged by location (R-LOC), price (R-BUDGET, R-PRICE-M2), and all other standard filters. **Note (2026-11-21)**: str. Pajurii is blacklisted (R-BLACKLIST 2026-11-21 21:00); **str. Tudor Vladimirescu (Chișinău Rîșcani) is re-blacklisted (R-BLACKLIST 2026-11-21 21:21)**.
  - Matching note (2026-11-04): normalise addresses before checking — lowercase, strip diacritics, transliterate Cyrillic (e.g. Николай/Nicolae Димо = Nicolae Dimo, Тудор Владимиреску = Tudor Vladimirescu; same for Poșta Veche/Пошта Веке).
  - **Historical note (2026-11-21)**: CET-1 zone was a hard exclusion from 2026-11-02 to 2026-11-20, covering str. Nicolae Dimo in Chișinău Rîșcani and ~800 m around CET-1. str. Tudor Vladimirescu was excluded 2026-11-02 to 2026-11-19, then allowed with CET-1 flag 2026-11-19 to 2026-11-21 21:21, then re-blacklisted 2026-11-21 21:21. As of 2026-11-20, the entire CET-1 zone exclusion is removed; CET-1 proximity is flagged for information only.

## 5. Rejected listings (mirror of `listings/rejected.md`)

| Listing | Link | Reason |
|---|---|---|
| Nicolae Titulescu 36/A, Botanica (1 room + living, 65 m², €110,000, 15/17) | https://999.md/ro/105988976 | R-BLACKLIST Nicolae Titulescu (2026-11-23); was published as MAYBE in Telegram msg 568 on 23.11 before the rule |
| Sarmizegetusa 53, Botanica (2 rooms, 63 m², €89,900, white variant, 5/10) | https://999.md/ro/105995223 | R-BLACKLIST Sarmizegetusa (2026-11-23); was published as MAYBE in Telegram msg 568 on 23.11 before the rule |
| Pajurii 13/1 | — | R-MICRO remote location (2026-10-31) |
| Pajurii 11, Chișinău Rîșcani (3 rooms, 68 m², 3/5, seria 102, €126.9k) | https://999.md/ro/105823043 | R-BLACKLIST Pajurii (2026-11-21); was published 21.11 in Telegram msg 535 before the rule |
| Ceucari 11/1 | https://999.md/ro/105795066 | R-BLACKLIST Ceucari (2026-11-21); was published 21.11 as MAYBE in Telegram msg 536 before the rule |
| Braniștii 5/4 (€129.9k) | https://999.md/ro/105552611 | R-BLACKLIST Braniștii (2026-11-21); was published 21.11 as PASS in Telegram msg 535 before the rule |
| Gagarin 7 (dupes 105832341, 105823686) | https://999.md/ro/105966142 | R-BLACKLIST Gagarin (2026-11-21); was published 21.11 as MAYBE in Telegram msg 537 before the rule |
| Malaia Malina (Romanescu 11997) | — | R-BLACKLIST Malaia Malina (2026-11-21); was published as MAYBE in Telegram msg 537/538 on 21.11 before the rule |
| Tudor Vladimirescu 1/4, Chișinău Rîșcani | https://999.md/ro/104749432 | R-BLACKLIST Tudor Vladimirescu (2026-11-21); was published 21.11 as MAYBE in Telegram msg 536 before the rule |
| Tudor Vladimirescu 1/1, Chișinău Rîșcani | https://999.md/ro/105936700 | R-BLACKLIST Tudor Vladimirescu (2026-11-21); was published 21.11 as MAYBE in Telegram msg 536 before the rule |
| 2 Florării 1 | https://999.md/ro/103530986 | R-BLACKLIST |
| Podul Înalt 20 | — | R-LOC Ciocana |
| Piața Unirii Principatelor 3 | — | R-FLOOR floor 15 |
| Mihail Lomonosov soclu flat (Acces Imobil 491356) | — | R-EXCL-BASEMENT semi-basement |
| Zelinski 20 | https://999.md/ro/105772089 | R-EXCL-BOTANICA (formerly R-LIFT) |
| Pandurilor 14 | https://999.md/ro/105776688 | Location unclear; previously flagged 5/5 no lift (lift no longer exclusion as of 2026-11-07) |
| Ginta Latină 12/5 | https://999.md/ro/105418586 | R-LOC Ciocana (€119.9k) |
| Colina Pușkin 8A | https://999.md/ro/105722767 | R-FLOOR floor 1 (€112k) |
| Tudor Vladimirescu 3, Chișinău Rîșcani (3 rooms, 73 m², 3/3, €84.9k; dupes 105104604, 105287773, 105736654) | https://999.md/ro/105513974 | R-BLACKLIST Tudor Vladimirescu (2026-11-21); originally rejected as R-BLACKLIST-CET1 (2026-11-02), street was removed from blacklist 2026-11-19, re-blacklisted 2026-11-21 |

## 5a. MAYBE listings (published per 2026-11-08 rules)

MAYBE candidates are now published with specific reasons. See FILTERS.md §11 for MAYBE publication rules.

| Listing | Link | Status & Required Verification |
|---|---|---|
| Cornului 9/3, Buiucani (Gonvaro-Con) | https://999.md/ro/105823314 | **NO LONGER ELIGIBLE** (2026-11-22 20:52): Old housing stock rule change. Was MAYBE (2026-11-07, updated 2026-11-08): 2+living, cadastral 93 m², 6/6, €135k (€1,452/m²) or €128k scenario (€1,376/m²). Construction year UNVERIFIED; with pre-2000 exception revoked 2026-11-22 20:52, any unverified year requires strict verification ≥2000 AND commissioned, no old-stock series allowed. Mansard status also UNVERIFIED. No longer considered without year verification. |

## 6. Benchmark

**Removed 2026-11-08 18:33.** No benchmark designated. Price each listing using real comparables per R-PRICE (§7).

**Historical note:** Matei Basarab 7/5, Rîșcani (https://999.md/ro/105332474, €66,900, 35 m², 3/5, ≈€1,911/m²) was used as benchmark until 2026-11-08 18:33; removed (below current R-AREA ≥45 m², likely pre-2000 construction). Not used for valuation or comparison.

## 7. Pricing method (R-PRICE)

- Use real comparables from 999.md asking prices: same sector, type, condition.
- Deduplicate (one flat posted by several agencies counts once).
- Report **median and IQR of €/m²**.
- Deals usually close 5–10% below asking — rule of thumb, always mark as **estimate**.
- Price ≈30%+ below comps = red flag that needs an explanation.
- **Never invent numbers.** State what data each conclusion rests on.

Reference asking medians (2026-11-01, asking prices, not deals):

| Segment | €/m² |
|---|---|
| Botanica renovated 2-room, old buildings | ≈2,066 |
| Botanica ≤6-floor buildings | ≈1,927 |
| Botanica 3-room old | ≈1,640 |
| bd. Traian 3-room | ≈1,444 |
| Rîșcani 2-room 50–65 m² | ≈1,923 (euro-renovated ≈2,127; needs repair ≈1,515) |
| Ciocana new builds renovated | ≈2,387 |

## 8. Red flags (R-REDFLAG)

- Price far below comps.
- "Floor 1" that is actually parter/demisol.
- Area larger than typical for the series (unregistered attic / loggia extension).
- Empty description (inheritance / quick sale).
- Top-floor roof leaks.
- Heating type mismatch.
- Same flat at different prices across agencies.
- Reseller posing as owner.

## 9. Due diligence (R-DD)

- Fresh extract from the Real Estate Register (owners, shares, liens/mortgage/seizure, registered area).
- Cadastral plan vs reality.
- How ownership was acquired; registered residents; minors.
- No-debt certificates: Termoelectrica, Apă-Canal, gas, electricity, owners' association.
- Roof type & last repair; heating; lift; bathroom & risers; how long listed.

## 10. Search sources and method (for agents)

**Always read `SOURCES.md` for the prioritized source registry.** Process enabled sources in priority order; log which sources were checked/skipped with reasons.

### 999.md (primary source)
- Ignore promoted ads at the top (R-EXCL-PROMO).
- List pages render client-side; organic results can be fetched via `https://999.md/graphql` with the site's filters:
  - sale `o_16_1=776` (apartments) — **also search house sale categories** since single-storey houses are now allowed (R-HOUSE)
  - sectors `o_32_9=15665,15666,15664,15667,15668,15669` — Chișinău sectors only; suburbs excluded (R-EXCL-SUBURB)
  - price filter id `9441`, unit `eur`

### All sources
- Deduplicate cross-site listings (same address, agency, phone, description patterns).
- **New parameters to flag** (2026-11-07): construction year (must be ≥2000), mansard status, house type, roof condition, legal/cadastral registration status.
- Continue on transient errors; log checked/failed sources.
- Never weaken filters to increase results — all R-* rules apply equally to all sources.

## 11. MAYBE publication rules (added 2026-11-08)

**MAYBE candidates are PUBLISHED** with literal tag **MAYBE** and specific reasons why uncertain.

- **PASS** = all hard rules met, fully verified
- **MAYBE** = unknown/contradictory criterion but no confirmed mandatory violation; published with material unknowns/conflicts and required verification
- **FAIL** = any hard rule confirmed violated; excluded from publication

### MAYBE examples
- ✅ **MAYBE** — construction year not confirmed (must verify ≥2000); other criteria met
- ✅ **MAYBE** — cadastral area conflicts with listing (must verify); price/location/year OK
- ✅ **MAYBE** — locality ambiguous between Chișinău Rîșcani (excluded) and Durlești (allowed); must resolve
- ❌ **FAIL** — construction year confirmed <2000 (R-YEAR violation)

### For each published MAYBE
- Include all material unknowns/conflicts
- Include required verification steps
- Never fabricate facts or upgrade to PASS without verification

### Previous blanket exclusion removed
MAYBE candidates are now published (previously excluded from buffer/reports). Unknown year may now publish clearly as MAYBE; known pre-2000 remains FAIL.

## 12. Reporting format

Always organize into the single price band from R-BANDS (€80k–159k inclusive). Present in this order:
1. **PASS** (up to 10) — ranked best first
2. **MAYBE** (up to 10 TOTAL) — ranked best potential first

Each section starts with a one-line summary (scanned / PASS count / MAYBE count). Nothing above €159k or below €80k. Empty section → say "нет подходящих".

### Per listing
**Status PASS/MAYBE** · link · price · rooms · m² · €/m² · street + number · floor/total · lift yes/no/unknown · building type/series/year · layout · condition · nearest main road/park/university · risks · fair price + opening offer (based on real comparables per R-PRICE) · **verdict with rule IDs**.

**For MAYBE listings, add:** specific reasons why MAYBE (e.g. "year unverified — must confirm ≥2000"), required verification steps, material unknowns/conflicts.

## 13. Publication & Telegram posting rules

### Morning run (∼09:00) empty results message (added 2026-11-20)
When the daily morning (~09:00) search run completes and finds **NO fresh eligible PASS or MAYBE** listings, it still posts **ONE short plain-text Russian message** to the Telegram channel 'real estate investments' stating that nothing new was found under the current filters.

**Message must include:**
- Statement that no new results were found
- One-line filter summary: €80–159k, ≥55 m², ≤€2200/m², этаж от 2-го, Центр, Рышкановка (без Старой Почты), Ботаника (без Малой/Большой Малины), озеро Комсомольское + вся ул. Алба Юлия (только MAYBE)
- One-line coverage summary: sources and pages scanned (honest if partial)

**Important notes:**
- **Not posted** if the run itself failed (failure reported in the Grok Bot chat instead)
- The message **adds nothing to posted_ids** (it's not a listing)
- **12:00/19:00 buffer runs unchanged**: empty buffer => no message posted

**Previous rule (superseded 2026-11-20):** morning run finding no fresh results => no messages anywhere.

---

## Кратко по-русски (жёсткие правила)

- **Цена €80–159k** (с 21.11.2026 20:21; было €80–120k); всё дороже €159k или дешевле €80k — сразу исключаем. **Белый вариант (variantă albă / белый вариант) — R-WHITE** (с 23.11.2026 17:04): не дороже €100k (дороже €100k — исключаем, даже если меньше €159k); ТОЛЬКО новый фонд, сдан или сдача в течение ~2 месяцев (к ~31.01.2027), известная поздняя дата = FAIL, несданный неизвестная дата = MAYBE; этажи 1–10 включительно (1-й этаж разрешён только для белого, >10 = FAIL); площадь от 50 м² (вместо 55 м²); ТОЛЬКО Центр/близко к центру, озеро Комсомольское/Валя Морилор, близко к Ботаническому саду (~≤1,5 км), бд. Москова, ул. Киев; вне этих зон = FAIL, неясное расстояние = MAYBE с картой; ранжировать ближе к центру первыми. Чёрный список, ≤€2200/м², не серый, не старый фонд и т.д. применяются. **Неизвестная отделка** (не указана явно) → MAYBE с проверкой «уточнить отделку: белый вариант >€100k или вне зоны = FAIL», не FAIL (с 17.11.2026, обновлено 23.11.2026). **Не-белые объявления** (готовые) без изменений: €80–159k, ≥55 м², этаж ≥2 (не 1-й), все R-LOC зоны. Было: белый вариант ≤€90k (отменено 23.11.2026 17:04).
- **Отчёт всегда из одного блока**: €80k–159k включительно (с 21.11.2026 20:21; было €80k–120k).
- **Квоты на публикацию (с 18.11.2026):** PASS до 10 объявлений, **MAYBE отдельная группа до 10 ВСЕГО** (независимая квота, не потребляет квоту PASS). Остатки в буфер, публикуются порциями ≤10 в полдень/вечером.
- Любое число комнат; площадь — от 55 м² (меньше 55 м² — исключаем; неизвестная площадь → MAYBE с проверкой).
- **Цена за м² — не дороже €2 200/м²** (дороже — исключаем, с 20.11.2026; было ≤€2 100/м² до 20.11.2026).
- Логичная планировка: своя кухня, санузел, прихожая, без проходных комнат.
- **Год постройки ≥2000, дом сдан; старый жилой фонд не рассматриваем** (с 22.11.2026 20:52) — ТОЛЬКО здания построенные в 2000 году или позже И сданные. Любое здание построенное до 2000 года = FAIL сразу. Любое здание советской/типовой серии = FAIL сразу. Ремонт в старом доме не считается. Непроверенный год без признаков старого фонда = MAYBE (требуется проверка ≥2000), никогда не PASS. **Исключение для Сталинки/102/143/чешского/индивидуального проектов ОТМЕНЕНО** (22.11.2026 20:52; было разрешено 15.11–22.11.2026) — теперь весь старый фонд исключён без исключений. Новостройки — только сданные.
- Этажи от 2-го и выше для квартир (с 21.11.2026 23:04; было 2–8 до 21.11.2026); первый этаж — нет; верхний предел снят; последний этаж — флаг (крыша). **Частные одноэтажные дома — исключение** из правила этаж ≥2.
- **Лифт — только информация**, не жёсткое исключение. Высокий этаж (≥4) без лифта — флаг, но не отказ. Лифт неизвестен в ≤5-этажке = считаем нет лифта (для флага).
- **Мансарды разрешены** (флаг: крыша/регистрация/кадастр). **Частные одноэтажные дома разрешены** (флаг: статус/кадастр/земля).
- Исключены: общежития/гостинки, цоколь/демисол/pe sol, серый вариант, несданные новостройки.
- **Районы (с 21.11.2026 23:06): ТОЛЬКО Центр (весь сектор), весь сектор Рышкановка КРОМЕ Старой Почты (Старая Почта исключена; Петричаны, Картиерул Молдова, Соколены, Студенцилор и другие части сектора допустимы; Чеукарь в чёрном списке с 21.11.2026), весь сектор Ботаника КРОМЕ Малой Малины и Большой Малины (добавлена 21.11.2026 23:06; Малая/Большая Малина в чёрном списке; вся остальная Ботаника оценивается по стандартным фильтрам, PASS возможен; была полностью исключена 02.11–21.11.2026), зона вокруг озера Комсомольское / Валя Морилор (≈0–20 минут пешком реальным маршрутом, включая прилегающие части Буюкан), и вся ул. Алба Юлия в Кишинёве (добавлена 21.11.2026 20:21) — любое здание на ул. Алба Юлия в Кишинёве (включая Скулянку/Буюканы) допустимо по местоположению независимо от расстояния до озера (R-ALBA-IULIA). Алба Юлия всегда максимум MAYBE, никогда не PASS, с пометкой «Алба Юлия — вне основной зоны (Скулянка/Буюканы)». Другие правила R-* применяются (подтверждённое нарушение = FAIL). Ул. Алба Юлия в пригородах/других населённых пунктах исключена (R-EXCL-SUBURB).** Всё остальное исключено: Старая Почта (часть сектора Рышкановка, но специально исключена), другие части Буюкан (вне зоны озера ~0–20 мин), **Телецентр** (ранее допустимо, теперь исключён с 18.11.2026), **все Чеканы** (включая бывшее исключение Port Mall/край Рышкановки, отменено 12.11.2026), **пригороды — нет** (Дурлешты, Кодру, Стэучены, Яловены, Сынжера и др.). Неоднозначный микрорайон (напр. только 'Рышкановка' без улицы/карты) = MAYBE с проверкой на карте.
- 5–10 минут пешком до магистрали, парка или университета; приоритет озера (20 минут) не отменяется общим правилом 5–10 минут.
- **Чёрный список (с 23.11.2026 09:53):** **Улицы (12):** Drumul Viilor (13.11.2026); Valea Dicescu (15.11.2026); Calea Ieșilor (15.11.2026); Grădinilor (15.11.2026); Pajurii / Păjurii / Пажурий (21.11.2026 21:00; Кишинёв Рышкановка, все номера домов, квартиры и дома; была в восточном кармане Рышкановки 01.11–20.11.2026, снова внесена в чёрный список 21.11.2026); Ceucari / Чеукарь (21.11.2026 21:09; Кишинёв Рышкановка, все номера домов, квартиры и дома); Braniștii / Branistii / Брэништий / Браништий (21.11.2026 21:09; Кишинёв Рышкановка, все номера домов, квартиры и дома); бул./ул. Gagarin / Гагарина (21.11.2026 21:21; Кишинёв Центр, все номера домов, квартиры и дома); ул. Тудор Владимиреску / Tudor Vladimirescu (21.11.2026 21:21; Кишинёв Рышкановка, все номера домов, квартиры и дома; была в чёрном списке зоны ТЭЦ-1 02.11–19.11.2026, разрешена 19.11.2026, снова внесена в чёрный список 21.11.2026); шос. Мунчешть / Muncești / Muncesti / Munceşti (22.11.2026 19:46; Кишинёв, все номера домов, квартиры и дома); ул. Сармизеджетуса / Sarmizegetusa / Сармизегетуса / Sarmisegetusa (23.11.2026 09:50; Кишинёв Ботаника, все номера домов, квартиры и дома); ул. Николае Титулеску / Nicolae Titulescu / N. Titulescu (23.11.2026 09:53; Кишинёв Ботаника, все номера домов, квартиры и дома). **Районы (2):** Малая Малина / Большая Малина (Малая Малина/Большая Малина/Malina Mică/Malina Mare) (21.11.2026 23:06; Кишинёв Ботаника, целые микрорайоны и улицы с этими названиями, квартиры и дома; неоднозначный адрес = MAYBE с проверкой на карте). **Дома (1):** бд. Дачия 59 (Edera Home) (22.11.2026 21:30; Кишинёв Ботаника, комплекс Edera Home, любая квартира в этом доме; только этот номер дома; другие номера на бд. Дачия оцениваются нормально; Dacia 59/x с упоминанием Edera Home = FAIL; неясный адрес = MAYBE с проверкой). **Зона ТЭЦ-1 полностью снята с чёрного списка** (20.11.2026): ул. Николае Димо, ул. Florării, Forăriei, Zimbrului и все адреса около ТЭЦ-1 теперь оцениваются по стандартным фильтрам (кроме Pajurii, Ceucari, Braniștii, Тудор Владимиреску — в чёрном списке с 21.11.2026). Близость к ТЭЦ-1 — только информационный флаг "близко к ТЭЦ-1", не исключение. Обязательна проверка населённого пункта из объявления, не просто название улицы. Неоднозначная локация = MAYBE до уточнения; не предполагать Кишинёв.
- Рекламные (поднятые) объявления 999.md игнорируются.
- **MAYBE теперь публикуются** с буквальной меткой MAYBE и конкретными причинами неопределённости (например, год постройки не подтверждён — требуется проверка ≥2000). PASS = полностью проверено; MAYBE = неизвестный/противоречивый критерий, но нет подтверждённого нарушения обязательного правила; FAIL = подтверждённое нарушение, исключено. Для каждого MAYBE: все существенные неизвестные/конфликты, требуемая проверка, никогда не выдумывать факты. Неизвестный год может публиковаться как MAYBE; подтверждённый <2000 остаётся FAIL (если не сталинка/102).
- Поиск включает **категорию продажи домов**, так как частные дома разрешены. Только сектора Кишинёва; пригороды исключены.
- **Эталон удалён**. Оценка по реальным аналогам (R-PRICE §7). Матей Басараб 7/5 больше не используется (меньше 45 м², вероятно <2000 года).
- Никаких выдуманных цифр; оценки помечаются как оценки.
