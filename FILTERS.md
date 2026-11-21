# FILTERS.md — Chișinău apartment search rules (single source of truth)

Owner: Andrew Grini · Last updated: 2026-11-18 23:18

Every listing must be checked against **every** rule below. Verdicts cite rule IDs.
Verdict scale:
- **PASS** (all hard rules met, fully verified)
- **MAYBE** (unknown/contradictory criterion but no confirmed mandatory violation; published with specific reasons why uncertain)
- **FAIL** (any hard rule confirmed violated; excluded from publication)

---

## 1. Budget & type

- **R-BUDGET** (updated 2026-11-21) — Asking price **€80,000–159,000 inclusive**. Anything above €159k or below €80k is excluded immediately.
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

- **R-FLOOR** (updated 2026-11-07) — For **apartments**: floors **2–8 only**. Never ground floor, never above the 8th. For **single-storey houses**: explicit exception to the 2–8 rule.
- **R-LIFT** (updated 2026-11-07):
  - Lift presence (yes/no/unknown) is **informational only**.
  - High floor (≥4) without a lift is **flagged** as a practical concern, but **NEVER a hard exclusion**.
  - Unknown lift in a building of ≤5 floors = **no lift** (for flagging purposes).
- **R-TOPFLOOR** — Top floor is always flagged (roof risk).

## 3. Always excluded

- **R-EXCL-HOSTEL** — Hostel units (cămin / gostinka / shared kitchen or bath).
- **R-EXCL-BASEMENT** — Soclu, demisol, semi-basement, "pe sol".
- **R-EXCL-UNFINISHED** (updated 2026-11-17) — Grey variant (no finishing at all) is excluded. **White variant (variantă albă) is ALLOWED** with a **mandatory price cap**: asking price must be **≤€90,000 inclusive**. White variant asking >€90,000 is **FAIL**, even though the general budget cap is €159,000. This applies to apartments and houses, all locations, all statuses (PASS/MAYBE/buffer), and uses the asking price (not hypothetical discounted offers). For white variant, add an estimated renovation budget (label it as an estimate) and the building must still be commissioned (R-EXCL-NEWBUILD).
  - **Unknown finish rule** (added 2026-11-17): If finishing is not explicitly stated, the white cap is UNKNOWN → verdict **MAYBE** with verification requirement, not FAIL. Only an explicitly stated white variant >€90k is FAIL.
  - Boundary test cases: white variant €90,000 asking = PASS (at cap); white variant €90,001 asking = FAIL (over cap).
  - Historical note: cap was €110,000 from 2026-11-07 to 2026-11-08 18:32; superseded by €90,000 cap 2026-11-08 18:32.
- **R-EXCL-NEWBUILD** — New builds not yet commissioned.
- **R-EXCL-SUBURB** (updated 2026-11-08) — Suburbs (Durlești, Codru, Stăuceni, Ialoveni, Sîngera, etc.) are excluded. **No exceptions.** (Note: Durlești was temporarily allowed 2026-11-07 to 2026-11-08; revoked 2026-11-08 18:28.)
- **R-EXCL-PROMO** — Promoted/boosted ads on 999.md are ignored (not counted in results).

## 3a. Building age & special property types

- **R-YEAR** (updated 2026-11-18) — Buildings constructed **before 2000 are excluded**. Only construction year **≥2000 (inclusive)** is allowed for both apartments and houses. **Exception (updated 2026-11-18):** The following building series/types are allowed even if pre-2000, **only when explicitly confirmed in the listing**:
  - **Stalinka**
  - **seria 102 (cotileț)**
  - **seria 143**
  - **Czech series/project** (чешский проект / proiect cehesc)
  - **Individual projects** (индивидуальный проект / proiect individual)
  
  Unconfirmed exception series → verdict **MAYBE**; other pre-2000 series (135, MS/Varnița, brejnevka, hrușciovka, etc.) remain **FAIL**. Renovation in an old building does NOT count. Unverified construction year → verdict **MAYBE**, not PASS. Never invent or guess a construction year. Flag building-age checks. Commissioned status still required (R-EXCL-NEWBUILD).
  
  **Historical note:** Exception initially covered Stalinka and seria 102 only (2026-11-15); extended to include seria 143, Czech series, and individual projects 2026-11-18 23:18.
- **R-MANSARD** (added 2026-11-07) — **Mansards are now ALLOWED**. Flag for verification: roof condition, legal registration, cadastral compliance.
- **R-HOUSE** (added 2026-11-07) — **Single-storey private houses are now ALLOWED**. Explicit exception to R-FLOOR (2–8 requirement) and R-LIFT. Flag for verification: legal status, cadastral registration, land ownership/rights.

## 4. Location

- **R-LOC** (updated 2026-11-21) — **ONLY** the following locations are acceptable:
  - **Centru** (whole sector)
  - **Rîșcani / Рышкановка (whole sector)** EXCEPT **Poșta Veche**, which remains excluded
  - **Buiucani area around Komsomol lake / Valea Morilor** — approximately 0–20 minute actual walking route, including adjacent parts of Buiucani (R-LAKE)
  - **Whole str. Alba Iulia, Chișinău** (added 2026-11-21 20:21) — every building on str. Alba Iulia in Chișinău (Buiucani/Sculeanca included) is location-OK regardless of distance from the lake (R-ALBA-IULIA). **Alba Iulia listings are ALWAYS MAYBE at best, never PASS**, and are published with the literal note «Алба Юлия — вне основной зоны (Скулянка/Буюканы)». Other R-* rules still apply (a confirmed violation is still FAIL). Alba Iulia streets in suburbs/other localities remain excluded (R-EXCL-SUBURB).
  
  **Everything else is EXCLUDED**, including:
  - **Poșta Veche** (part of Rîșcani sector but specifically excluded)
  - Other parts of Buiucani (outside the ~0–20 min lake area)
  - **Telecentru** (previously acceptable; excluded as of 2026-11-18)
  - **All Ciocana** (including former Port Mall/Rîșcani edge exception, revoked 2026-11-12)
  - Botanica (R-EXCL-BOTANICA)
  - All suburbs (Durlești, Codru, Stăuceni, Ialoveni, Sîngera, etc.) (R-EXCL-SUBURB)
  
  Unclear micro-district (e.g. only 'Rîșcani' without street/map) → verdict **MAYBE** with map check until resolved.
  
  **Historical note:** Telecentru, other Buiucani, and Ciocana near Port Mall were acceptable until 2026-11-18; whole Rîșcani sector was acceptable until 2026-11-19, then restricted to Rîșcanovca neighbourhood only (2026-11-19), then expanded to whole Rîșcani sector except Poșta Veche (2026-11-20).
- **R-LAKE** (added 2026-11-07) — Buiucani within ≈0–20 minute walk of Komsomol lake / Valea Morilor has **priority** status. Walking time is measured by actual routes, not straight-line distance. This explicit 20-minute lake priority overrides the generic 5–10 minute R-MICRO rule for these areas.
- **R-EXCL-BOTANICA** (2026-11-02) — The whole **Botanica** sector is excluded (all streets, all micro-districts), including listings already in the Telegram buffer.
  - **Poșta Veche** excluded (part of Rîșcani sector but not Rîșcanovca neighbourhood).
  - **Ciocana** excluded entirely as of 2026-11-18.
  - Verify the real address from the listing text, not just the sector field.
- **R-MICRO** — Within ≈5–10 min walk of:
  - a main road/boulevard (bd. Moscova, Alecu Russo, Kiev, Ștefan cel Mare, Dacia, Decebal, Ion Creangă, Calea Ieșilor, Mircea cel Bătrân, etc.), or
  - a park (Valea Morilor, Râșcani / La Izvor, Central Park, Valea Trandafirilor, Dendrarium, Lacul Dimo), or
  - a university (USM, UTM, ASEM, USMF, Pedagogical University).
  - Remote inner-block / outskirt streets are excluded.
  - Note: The explicit R-LAKE 20-minute priority for Buiucani near Valea Morilor / Komsomol lake takes precedence over this generic 5–10 minute rule.
- **R-BLACKLIST** (updated 2026-11-21) — The following streets are excluded entirely (whole street, both apartments and houses, all statuses including buffer):
  - **str. Drumul Viilor** (added 2026-11-13)
  - **str. Valea Dicescu** (added 2026-11-15)
  - **str. Calea Ieșilor** (added 2026-11-15)
  - **str. Grădinilor** (added 2026-11-15)
  - **str. Pajurii** (Chișinău, Rîșcani; all house numbers, apartments and houses; variants Pajurii/Păjurii/Пажурий) (added 2026-11-21 21:00)
  
  **Historical note:** East Rîșcani pocket (str. Florării, str-la Florării, str. Pajurii, str. Forăriei, str. Zimbrului) was excluded from 2026-11-01 to 2026-11-20; removed from blacklist 2026-11-20 (now evaluated by standard filters). str. Pajurii re-blacklisted 2026-11-21 21:00.
- **R-CET1-INFO** (updated 2026-11-21) — CET-1 (Termoelectrica Sursa 1) proximity **is informational only** and NOT an exclusion. All addresses previously excluded under the CET-1 zone rule are now evaluated by standard filters. Proximity to CET-1 (≈47.0331, 28.8635) should be flagged as "близко к ТЭЦ-1" for informational purposes. Reasons for CET-1 concern: plant can burn fuel oil (păcură), gas filters reported non-compliant (UTM study), planned ~250 MW new plant construction on site, weak liquidity.
  - **Locality clarification**: str. Tudor Vladimirescu and str. Nicolae Dimo exist in multiple localities. **Must verify locality/address from listing, not match bare street name.** Unclear locality → verdict MAYBE until resolved; do NOT assume Chișinău.
  - **All addresses now evaluated by standard filters**: str. Nicolae Dimo (Chișinău Rîșcani), str. Tudor Vladimirescu (Chișinău Rîșcani), and all addresses within ~800 m of CET-1 are now judged by location (R-LOC), price (R-BUDGET, R-PRICE-M2), and all other standard filters. **Note (2026-11-21)**: str. Pajurii is now blacklisted (R-BLACKLIST 2026-11-21 21:00).
  - Matching note (2026-11-04): normalise addresses before checking — lowercase, strip diacritics, transliterate Cyrillic (e.g. Николай/Nicolae Димо = Nicolae Dimo, Тудор Владимиреску = Tudor Vladimirescu; same for Poșta Veche/Пошта Веке).
  - **Historical note (2026-11-20)**: CET-1 zone was a hard exclusion from 2026-11-02 to 2026-11-20, covering str. Nicolae Dimo in Chișinău Rîșcani and ~800 m around CET-1. str. Tudor Vladimirescu was excluded 2026-11-02 to 2026-11-19, then allowed with CET-1 flag 2026-11-19. As of 2026-11-20, the entire CET-1 zone exclusion is removed; CET-1 proximity is flagged for information only.

## 5. Rejected listings (mirror of `listings/rejected.md`)

| Listing | Link | Reason |
|---|---|---|
| Pajurii 13/1 | — | R-MICRO remote location (2026-10-31) |
| Pajurii 11, Chișinău Rîșcani (3 rooms, 68 m², 3/5, seria 102, €126.9k) | https://999.md/ro/105823043 | R-BLACKLIST Pajurii (2026-11-21); was published 21.11 in Telegram msg 535 before the rule |
| 2 Florării 1 | https://999.md/ro/103530986 | R-BLACKLIST |
| Podul Înalt 20 | — | R-LOC Ciocana |
| Piața Unirii Principatelor 3 | — | R-FLOOR floor 15 |
| Mihail Lomonosov soclu flat (Acces Imobil 491356) | — | R-EXCL-BASEMENT semi-basement |
| Zelinski 20 | https://999.md/ro/105772089 | R-EXCL-BOTANICA (formerly R-LIFT) |
| Pandurilor 14 | https://999.md/ro/105776688 | Location unclear; previously flagged 5/5 no lift (lift no longer exclusion as of 2026-11-07) |
| Ginta Latină 12/5 | https://999.md/ro/105418586 | R-LOC Ciocana (€119.9k) |
| Colina Pușkin 8A | https://999.md/ro/105722767 | R-FLOOR floor 1 (€112k) |
| Tudor Vladimirescu 3, Chișinău Rîșcani (3 rooms, 73 m², 3/3, €84.9k; dupes 105104604, 105287773, 105736654) | https://999.md/ro/105513974 | R-BLACKLIST-CET1 (2026-11-02); **NOTE (2026-11-19): street removed from blacklist, may be re-evaluated if still live** |

## 5a. MAYBE listings (published per 2026-11-08 rules)

MAYBE candidates are now published with specific reasons. See FILTERS.md §11 for MAYBE publication rules.

| Listing | Link | Status & Required Verification |
|---|---|---|
| Cornului 9/3, Buiucani (Gonvaro-Con) | https://999.md/ro/105823314 | **MAYBE** (2026-11-07, updated 2026-11-08): 2+living, cadastral 93 m², 6/6, €135k (€1,452/m²) or €128k scenario (€1,376/m²). Lift status: prior source Ascensor=false NOT confirmed on site. **Material unknowns:** Construction year UNVERIFIED (must confirm ≥2000 for R-YEAR); mansard status UNVERIFIED (must verify roof/legal/cadastral for R-MANSARD); lift presence NOT confirmed on site. **Required verification:** year ≥2000, roof/legal/cadastral compliance, on-site lift confirmation. Do NOT fabricate year or clear risks; do NOT upgrade to PASS without verification. |

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
- One-line filter summary: €80–159k, ≥55 m², ≤€2200/m², floors 2–8, Rîșcani (except Poșta Veche) / Centru / Komsomol lake–Valea Morilor / whole str. Alba Iulia (MAYBE only)
- One-line coverage summary: sources and pages scanned (honest if partial)

**Important notes:**
- **Not posted** if the run itself failed (failure reported in the Grok Bot chat instead)
- The message **adds nothing to posted_ids** (it's not a listing)
- **12:00/19:00 buffer runs unchanged**: empty buffer => no message posted

**Previous rule (superseded 2026-11-20):** morning run finding no fresh results => no messages anywhere.

---

## Кратко по-русски (жёсткие правила)

- **Цена €80–159k** (с 21.11.2026 20:21; было €80–120k); всё дороже €159k или дешевле €80k — сразу исключаем. **Белый вариант (variantă albă) — не дороже €90k** (дороже €90k — исключаем, даже если меньше €159k). **Неизвестная отделка** (не указана явно) → MAYBE с проверкой, не FAIL (с 17.11.2026).
- **Отчёт всегда из одного блока**: €80k–159k включительно (с 21.11.2026 20:21; было €80k–120k).
- **Квоты на публикацию (с 18.11.2026):** PASS до 10 объявлений, **MAYBE отдельная группа до 10 ВСЕГО** (независимая квота, не потребляет квоту PASS). Остатки в буфер, публикуются порциями ≤10 в полдень/вечером.
- Любое число комнат; площадь — от 55 м² (меньше 55 м² — исключаем; неизвестная площадь → MAYBE с проверкой).
- **Цена за м² — не дороже €2 200/м²** (дороже — исключаем, с 20.11.2026; было ≤€2 100/м² до 20.11.2026).
- Логичная планировка: своя кухня, санузел, прихожая, без проходных комнат.
- **Год постройки ≥2000** — здания построенные до 2000 исключены; ремонт не считается; непроверенный год = MAYBE. **Исключение (с 18.11.2026 23:18): Сталинка, серия 102 (котелец), серия 143, чешский проект (proiect cehesc) и индивидуальный проект (proiect individual) разрешены даже если до 2000, только при явном подтверждении в объявлении**; неподтверждённые = MAYBE; другие серии до 2000 (135, MS/Вэрница, брежневка, хрущёвка и т.д.) остаются FAIL. Новостройки — только сданные.
- Этажи 2–8 для квартир; первый и выше 8-го — нет; последний этаж — флаг (крыша). **Частные одноэтажные дома — исключение** из правила 2–8 этажей.
- **Лифт — только информация**, не жёсткое исключение. Высокий этаж (≥4) без лифта — флаг, но не отказ. Лифт неизвестен в ≤5-этажке = считаем нет лифта (для флага).
- **Мансарды разрешены** (флаг: крыша/регистрация/кадастр). **Частные одноэтажные дома разрешены** (флаг: статус/кадастр/земля).
- Исключены: общежития/гостинки, цоколь/демисол/pe sol, серый вариант, несданные новостройки.
- **Районы (с 21.11.2026 20:21): ТОЛЬКО Центр (весь сектор), весь сектор Рышкановка КРОМЕ Старой Почты (Старая Почта исключена; Петричаны, Картиерул Молдова, Соколены, Студенцилор, Чеукарь и другие части сектора теперь допустимы), зона вокруг озера Комсомольское / Валя Морилор (≈0–20 минут пешком реальным маршрутом, включая прилегающие части Буюкан), и вся ул. Алба Юлия в Кишинёве (добавлена 21.11.2026 20:21) — любое здание на ул. Алба Юлия в Кишинёве (включая Скулянку/Буюканы) допустимо по местоположению независимо от расстояния до озера (R-ALBA-IULIA). Алба Юлия всегда максимум MAYBE, никогда не PASS, с пометкой «Алба Юлия — вне основной зоны (Скулянка/Буюканы)». Другие правила R-* применяются (подтверждённое нарушение = FAIL). Ул. Алба Юлия в пригородах/других населённых пунктах исключена (R-EXCL-SUBURB).** Всё остальное исключено: Старая Почта (часть сектора Рышкановка, но специально исключена), другие части Буюкан (вне зоны озера ~0–20 мин), **Телецентр** (ранее допустимо, теперь исключён с 18.11.2026), **все Чеканы** (включая бывшее исключение Port Mall/край Рышкановки, отменено 12.11.2026), Ботаника (весь сектор), **пригороды — нет** (Дурлешты, Кодру, Стэучены, Яловены, Сынжера и др.). Неоднозначный микрорайон (напр. только 'Рышкановка' без улицы/карты) = MAYBE с проверкой на карте.
- 5–10 минут пешком до магистрали, парка или университета; приоритет озера (20 минут) не отменяется общим правилом 5–10 минут.
- **Чёрный список (с 21.11.2026 21:00):** **Drumul Viilor** (13.11.2026); **Valea Dicescu** (15.11.2026); **Calea Ieșilor** (15.11.2026); **Grădinilor** (15.11.2026); **Pajurii / Păjurii / Пажурий** (21.11.2026 21:00; Кишинёв Рышкановка, все номера домов, квартиры и дома; была в восточном кармане Рышкановки 01.11–20.11.2026, снова внесена в чёрный список 21.11.2026). **Зона ТЭЦ-1 полностью снята с чёрного списка** (20.11.2026): ул. Николае Димо, ул. Тудор Владимиреску, ул. Florării, Forăriei, Zimbrului и все адреса около ТЭЦ-1 теперь оцениваются по стандартным фильтрам (кроме Pajurii — в чёрном списке с 21.11.2026). Близость к ТЭЦ-1 — только информационный флаг "близко к ТЭЦ-1", не исключение. Обязательна проверка населённого пункта из объявления, не просто название улицы. Неоднозначная локация = MAYBE до уточнения; не предполагать Кишинёв.
- Рекламные (поднятые) объявления 999.md игнорируются.
- **MAYBE теперь публикуются** с буквальной меткой MAYBE и конкретными причинами неопределённости (например, год постройки не подтверждён — требуется проверка ≥2000). PASS = полностью проверено; MAYBE = неизвестный/противоречивый критерий, но нет подтверждённого нарушения обязательного правила; FAIL = подтверждённое нарушение, исключено. Для каждого MAYBE: все существенные неизвестные/конфликты, требуемая проверка, никогда не выдумывать факты. Неизвестный год может публиковаться как MAYBE; подтверждённый <2000 остаётся FAIL (если не сталинка/102).
- Поиск включает **категорию продажи домов**, так как частные дома разрешены. Только сектора Кишинёва; пригороды исключены.
- **Эталон удалён**. Оценка по реальным аналогам (R-PRICE §7). Матей Басараб 7/5 больше не используется (меньше 45 м², вероятно <2000 года).
- Никаких выдуманных цифр; оценки помечаются как оценки.
