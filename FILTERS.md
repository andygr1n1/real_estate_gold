# FILTERS.md — Chișinău apartment search rules (single source of truth)

Owner: Andrew Grini · Last updated: 2026-11-01

Every listing must be checked against **every** rule below. Verdicts cite rule IDs.
Verdict scale: **PASS** (all hard rules met) · **MAYBE** (borderline/unknown, flagged) · **FAIL** (any hard rule violated).

---

## 1. Budget & type

- **R-BUDGET** (updated 2026-11-01) — Asking price **€40,000–140,000**. Anything above €140k (or below €40k) is excluded immediately.
- **R-BANDS** (2026-11-01) — Every report is split into 4 price blocks, in this order:
  1. **€40–60k**
  2. **€60–75k**
  3. **€75–105k**
  4. **€105–140k**
  Boundary prices go to the lower block (e.g. €60,000 → block 1, €75,000 → block 2, €105,000 → block 3). Each block starts with a one-line summary: listings scanned, passed, MAYBE; then the passed listings ranked best first. Empty block → say "нет подходящих".
  - Financing context: Prima Casă mortgage ≈ €40k over 15 years.
- **R-TYPE** (updated 2026-11-01) — Any number of rooms in all price blocks (studio, 1, 2, 3+ rooms). Always state the room count.
- **R-LAYOUT** — Logical layout: own kitchen, own bathroom, hallway, no walk-through rooms.
- **R-AREA** (updated 2026-11-02) — Total area **≥ 40 m²** for every listing, any room count. Anything below 40 m² (or with unknown area) is excluded immediately, including listings already in the Telegram buffer.
- **R-PRICE-M2** (2026-11-02) — Asking price per m² **≤ €1,800/m²** (price ÷ total area). Anything above €1,800/m² is excluded immediately, including listings already in the Telegram buffer.

## 2. Floors & elevator

- **R-FLOOR** — Floors **2–8 only**. Never ground floor, never above the 8th.
- **R-LIFT** (2026-11-01):
  - In **Botanica, Buiucani, Telecentru**: building without a lift is acceptable only on floors 2–3. Floors 4–8 only with a **confirmed** lift.
  - Unknown lift in a building of ≤5 floors = **no lift**.
  - In **Centru and Rîșcani** a missing lift is forgiven (floors 2–8 OK).
- **R-TOPFLOOR** — Top floor is always flagged (roof risk).

## 3. Always excluded

- **R-EXCL-HOSTEL** — Hostel units (cămin / gostinka / shared kitchen or bath).
- **R-EXCL-BASEMENT** — Soclu, demisol, semi-basement, "pe sol", single-storey houses, mansards.
- **R-EXCL-UNFINISHED** (updated 2026-11-01) — Grey variant (no finishing at all) is excluded. **White variant (variantă albă) is ALLOWED**: it is easier to renovate to one's own taste. For white variant, add an estimated renovation budget (label it as an estimate) and the building must still be commissioned (R-EXCL-NEWBUILD).
- **R-EXCL-NEWBUILD** — New builds not yet commissioned.
- **R-EXCL-SUBURB** — Suburbs (Durlești, Codru, Stăuceni, Ialoveni, Sîngera, etc.).
- **R-EXCL-PROMO** — Promoted/boosted ads on 999.md are ignored (not counted in results).

## 4. Location

- **R-LOC** — Priority: **Rîșcani, Centru**. Acceptable: **Botanica, Buiucani, Telecentru**.
  - **Poșta Veche** excluded.
  - **Ciocana** excluded, except the part bordering Rîșcani / near Port Mall.
  - Verify the real address from the listing text, not just the sector field.
- **R-MICRO** — Within ≈5–10 min walk of:
  - a main road/boulevard (bd. Moscova, Alecu Russo, Kiev, Ștefan cel Mare, Dacia, Decebal, Ion Creangă, Calea Ieșilor, Mircea cel Bătrân, etc.), or
  - a park (Valea Morilor, Râșcani / La Izvor, Central Park, Valea Trandafirilor, Dendrarium, Lacul Dimo), or
  - a university (USM, UTM, ASEM, USMF, Pedagogical University).
  - Remote inner-block / outskirt streets are excluded.
- **R-BLACKLIST** (2026-11-01) — East Rîșcani pocket east of str. Tudor Vladimirescu toward the Vadul lui Vodă greenbelt / CET-1: str. Florării, str-la Florării, str. Pajurii, str. Forăriei, str. Zimbrului and inner streets between them.
- **R-BLACKLIST-CET1** (2026-11-02) — Whole CET-1 (Termoelectrica Sursa 1, str. Tudor Vladimirescu 6) zone in Rîșcani: the entire str. Tudor Vladimirescu (all house numbers) and any building within ~800 m of the CET-1 site (≈47.0331, 28.8635). Reasons: plant can burn fuel oil (păcură), gas filters reported non-compliant (UTM study), planned ~250 MW new plant construction on site, weak liquidity. Tudor Vladimirescu 3 (4 duplicate ads) rejected.

## 5. Rejected listings (mirror of `listings/rejected.md`)

| Listing | Link | Reason |
|---|---|---|
| Pajurii 13/1 | — | R-MICRO remote location (2026-10-31) |
| 2 Florării 1 | https://999.md/ro/103530986 | R-BLACKLIST |
| Podul Înalt 20 | — | R-LOC Ciocana |
| Piața Unirii Principatelor 3 | — | R-FLOOR floor 15 |
| Mihail Lomonosov soclu flat (Acces Imobil 491356) | — | R-EXCL-BASEMENT semi-basement |
| Zelinski 20 | https://999.md/ro/105772089 | R-LIFT Botanica 5/5 no lift |
| Pandurilor 14 | https://999.md/ro/105776688 | R-LIFT 5/5 no lift |
| Ginta Latină 12/5 | https://999.md/ro/105418586 | R-LOC Ciocana (€119.9k) |
| Colina Pușkin 8A | https://999.md/ro/105722767 | R-FLOOR floor 1 (€112k) |
| Tudor Vladimirescu 3 (3 rooms, 73 m², 3/3, €84.9k; dupes 105104604, 105287773, 105736654) | https://999.md/ro/105513974 | R-BLACKLIST-CET1 (2026-11-02) |

## 6. Benchmark

**Matei Basarab 7/5, Rîșcani** — https://999.md/ro/105332474 — €66,900, 35 m², floor 3/5, ≈€1,911/m². Suggested offer €60–63k.
Every candidate is compared against this benchmark.

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

## 10. 999.md search method (for agents)

- Ignore promoted ads at the top (R-EXCL-PROMO).
- List pages render client-side; organic results can be fetched via `https://999.md/graphql` with the site's filters:
  - sale `o_16_1=776`
  - sectors `o_32_9=15665,15666,15664,15667,15668,15669`
  - price filter id `9441`, unit `eur`
- Deduplicate.

## 11. Reporting format per listing

price block (R-BANDS) · link · price · rooms · m² · €/m² · street + number · floor/total · lift yes/no/unknown · building type/series/year · layout · condition · nearest main road/park/university · risks · fair price + opening offer · comparison with benchmark · **verdict PASS/MAYBE/FAIL with rule IDs**.

---

## Кратко по-русски (жёсткие правила)

- Цена €40–140k; всё дороже €140k — сразу исключаем.
- Отчёт всегда из 4 блоков: €40–60k, €60–75k, €75–105k, €105–140k.
- Любое число комнат во всех блоках; площадь — от 40 м² (меньше 40 м² — исключаем, с 02.11.2026).
- Цена за м² — не дороже €1 800/м² (дороже — исключаем, с 02.11.2026).
- Логичная планировка: своя кухня, санузел, прихожая, без проходных комнат.
- Этажи 2–8; первый и выше 8-го — нет; последний этаж — флаг (крыша).
- Лифт: Ботаника/Буюканы/Телецентр без лифта — только 2–3 этаж; лифт неизвестен в ≤5-этажке = нет лифта. Центр и Рышкановка — без лифта можно.
- Исключены: общежития/гостинки, цоколь/демисол/pe sol, мансарды, частные одноэтажные дома, серый вариант (белый вариант разрешён с 01.11.2026, с оценкой бюджета ремонта), несданные новостройки, пригороды.
- Районы: приоритет Рышкановка и Центр; допустимо Ботаника, Буюканы, Телецентр. Старая Почта — нет. Чеканы — нет (кроме части у Рышкановки/Port Mall).
- 5–10 минут пешком до магистрали, парка или университета.
- Чёрный список: восток Рышкановки за Тудор Владимиреску (Florării, str-la Florării, Pajurii, Forăriei, Zimbrului); вся зона ТЭЦ-1 (вся ул. Тудор Владимиреску и ~800 м вокруг станции).
- Рекламные (поднятые) объявления 999.md игнорируются.
- Эталон: Матей Басараб 7/5, €66 900, 35 м², ≈€1 911/м², предложение €60–63k.
- Никаких выдуманных цифр; оценки помечаются как оценки.
