# FILTERS.md — Chișinău apartment search rules (single source of truth)

Owner: Andrew Grini · Last updated: 2026-11-07

Every listing must be checked against **every** rule below. Verdicts cite rule IDs.
Verdict scale: **PASS** (all hard rules met) · **MAYBE** (borderline/unknown, flagged) · **FAIL** (any hard rule violated).

---

## 1. Budget & type

- **R-BUDGET** (updated 2026-11-01) — Asking price **€40,000–140,000**. Anything above €140k (or below €40k) is excluded immediately.
- **R-BANDS** (updated 2026-11-07) — Every report is split into 2 price blocks, in this order:
  1. **€40,000–110,000 inclusive**
  2. **>€110,000–140,000 inclusive**
  Boundary: exactly €110,000 belongs to block 1. Each block starts with a one-line summary: listings scanned, passed, MAYBE; then the passed listings ranked best first. Empty block → say "нет подходящих". Up to 10 listings per block.
  - Financing context: Prima Casă mortgage ≈ €40k over 15 years.
- **R-TYPE** (updated 2026-11-01) — Any number of rooms in all price blocks (studio, 1, 2, 3+ rooms). Always state the room count.
- **R-LAYOUT** — Logical layout: own kitchen, own bathroom, hallway, no walk-through rooms.
- **R-AREA** (updated 2026-11-02) — Total area **≥ 40 m²** for every listing, any room count. Anything below 40 m² (or with unknown area) is excluded immediately, including listings already in the Telegram buffer.
- **R-PRICE-M2** (2026-11-02) — Asking price per m² **≤ €1,900/m²** (price ÷ total area). Anything above €1,900/m² is excluded immediately, including listings already in the Telegram buffer.

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
- **R-EXCL-UNFINISHED** (updated 2026-11-07) — Grey variant (no finishing at all) is excluded. **White variant (variantă albă) is ALLOWED** with a **mandatory price cap**: asking price must be **≤€110,000 inclusive**. White variant asking >€110,000 is **FAIL**, even though the general budget cap is €140,000. This applies to apartments and houses, all locations, and uses the asking price (not hypothetical discounted offers). For white variant, add an estimated renovation budget (label it as an estimate) and the building must still be commissioned (R-EXCL-NEWBUILD).
  - Boundary test cases: white variant €110,000 asking = PASS (at cap); white variant €110,001 asking = FAIL (over cap).
- **R-EXCL-NEWBUILD** — New builds not yet commissioned.
- **R-EXCL-SUBURB** (updated 2026-11-07) — Suburbs (Codru, Stăuceni, Ialoveni, Sîngera, etc.) are excluded. **Durlești is explicitly allowed** as an exception.
- **R-EXCL-PROMO** — Promoted/boosted ads on 999.md are ignored (not counted in results).

## 3a. Building age & special property types

- **R-YEAR** (added 2026-11-07) — Buildings constructed **before 2000 are excluded**. Only construction year **≥2000 (inclusive)** is allowed for both apartments and houses. Renovation in an old building does NOT count. Unverified construction year → verdict **MAYBE**, not PASS. Never invent or guess a construction year. Commissioned status still required (R-EXCL-NEWBUILD).
- **R-MANSARD** (added 2026-11-07) — **Mansards are now ALLOWED**. Flag for verification: roof condition, legal registration, cadastral compliance.
- **R-HOUSE** (added 2026-11-07) — **Single-storey private houses are now ALLOWED**. Explicit exception to R-FLOOR (2–8 requirement) and R-LIFT. Flag for verification: legal status, cadastral registration, land ownership/rights.

## 4. Location

- **R-LOC** (updated 2026-11-07) — Priority: **Centru, Rîșcani**, and **Buiucani within approximately 0–20 minute WALK of Komsomol lake / Valea Morilor** (R-LAKE). Other parts of **Buiucani** and **Telecentru** are acceptable. **Durlești** is acceptable.
- **R-LAKE** (added 2026-11-07) — Buiucani within ≈0–20 minute walk of Komsomol lake / Valea Morilor has **priority** status. Walking time is measured by actual routes, not straight-line distance. This explicit 20-minute lake priority overrides the generic 5–10 minute R-MICRO rule for these areas.
- **R-EXCL-BOTANICA** (2026-11-02) — The whole **Botanica** sector is excluded (all streets, all micro-districts), including listings already in the Telegram buffer.
  - **Poșta Veche** excluded.
  - **Ciocana** excluded, except the part bordering Rîșcani / near Port Mall.
  - Verify the real address from the listing text, not just the sector field.
- **R-MICRO** — Within ≈5–10 min walk of:
  - a main road/boulevard (bd. Moscova, Alecu Russo, Kiev, Ștefan cel Mare, Dacia, Decebal, Ion Creangă, Calea Ieșilor, Mircea cel Bătrân, etc.), or
  - a park (Valea Morilor, Râșcani / La Izvor, Central Park, Valea Trandafirilor, Dendrarium, Lacul Dimo), or
  - a university (USM, UTM, ASEM, USMF, Pedagogical University).
  - Remote inner-block / outskirt streets are excluded.
  - Note: The explicit R-LAKE 20-minute priority for Buiucani near Valea Morilor / Komsomol lake takes precedence over this generic 5–10 minute rule.
- **R-BLACKLIST** (2026-11-01) — East Rîșcani pocket east of str. Tudor Vladimirescu toward the Vadul lui Vodă greenbelt / CET-1: str. Florării, str-la Florării, str. Pajurii, str. Forăriei, str. Zimbrului and inner streets between them.
- **R-BLACKLIST-CET1** (2026-11-02) — Whole CET-1 (Termoelectrica Sursa 1, str. Tudor Vladimirescu 6) zone in Rîșcani: the entire str. Tudor Vladimirescu (all house numbers) and any building within ~800 m of the CET-1 site (≈47.0331, 28.8635). Reasons: plant can burn fuel oil (păcură), gas filters reported non-compliant (UTM study), planned ~250 MW new plant construction on site, weak liquidity. Tudor Vladimirescu 3 (4 duplicate ads) rejected.
  - Extended 2026-11-02: the entire **str. Nicolae Dimo** (all house numbers, incl. 1/3, 23 etc.) is also excluded as part of the CET-1 zone, regardless of distance.
  - Matching note (2026-11-04): normalise addresses before checking any blacklist — lowercase, strip diacritics, transliterate Cyrillic (e.g. Николай/Николае Димо = Nicolae Dimo, Тудор Владимиреску = Tudor Vladimirescu; same for Florării/Флорилор, Pajurii/Пажурий, Forăriei/Форэрией, Zimbrului/Зимбрулуй, Poșta Veche/Пошта Веке). Use map coordinates vs the CET-1 radius when available.

## 5. Rejected listings (mirror of `listings/rejected.md`)

| Listing | Link | Reason |
|---|---|---|
| Pajurii 13/1 | — | R-MICRO remote location (2026-10-31) |
| 2 Florării 1 | https://999.md/ro/103530986 | R-BLACKLIST |
| Podul Înalt 20 | — | R-LOC Ciocana |
| Piața Unirii Principatelor 3 | — | R-FLOOR floor 15 |
| Mihail Lomonosov soclu flat (Acces Imobil 491356) | — | R-EXCL-BASEMENT semi-basement |
| Zelinski 20 | https://999.md/ro/105772089 | R-EXCL-BOTANICA (formerly R-LIFT) |
| Pandurilor 14 | https://999.md/ro/105776688 | Location unclear; previously flagged 5/5 no lift (lift no longer exclusion as of 2026-11-07) |
| Ginta Latină 12/5 | https://999.md/ro/105418586 | R-LOC Ciocana (€119.9k) |
| Colina Pușkin 8A | https://999.md/ro/105722767 | R-FLOOR floor 1 (€112k) |
| Tudor Vladimirescu 3 (3 rooms, 73 m², 3/3, €84.9k; dupes 105104604, 105287773, 105736654) | https://999.md/ro/105513974 | R-BLACKLIST-CET1 (2026-11-02) |

## 5a. User-designated MAYBE listings under review

| Listing | Link | Notes |
|---|---|---|
| Cornului 9/3, Buiucani (Gonvaro-Con) | https://999.md/ro/105823314 | User-designated MAYBE (2026-11-07): 2+living, cadastral 93 m², 6/6, €135k (€1,452/m²) or €128k scenario (€1,376/m²). Lift status: prior source Ascensor=false NOT confirmed on site. **Construction year and mansard status UNVERIFIED** → verdict MAYBE pending R-YEAR (≥2000), R-MANSARD verification (roof/legal/cadastral), and on-site lift confirmation. Do NOT fabricate year or clear risks. |

## 6. Benchmark

**Matei Basarab 7/5, Rîșcani** — https://999.md/ro/105332474 — €66,900, 35 m², floor 3/5, ≈€1,911/m². Suggested offer €60–63k.
**Note (2026-11-07)**: This benchmark is **historical reference only**. At 35 m² it is below the current R-AREA minimum (≥40 m²), and if the building was constructed before 2000 it would not meet R-YEAR. Use for pricing comparison context, not as a target for new searches.

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
  - sectors `o_32_9=15665,15666,15664,15667,15668,15669` — ensure **Durlești** (R-EXCL-SUBURB exception) is not silently omitted by sector queries; add sector code if needed
  - price filter id `9441`, unit `eur`

### All sources
- Deduplicate cross-site listings (same address, agency, phone, description patterns).
- **New parameters to flag** (2026-11-07): construction year (must be ≥2000), mansard status, house type, roof condition, legal/cadastral registration status.
- Continue on transient errors; log checked/failed sources.
- Never weaken filters to increase results — all R-* rules apply equally to all sources.

## 11. Reporting format

Always group into the 2 price blocks from R-BANDS (€40k–110k inclusive, >€110k–140k inclusive), each with a one-line summary (scanned / passed / MAYBE). Up to 10 listings per block.

### Per listing
price block (R-BANDS) · link · price · rooms · m² · €/m² · street + number · floor/total · lift yes/no/unknown · building type/series/year · layout · condition · nearest main road/park/university · risks · fair price + opening offer · comparison with benchmark · **verdict PASS/MAYBE/FAIL with rule IDs**.

---

## Кратко по-русски (жёсткие правила)

- Цена €40–140k; всё дороже €140k — сразу исключаем. **Белый вариант (variantă albă) — не дороже €110k** (дороже €110k — исключаем, даже если меньше €140k, с 07.11.2026).
- Отчёт всегда из 2 блоков: €40k–110k включительно (€110 000 точно в первом блоке), >€110k–140k включительно (с 07.11.2026). До 10 объявлений в каждом блоке.
- Любое число комнат во всех блоках; площадь — от 40 м² (меньше 40 м² — исключаем, с 02.11.2026).
- Цена за м² — не дороже €1 900/м² (дороже — исключаем, с 02.11.2026).
- Логичная планировка: своя кухня, санузел, прихожая, без проходных комнат.
- **Год постройки ≥2000** — здания построенные до 2000 исключены; ремонт не считается; непроверенный год = MAYBE (с 07.11.2026). Новостройки — только сданные.
- Этажи 2–8 для квартир; первый и выше 8-го — нет; последний этаж — флаг (крыша). **Частные одноэтажные дома — исключение** из правила 2–8 этажей (с 07.11.2026).
- **Лифт — только информация**, не жёсткое исключение (с 07.11.2026). Высокий этаж (≥4) без лифта — флаг, но не отказ. Лифт неизвестен в ≤5-этажке = считаем нет лифта (для флага).
- **Мансарды разрешены** с 07.11.2026 (флаг: крыша/регистрация/кадастр). **Частные одноэтажные дома разрешены** (флаг: статус/кадастр/земля).
- Исключены: общежития/гостинки, цоколь/демисол/pe sol, серый вариант, несданные новостройки.
- Районы: приоритет **Центр, Рышкановка**, и **Буюканы в пределах ≈0–20 минут пешком** от озера Комсомольское / Валя Морилор (с 07.11.2026). Остальные Буюканы и Телецентр — допустимо. **Дурлешты — допустимо** (исключение из пригородов, с 07.11.2026). Ботаника — нет (весь сектор). Старая Почта — нет. Чеканы — нет (кроме части у Рышкановки/Port Mall).
- 5–10 минут пешком до магистрали, парка или университета; приоритет озера (20 минут) не отменяется общим правилом 5–10 минут.
- Чёрный список: восток Рышкановки за Тудор Владимиреску (Florării, str-la Florării, Pajurii, Forăriei, Zimbrului); вся зона ТЭЦ-1 (вся ул. Тудор Владимиреску, вся ул. Николае Димо и ~800 м вокруг станции).
- Рекламные (поднятые) объявления 999.md игнорируются.
- Поиск включает **категорию продажи домов**, так как частные дома разрешены; Дурлешты не упускается запросами по секторам (с 07.11.2026).
- Эталон: Матей Басараб 7/5, €66 900, 35 м², ≈€1 911/м², предложение €60–63k. **Это исторический эталон** (меньше 40 м² и возможно построен до 2000 года, с 07.11.2026).
- Никаких выдуманных цифр; оценки помечаются как оценки.
