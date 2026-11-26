# Changelog — filter rules

## 2026-11-26 20:47 — white cap €138k, €/m² cap €2,286, Ion Creangă / Dendrarium allowed

**Owner rule change 2026-11-26 20:47 Europe/Chisinau (from Andrew).** White-variant price cap raised, per-m² cap raised for all listings, and str. Ion Creangă near the Dendrarium / Komsomol lake explicitly allowed so that 999.md/105823931 can pass the filters.

### R-WHITE-PRICE: cap raised to €138,000
- **Old cap:** white variant asking **≤€100,000 inclusive** (2026-11-23 17:04).
- **New cap:** white variant asking **≤€138,000 inclusive**. General €80k minimum unchanged. White variant asking >€138k is still **FAIL**, even though the general budget cap remains €159,000. Uses asking price (not hypothetical discounted offers).
- R-BUDGET mention of the white cap updated to €138k.
- Unknown-finish verification text updated: «уточнить отделку: белый вариант >€138k или вне зоны = FAIL».

### R-PRICE-M2: cap raised to €2,286/m² for all listings
- **Old cap:** ≤€2,200/m² (2026-11-20).
- **New cap:** asking price per m² **≤ €2,286/m²** for **all listings** (white and non-white).
- **Definition:** price ÷ total area, **rounded to the nearest whole euro**, must be ≤ €2,286. Anything above €2,286/m² after rounding is excluded immediately.
- Example: €134,900 ÷ 59 m² = €2,286.44 → €2,286/m² after rounding, so it meets the cap.

### Location: Ion Creangă near Dendrarium / Komsomol lake explicitly allowed
- **R-LOC / R-LAKE:** str. Ion Creangă in Buiucani near the Dendrarium / Komsomol lake (Valea Morilor) is explicitly allowed, including the Ion Creangă stretch opposite/near the Dendrarium and the buildings **Ion Creangă 5, 5/2, and 5/3** (Dendrarium Park Residence; developers Astercon-Grup SRL and Dansicons SRL; handed over 2017; 13 floors). Other stretches of Ion Creangă outside the ~0–20 min lake / Dendrarium area are not automatically allowed.
- **R-WHITE-LOC:** added **Dendrarium area (str. Ion Creangă near the Dendrarium)** to the allowed white-variant location list, including Ion Creangă 5, 5/2, 5/3.

### Acceptance example
- https://999.md/ro/105823931 — Ion Creangă 5/2, Buiucani, 2 rooms, 59 m², floor 10/13, white variant, €134,900, 2 bathrooms, built 2017 (commissioned). Must now pass location, white price, white floor (1–10), white area (≥50), and €/m². Added to `listings/shortlist.md` and FILTERS.md §5a as MAYBE with caveats: 2017 court attachment on Dansicons property (outcome unknown); asking above earlier comps in the complex; duplicate Romanescu P22957. Was not in `listings/rejected.md`.

### Files updated
- FILTERS.md: "Last updated" 2026-11-26 20:47; R-BUDGET; R-PRICE-M2; R-WHITE / R-WHITE-PRICE / R-WHITE-LOC (Dendrarium area + acceptance example); unknown-finish rule; historical notes; R-LOC; R-LAKE; §5a; one-line filter summary; Russian summary
- AGENTS.md: R-WHITE summary and morning-run one-liner
- templates/listing-check.md: R-BUDGET, R-PRICE-M2, R-WHITE, R-LOC
- .cursor/rules/real-estate-filters.mdc: condensed R-BUDGET / R-WHITE / R-PRICE-M2 / R-LOC / Telegram one-liner
- listings/shortlist.md: added Ion Creangă 5/2 (105823931)
- CHANGELOG.md: this entry

### All other criteria unchanged
Max price €159k, min €80k, white new-stock / floors 1–10 / ≥50 m² rules (apart from the €138k cap and Dendrarium location), ≥55 m² (non-white), year ≥2000 AND commissioned (old housing stock excluded), floor ≥2 (non-white), blacklisted streets/areas/buildings, Alba Iulia MAYBE-only, quotas — all unchanged.

## 2026-11-25 13:03 — str. Prigoreni blacklisted

**Street blacklist expanded.** Owner rule change 2026-11-25 13:03 Europe/Chisinau (from Andrew).

### str. Prigoreni (whole street) blacklisted
- **R-BLACKLIST**: Added **str. Prigoreni** (Chișinău, Botanica; all house numbers including 5/1, apartments and houses; variants Пригорень/Пригорены) to street blacklist.
- **Any apartment or house on this street** = FAIL R-BLACKLIST immediately (all statuses including buffer).
- **All house numbers** (including 5/1) excluded without exception.
- **No recovery**: blacklisted street, entire street excluded.

### Blacklist structure updated
- **R-BLACKLIST** street list now includes **13 streets** (was 12):
  - Drumul Viilor, Valea Dicescu, Calea Ieșilor, Grădinilor, Pajurii, Ceucari, Braniștii, Gagarin, Tudor Vladimirescu, Muncești, Sarmizegetusa, Nicolae Titulescu, **Prigoreni** (new)
- **Areas (3)**: Malaia Malina, Bolșaia Malina, Aeroport (unchanged)
- **Buildings (2)**: bd. Dacia 59 (Edera Home), bd. Dacia 62 (Grand Family) (unchanged)

### R-LOC Botanica description updated
- **Botanica sector allowed-location text** now mentions Prigoreni exclusion:
- "Whole Botanica sector EXCEPT Malaia Malina and Bolșaia Malina (micro-districts and streets), str. Sarmizegetusa (whole street, all house numbers), str. Nicolae Titulescu (whole street, all house numbers), **and str. Prigoreni (whole street, all house numbers)**"

### Russian summary updated
- Blacklist header date updated to **25.11.2026 13:03**
- Streets count updated from **(12)** to **(13)**
- Added **"ул. Пригорень / Prigoreni / Пригорены"** to street list (25.11.2026 13:03; Кишинёв Ботаника, все номера домов включая 5/1, квартиры и дома)

### Rejected listing added
- **str. Prigoreni 5/1, Botanica** (3 rooms, 73 m², 5/6, €116.5k) | https://999.md/ro/106008515 | R-BLACKLIST Prigoreni (2026-11-25 13:03); was published 25.11 in Telegram msg 579 (PASS) before the rule | 2026-11-25

### Files updated
- FILTERS.md: "Last updated" date (2026-11-25 13:03), R-BLACKLIST (updated header date to 2026-11-25, added Prigoreni to Streets section), R-LOC (updated Botanica description to mention Prigoreni exclusion), Russian summary (updated date to 25.11.2026 13:03, streets count to 13, added Prigoreni to list), §5 rejected listings (added Prigoreni 5/1 row)
- .cursor/rules/real-estate-filters.mdc: R-BLACKLIST / R-BLACKLIST-BUILDING / R-BLACKLIST-AREA (updated date to 2026-11-25, streets count to 13, added Prigoreni)
- templates/listing-check.md: R-BLACKLIST checklist (updated streets count to 13, added Prigoreni; also updated areas to 3 and buildings to 2)
- listings/rejected.md: added Prigoreni 5/1 row
- CHANGELOG.md: this entry

### All other criteria unchanged
Max price €159k, white variant R-WHITE (≤€100k, new stock, floors 1–10, ≥50 m², restricted location), ≥55 m² (non-white), price/m² ≤€2,200, year ≥2000 AND commissioned (old housing stock excluded), floor ≥2 (non-white), blacklisted areas (3 areas), blacklisted buildings (2 buildings), location rules — all unchanged.

## 2026-11-23 18:27 — Aeroport area boundary firmed

**Aeroport blacklist boundary made firm.** Owner rule change 2026-11-23 18:27 Europe/Chisinau (confirmed by Andrew).

### Aeroport area boundary firmed (R-BLACKLIST-AREA)

**Old description** (2026-11-23 17:34): vague wording "eastern stretch of bd. Dacia towards the airport roughly from ~Dacia 44 / Valea Crucii onwards including Dacia 58, Dacia 62..."

**New firm boundary** (2026-11-23 18:27):
- **Aeroport = every bd. Dacia house number ≥44** (including 44–59, 60/x, 62, 69/x etc.)
- **Plus Galata, Băcioii Noi, str. Aeroportului**
- **Any listing labelled «zona Aeroport»**
- **Anything within ~1.5 km of the airport**
- **Unnumbered bd. Dacia listing**: pin at longitude ≥28.868 (east of Dacia 44, OSM 46.9775, 28.8684) → **FAIL**; west of it → **MAYBE** with map check
- Unclear distance → MAYBE with map check

### Rejected listings added (24 rows)

Added 24 rejected listings to `listings/rejected.md` for Aeroport area and bd. Dacia 62:
- bd. Dacia 62/G (Exfactor Grand Family) — 105474701 (was published msg 569 PASS)
- bd. Dacia 62 (Grand Family) — 105464506
- bd. Dacia 60/12, 60/5 (multiple), 60/1, 69/1 — Aeroport area
- bd. Dacia 58 (DMZ Home Construct) — 103836871 (was published msgs 569-571 MAYBE)
- bd. Dacia 44, 47/2, 49 (multiple), 49/6, 56 — Aeroport area, bd. Dacia ≥44
- bd. Dacia (unnumbered, pins east of Dacia 44) — multiple
- bd. Dacia 59 (Edera Home) — multiple (building + area blacklist)
- str-la Gheorghe Cucereanu 11, Băcioii Noi — Aeroport area
- bd. Dacia «în zona Aeroportului» — labelled Aeroport
- șos. Muncești 782/1 — Aeroport area + Muncești street

### Files updated
- FILTERS.md: "Last updated" date (2026-11-23 18:27), R-BLACKLIST-AREA Aeroport description (firmed boundary: bd. Dacia ≥44, plus Galata/Băcioii Noi/Aeroportului/labelled Aeroport/~1.5 km; unnumbered Dacia longitude ≥28.868 = FAIL), Russian summary (Aeroport description updated with firm boundary)
- listings/rejected.md: added 24 rows for Aeroport area and Dacia 62
- listings/shortlist.md: checked, no Dacia 58/62 URLs found (no changes needed)
- CHANGELOG.md: this entry

### All other criteria unchanged
Max price €159k, white variant R-WHITE (≤€100k, new stock, floors 1–10, ≥50 m², restricted location), ≥55 m² (non-white), price/m² ≤€2,200, year ≥2000 AND commissioned (old housing stock excluded), floor ≥2 (non-white), blacklisted streets (12 streets), blacklisted areas (3 areas), blacklisted buildings (2 buildings), location rules — all unchanged.

## 2026-11-23 17:34 — Dacia 62 and Aeroport area blacklisted

**Blacklist expanded: building and area.** Owner rule change 2026-11-23 17:34 Europe/Chisinau.

### bd. Dacia 62 (Grand Family) building blacklisted
- **R-BLACKLIST-BUILDING**: Added **bd. Dacia 62** (Chișinău, Botanica; all blocks 62, 62/1, 62/A…62/G including Grand Family complex) to building blacklist.
- **Any apartment in this building** = FAIL R-BLACKLIST-BUILDING immediately.
- **All blocks with number 62** excluded without exception.
- **No recovery**: blacklisted building, any apartment in this building excluded.
- Other bd. Dacia numbers evaluated normally (but note: bd. Dacia 59 also blacklisted; bd. Dacia 58, 62 also in Aeroport area blacklist).

### Aeroport area blacklisted
- **R-BLACKLIST-AREA**: Added **Aeroport area** (район Аэропорт, Chișinău, Botanica; near Chișinău International Airport) to area blacklist.
- **Includes**: str. Aeroportului, the eastern stretch of bd. Dacia towards the airport (roughly from ~Dacia 44 / Valea Crucii onwards, verify on map; includes Dacia 58, 62), any listing labelled Aeroport, any address within ~1.5 km of the airport.
- **Any apartment or house in this area** = FAIL R-BLACKLIST-AREA immediately.
- **Unclear distance** to airport or uncertain whether address is within Aeroport area → **MAYBE** with map check required.
- **No recovery**: blacklisted area, entire area excluded.

### Blacklist structure updated
- **R-BLACKLIST** now includes three categories:
  - **Streets (12)**: Drumul Viilor, Valea Dicescu, Calea Ieșilor, Grădinilor, Pajurii, Ceucari, Braniștii, Gagarin, Tudor Vladimirescu, Muncești, Sarmizegetusa, Nicolae Titulescu (unchanged)
  - **Areas (3)**: Malaia Malina, Bolșaia Malina, **Aeroport** (new)
  - **Buildings (2)**: bd. Dacia 59 (Edera Home), **bd. Dacia 62 (Grand Family)** (new)

### Russian summary updated
- Blacklist header date updated to **23.11.2026 17:34**
- **"Районы (2)"** changed to **"Районы (3)"**: added **Аэропорт / Aeroport** (23.11.2026 17:34; Кишинёв Ботаника, район Аэропорт около международного аэропорта Кишинёва; ул. Аэропортулуй / Aeroportului, восточный участок бд. Дачия в сторону аэропорта примерно от ~Дачия 44 / Valea Crucii включая Dacia 58, 62, любое объявление с меткой Aeroport, любой адрес в ~1,5 км от аэропорта; неясное расстояние = MAYBE с картой)
- **"Дома (1)"** changed to **"Дома (2)"**: added **бд. Дачия 62 (Grand Family)** (23.11.2026 17:34; Кишинёв Ботаника, все блоки 62, 62/1, 62/A…62/G включая комплекс Grand Family, любая квартира в этом доме; все блоки с номером 62; другие номера бд. Дачия оцениваются нормально, но Дачия 59 также в чёрном списке, Дачия 58, 62 также в районе Аэропорт)

### Rejected listing added
- **bd. Dacia 62/G Grand Family, Botanica** | — | R-BLACKLIST-BUILDING bd. Dacia 62 (Grand Family); building blacklisted; posted 23.11 msg 569-571 | 2026-11-23

### Files updated
- FILTERS.md: "Last updated" date (2026-11-23 17:34), R-BLACKLIST (updated header to include R-BLACKLIST-AREA, added Aeroport to Areas section, added bd. Dacia 62 to Buildings section), Russian summary (updated date to 23.11.2026 17:34, areas count to 3, buildings count to 2, added Aeroport and Dacia 62 descriptions), §5 rejected listings (added bd. Dacia 62/G Grand Family row)
- .cursor/rules/real-estate-filters.mdc: R-BLACKLIST / R-BLACKLIST-BUILDING / R-BLACKLIST-AREA (updated header, areas count to 3, buildings count to 2, added Aeroport and Dacia 62)
- listings/rejected.md: added bd. Dacia 62/G Grand Family row
- CHANGELOG.md: this entry

### All other criteria unchanged
Max price €159k, white variant R-WHITE (≤€100k, new stock, floors 1–10, ≥50 m², restricted location), ≥55 m² (non-white), price/m² ≤€2,200, year ≥2000 AND commissioned (old housing stock excluded), floor ≥2 (non-white), blacklisted streets (12 streets), location rules — all unchanged.

## 2026-11-23 17:04 — white variant rules replaced: R-WHITE

**Major white variant rule change.** Owner rule change 2026-11-23 17:04 Europe/Chisinau.

### Old white variant cap (≤€90k) REPLACED with comprehensive R-WHITE

The old simple price cap for white variant (variantă albă) listings has been replaced with a comprehensive set of rules under **R-WHITE**. White variant now has multiple mandatory constraints beyond standard filters.

### New R-WHITE rules (applies ONLY to listings explicitly stated as white variant / variantă albă / белый вариант)

- **R-WHITE-PRICE** (2026-11-23): Asking price **≤€100,000 inclusive** (up from €90k). General €80k minimum unchanged. White variant asking >€100k is **FAIL**, even though the general budget cap is €159,000. Uses asking price (not hypothetical discounted offers).

- **R-WHITE-NEW** (2026-11-23): **New stock only**. Building must be **commissioned OR have evidence of commissioning within approximately 2 months** (by ~31 January 2027). Known later commissioning date → **FAIL**. Uncommissioned with unknown date → **MAYBE** with commissioning verification required. Old housing stock (pre-2000) remains excluded for all listings including white variant.

- **R-WHITE-FLOOR** (2026-11-23): Floors **1–10 inclusive**. **Floor 1 (ground floor) is ALLOWED for white variant only** (exception to general R-FLOOR ≥2 rule). Floor >10 → **FAIL**. Soclu/demisol/pe sol (semi-basement) → **FAIL** (R-EXCL-BASEMENT unchanged).

- **R-WHITE-AREA** (2026-11-23): Total area **≥50 m²** (instead of general ≥55 m² rule for non-white listings). Known <50 m² → **FAIL**. Unknown area → **MAYBE** with area verification required.

- **R-WHITE-LOC** (2026-11-23): **Location restrictions for white variant**. ONLY the following locations are acceptable for white variant:
  - **Centru / near-centre**
  - **Komsomol lake / Valea Morilor area** (R-LAKE ~0–20 min walk)
  - **Near Botanical Garden** (Grădina Botanică, approximately ≤1.5 km)
  - **bd. Moscova**
  - **str. Kiev**
  
  White variant elsewhere → **FAIL**. Unclear distance to allowed zones → **MAYBE** with map check required. Rank white variant listings closer to centre first.

### Other rules still apply to white variant

- R-BLACKLIST (all streets/areas/buildings): white variant on blacklisted street/area/building = FAIL
- R-PRICE-M2 (≤€2,200/m²): white variant must meet price per m² cap
- No grey variant: grey variant remains excluded
- R-YEAR (≥2000 AND commissioned): old housing stock excluded for white variant (R-WHITE-NEW requires new stock)
- All other standard filters apply unless explicitly superseded by R-WHITE

### Unknown finish rule updated

- **Unknown finish rule** (added 2026-11-17, updated 2026-11-23): If finishing is not explicitly stated, finish type is UNKNOWN → verdict **MAYBE** with verification requirement «уточнить отделку: белый вариант >€100k или вне зоны = FAIL», not FAIL. Only an explicitly stated white variant violating R-WHITE is FAIL.

### Non-white listings unchanged

- **Non-white listings** (ready/finished apartments) are unchanged: €80k–159k, ≥55 m², floor ≥2 (no floor 1), all R-LOC locations allowed, no R-WHITE constraints.

### For white variant: add renovation estimate

- For white variant, add an estimated renovation budget (label it as an estimate).

### Historical note

- White variant cap was **€110,000** from 2026-11-07 to 2026-11-08 18:32
- Superseded by **€90,000 cap** 2026-11-08 18:32
- Superseded by **comprehensive R-WHITE rules** (€100k cap, new stock only, floors 1–10, area ≥50 m², location restrictions) 2026-11-23 17:04

### Files updated

- FILTERS.md: "Last updated" date (2026-11-23 17:04), R-BUDGET (mention R-WHITE), replaced R-EXCL-UNFINISHED with comprehensive R-WHITE section (R-WHITE-PRICE, R-WHITE-NEW, R-WHITE-FLOOR, R-WHITE-AREA, R-WHITE-LOC), Russian summary (updated white variant description with all R-WHITE constraints)
- AGENTS.md: added R-WHITE bullet after R-ALBA-IULIA
- .cursor/rules/real-estate-filters.mdc: R-BUDGET line (updated white variant to R-WHITE summary), R-EXCL-* line (updated white variant reference)
- templates/listing-check.md: R-BUDGET line (updated to reference R-WHITE), added R-WHITE checklist item
- CHANGELOG.md: this entry

### All other criteria unchanged

Max price €159k (non-white), ≥55 m² (non-white), price/m² ≤€2,200, year ≥2000 AND commissioned (old housing stock excluded), floor ≥2 (non-white), blacklisted streets (12 streets), blacklisted areas (2 areas), blacklisted buildings (1 building), location rules — all unchanged.

## 2026-11-23 09:53 (str. Nicolae Titulescu blacklisted)

**Street blacklist expanded.** Owner rule change 2026-11-23 09:53 Europe/Chisinau.

### str. Nicolae Titulescu (whole street) blacklisted
- **R-BLACKLIST**: Added **str. Nicolae Titulescu** (Chișinău, Botanica; all house numbers, apartments and houses; variants Николае Титулеску/N. Titulescu) to street blacklist.
- **Any apartment or house on this street** = FAIL R-BLACKLIST immediately (all statuses including buffer).
- **All house numbers** (36/A, etc.) excluded without exception.
- **No recovery**: blacklisted street, entire street excluded.

### Blacklist structure updated
- **R-BLACKLIST** street list now includes **12 streets** (was 11):
  - Drumul Viilor, Valea Dicescu, Calea Ieșilor, Grădinilor, Pajurii, Ceucari, Braniștii, Gagarin, Tudor Vladimirescu, Muncești, Sarmizegetusa, **Nicolae Titulescu** (new)
- **Areas (2)**: Malaia Malina, Bolșaia Malina (unchanged)
- **Buildings (1)**: bd. Dacia 59 (Edera Home) (unchanged)

### R-LOC Botanica description updated
- **Botanica sector allowed-location text** now mentions both Sarmizegetusa and Nicolae Titulescu exclusions:
- "Whole Botanica sector EXCEPT Malaia Malina and Bolșaia Malina (micro-districts and streets), **str. Sarmizegetusa (whole street, all house numbers), and str. Nicolae Titulescu (whole street, all house numbers)**"

### Russian summary updated
- Blacklist header date updated to **23.11.2026 09:53**
- Streets count updated from **(11)** to **(12)**
- Added **"ул. Николае Титулеску / Nicolae Titulescu / N. Titulescu"** to street list (23.11.2026 09:53; Кишинёв Ботаника, все номера домов, квартиры и дома)

### Telegram posting filter summary updated
- Empty-results message now includes both Sarmizegetusa and Nicolae Titulescu in Botanica exclusions:
- "Ботаника (без Малой/Большой Малины, без Сармизеджетусы, без Титулеску)"

### Rejected listing added
- **Nicolae Titulescu 36/A, Botanica** (1 room + living, 65 m², €110,000, 15/17) | https://999.md/ro/105988976 | R-BLACKLIST Nicolae Titulescu (2026-11-23); was published as MAYBE in Telegram msg 568 on 23.11 before the rule | 2026-11-23

### Files updated
- FILTERS.md: R-BLACKLIST (added Nicolae Titulescu to Streets section), R-LOC (updated Botanica description to mention Nicolae Titulescu exclusion), Russian summary (updated blacklist date to 23.11.2026 09:53, streets count to 12, added Nicolae Titulescu to list), §5 rejected listings (added Nicolae Titulescu 36/A row)
- .cursor/rules/real-estate-filters.mdc: R-BLACKLIST / R-BLACKLIST-BUILDING (updated streets count to 12, added Nicolae Titulescu), R-LOC (updated Botanica description), TELEGRAM POSTING (updated filter summary to include Nicolae Titulescu in Botanica exclusions)
- templates/listing-check.md: R-BLACKLIST checklist (updated streets count to 12, added Nicolae Titulescu)
- listings/rejected.md: added Nicolae Titulescu 36/A row
- CHANGELOG.md: this entry

### All other criteria unchanged
Max price €159k, white variant ≤€90k, area ≥55 m², price/m² ≤€2,200, year ≥2000 AND commissioned (old housing stock excluded), floor ≥2 (no upper limit), blacklisted areas (2 areas), blacklisted buildings (1 building), location rules — all unchanged.

## 2026-11-23 09:50 (str. Sarmizegetusa blacklisted)

**Street blacklist expanded.** Owner rule change 2026-11-23 09:50 Europe/Chisinau.

### str. Sarmizegetusa (whole street) blacklisted
- **R-BLACKLIST**: Added **str. Sarmizegetusa** (Chișinău, Botanica; all house numbers, apartments and houses; variants Сармизеджетуса/Сармизегетуса/Sarmisegetusa) to street blacklist.
- **Any apartment or house on this street** = FAIL R-BLACKLIST immediately (all statuses including buffer).
- **All house numbers** (53, 53A, 53D, 18/1, etc.) excluded without exception.
- **No recovery**: blacklisted street, entire street excluded.

### Blacklist structure updated
- **R-BLACKLIST** street list now includes **11 streets** (was 10):
  - Drumul Viilor, Valea Dicescu, Calea Ieșilor, Grădinilor, Pajurii, Ceucari, Braniștii, Gagarin, Tudor Vladimirescu, Muncești, **Sarmizegetusa** (new)
- **Areas (2)**: Malaia Malina, Bolșaia Malina (unchanged)
- **Buildings (1)**: bd. Dacia 59 (Edera Home) (unchanged)

### R-LOC Botanica description updated
- **Botanica sector allowed-location text** now mentions Sarmizegetusa exclusion:
- "Whole Botanica sector EXCEPT Malaia Malina and Bolșaia Malina (micro-districts and streets) **and str. Sarmizegetusa (whole street, all house numbers)**, which are blacklisted (R-BLACKLIST)"

### Russian summary updated
- Blacklist header date updated to **23.11.2026 09:50**
- Streets count updated from **(10)** to **(11)**
- Added **"ул. Сармизеджетуса / Sarmizegetusa / Сармизегетуса / Sarmisegetusa"** to street list (23.11.2026 09:50; Кишинёв Ботаника, все номера домов, квартиры и дома)

### Telegram posting filter summary updated
- Empty-results message now includes Sarmizegetusa in Botanica exclusions:
- "Ботаника (без Малой/Большой Малины, без Сармизеджетусы)"

### Rejected listing added
- **Sarmizegetusa 53, Botanica** (2 rooms, 63 m², €89,900, white variant, 5/10) | https://999.md/ro/105995223 | R-BLACKLIST Sarmizegetusa (2026-11-23); was published as MAYBE in Telegram msg 568 on 23.11 before the rule | 2026-11-23

### Files updated
- FILTERS.md: R-BLACKLIST (added Sarmizegetusa to Streets section), R-LOC (updated Botanica description to mention Sarmizegetusa exclusion), Russian summary (updated blacklist date to 23.11.2026 09:50, streets count to 11, added Sarmizegetusa to list), §5 rejected listings (added Sarmizegetusa 53 row)
- .cursor/rules/real-estate-filters.mdc: R-BLACKLIST / R-BLACKLIST-BUILDING (updated streets count to 11, added Sarmizegetusa), R-LOC (updated Botanica description), TELEGRAM POSTING (updated filter summary to include Sarmizegetusa in Botanica exclusions)
- templates/listing-check.md: R-BLACKLIST checklist (updated streets count to 11, added Sarmizegetusa)
- listings/rejected.md: added Sarmizegetusa 53 row
- CHANGELOG.md: this entry

### All other criteria unchanged
Max price €159k, white variant ≤€90k, area ≥55 m², price/m² ≤€2,200, year ≥2000 AND commissioned (old housing stock excluded), floor ≥2 (no upper limit), blacklisted areas (2 areas), blacklisted buildings (1 building), location rules — all unchanged.

## 2026-11-22 21:30 (bd. Dacia 59 building blacklisted)

**Building-level blacklist added.** Owner rule change 2026-11-22 21:30 Europe/Chisinau.

### bd. Dacia 59 (Edera Home) building blacklisted
- **R-BLACKLIST-BUILDING**: Added **bd. Dacia 59** (Chișinău, Botanica; complex Edera Home) to blacklist.
- **Any apartment in this building** = FAIL R-BLACKLIST-BUILDING immediately.
- **Only this building number**: other bd. Dacia numbers (e.g. Dacia 57, Dacia 61, etc.) evaluated normally by standard filters.
- **Dacia 59/x that names Edera Home** → FAIL.
- **Unclear address** (Dacia 59 without Edera Home confirmation) → MAYBE with check.
- **No recovery**: blacklisted building, any apartment excluded.

### Blacklist structure updated
- **R-BLACKLIST** now includes three categories:
  - **Streets (10)**: Drumul Viilor, Valea Dicescu, Calea Ieșilor, Grădinilor, Pajurii, Ceucari, Braniștii, Gagarin, Tudor Vladimirescu, Muncești
  - **Areas (2)**: Malaia Malina, Bolșaia Malina
  - **Buildings (1)**: bd. Dacia 59 (Edera Home)

### Russian summary updated
- Blacklist header date updated to **22.11.2026 21:30**
- Added **"Дома (1)"** section: **"бд. Дачия 59 (Edera Home)"** (22.11.2026 21:30; Кишинёв Ботаника, комплекс Edera Home, любая квартира в этом доме; только этот номер дома; другие номера на бд. Дачия оцениваются нормально; Dacia 59/x с упоминанием Edera Home = FAIL; неясный адрес = MAYBE с проверкой)

### Rejected listing added
- **bd. Dacia 59 (Edera Home), Botanica** | https://999.md/ro/105072311 | R-BLACKLIST-BUILDING bd. Dacia 59 (Edera Home); building blacklisted | 2026-11-22

### Files updated
- FILTERS.md: R-BLACKLIST (added Buildings section with bd. Dacia 59, updated header to include R-BLACKLIST-BUILDING), Russian summary (blacklist updated with "Дома (1)" section)
- .cursor/rules/real-estate-filters.mdc: R-BLACKLIST / R-BLACKLIST-BUILDING (added Buildings (1) section with bd. Dacia 59)
- templates/listing-check.md: R-BLACKLIST checklist (added R-BLACKLIST-BUILDING, added buildings (1) note)
- listings/rejected.md: added bd. Dacia 59 row
- CHANGELOG.md: this entry

### All other criteria unchanged
Max price €159k, white variant ≤€90k, area ≥55 m², price/m² ≤€2,200, year ≥2000 AND commissioned (old housing stock excluded), floor ≥2 (no upper limit), blacklisted streets (10 streets), blacklisted areas (2 areas), location rules — all unchanged.

## 2026-11-22 20:52 (old housing stock excluded entirely, pre-2000 exception revoked)

**Major filter tightening.** Owner rule change 2026-11-22 20:52 Europe/Chisinau.

### Old housing stock excluded entirely
- **R-YEAR / R-EXCL-OLD-STOCK**: **OLD HOUSING STOCK EXCLUDED ENTIRELY**. Only buildings constructed in **2000 or later (≥2000)** AND commissioned are eligible.
- **Any pre-2000 building** = FAIL immediately.
- **Any Soviet-era or typical series building** = FAIL immediately.
- Renovation in an old building does NOT count.
- Unverified construction year with no old-stock indication → verdict MAYBE (must verify ≥2000), never PASS.

### Pre-2000 series exception REVOKED
- **Exception for pre-2000 building series REVOKED** as of 2026-11-22 20:52.
- **Previously allowed** (2026-11-15 to 2026-11-22): Stalinka, seria 102 (cotileț), seria 143, Czech series/project, individual projects.
- **Now**: All these building types are **FAIL** (old housing stock excluded without exception).
- R-YEAR updated with superseded/revoked note and historical context preserved.

### Russian summary updated
- Updated to: **"Год постройки ≥2000, дом сдан; старый жилой фонд не рассматриваем"** (с 22.11.2026 20:52).
- Noted exception revoked: **"Исключение для Сталинки/102/143/чешского/индивидуального проектов ОТМЕНЕНО"** (22.11.2026 20:52; было разрешено 15.11–22.11.2026).
- Clear statement: "теперь весь старый фонд исключён без исключений".

### MAYBE listings updated
- **Cornului 9/3, Buiucani** marked as **NO LONGER ELIGIBLE** (2026-11-22 20:52) due to old housing stock rule change. Construction year was UNVERIFIED; with pre-2000 exception revoked, requires strict verification ≥2000 AND commissioned, no old-stock series allowed.

### Files updated
- FILTERS.md: R-YEAR (revoked exception, marked as superseded with date 2026-11-22 20:52, preserved historical note), Russian summary (updated with old housing stock exclusion note), §5a MAYBE listings (marked Cornului 9/3 as no longer eligible)
- .cursor/rules/real-estate-filters.mdc: R-YEAR / R-EXCL-OLD-STOCK (revoked exception with date)
- templates/listing-check.md: R-YEAR checklist (updated to reflect revoked exception)
- CHANGELOG.md: this entry

### Impact
- **Significantly reduces eligible properties**: all pre-2000 buildings now excluded
- **Previously MAYBE listings** relying on pre-2000 exception (Stalinka, seria 102, etc.) are now ineligible
- **Only modern housing stock** (2000+) accepted

### All other criteria unchanged
Max price €159k, white variant ≤€90k, area ≥55 m², price/m² ≤€2,200, floor ≥2 (no upper limit), blacklisted streets (10 streets), blacklisted areas (2 areas), location rules — all unchanged.

**Historical context:** Pre-2000 series exception was introduced 2026-11-15 (Stalinka, seria 102), extended 2026-11-18 23:18 (seria 143, Czech series, individual projects), operated for one week, then revoked entirely 2026-11-22 20:52.

## 2026-11-22 19:46 (șos. Muncești blacklisted)

**Street blacklist update.** Owner rule change 2026-11-22 19:46 Europe/Chisinau.

### șos. Muncești added to R-BLACKLIST
- **R-BLACKLIST**: Added **șos. Muncești** (Chișinău; all house numbers, apartments and houses; variants Мунчешть/Muncesti/Munceşti) (added 2026-11-22 19:46).
- Updated R-BLACKLIST header date to 2026-11-22.
- Updated blacklist counts throughout documentation: "9 streets" → "10 streets".

### Blacklist summary updated
- Russian summary: Updated blacklist header date to 22.11.2026 19:46, added counts "Улицы (10)" and "Районы (2)", added Muncești with full variants.
- .cursor/rules/real-estate-filters.mdc: Updated R-BLACKLIST date to 2026-11-22, added counts "Streets (10)" and "Areas (2)", added Muncești.
- templates/listing-check.md: Updated R-BLACKLIST to include count "(10)" and added Muncești; also added areas note "(2): Malaia Malina, Bolșaia Malina".

### Files updated
- FILTERS.md: R-BLACKLIST (added Muncești, updated header date), Russian summary (blacklist updated with counts and Muncești)
- .cursor/rules/real-estate-filters.mdc: R-BLACKLIST (added Muncești with counts)
- templates/listing-check.md: R-BLACKLIST checklist (added Muncești with counts)
- CHANGELOG.md: this entry

### Current blacklist
- **10 streets**: Drumul Viilor, Valea Dicescu, Calea Ieșilor, Grădinilor, Pajurii, Ceucari, Braniștii, Gagarin, Tudor Vladimirescu, Muncești
- **2 areas**: Malaia Malina, Bolșaia Malina

### All other criteria unchanged
Max price €159k, white variant ≤€90k, area ≥55 m², price/m² ≤€2,200, year ≥2000, floor ≥2 (no upper limit), location rules (Centru, Rîșcani except Poșta Veche, Botanica except Malaia/Bolșaia Malina, Komsomol lake area, Alba Iulia MAYBE-only) — all unchanged.

## 2026-11-21 23:06 (Botanica sector allowed, Malaia/Bolșaia Malina blacklisted)

**Major location expansion.** Owner rule change 2026-11-21 23:06 Europe/Chisinau.

### Botanica sector allowed (except Malaia/Bolșaia Malina)
- **R-LOC**: Added **whole Botanica sector** to acceptable locations (added 2026-11-21 23:06).
- **EXCEPTION**: Malaia Malina and Bolșaia Malina micro-districts and streets are blacklisted (R-BLACKLIST).
- All other Botanica locations evaluated by standard filters; **PASS possible**.
- **R-EXCL-BOTANICA**: Rule superseded. Botanica sector is now ALLOWED (except Malaia/Bolșaia Malina blacklisted areas).
- Historical note: whole Botanica was excluded 2026-11-02 to 2026-11-21 23:06.

### Malaia Malina and Bolșaia Malina added to R-BLACKLIST
- **R-BLACKLIST**: Added **Malaia Malina / Bolșaia Malina** (Chișinău, Botanica; whole micro-districts and streets named after them, apartments and houses; variants Малая Малина/Большая Малина/Malina Mică/Malina Mare) (added 2026-11-21 23:06).
- Unclear address → MAYBE with map check.
- R-BLACKLIST now includes 9 streets + 2 areas (Malaia Malina, Bolșaia Malina).

### Filter summaries updated
- Morning "nothing found" message filter summary locations updated to: **"Центр, Рышкановка (без Старой Почты), Ботаника (без Малой/Большой Малины), озеро Комсомольское + вся ул. Алба Юлия (только MAYBE)"**
- Updated in FILTERS.md §13, AGENTS.md, .cursor/rules/real-estate-filters.mdc.
- Russian summary districts line updated: added Botanica with exception note (Малая/Большая Малина blacklisted), updated date to 2026-11-21 23:06.
- Russian summary blacklist line updated: reorganized into "Улицы" and "Районы" sections, added Malaia/Bolșaia Malina to areas section.

### Rejected listings added/updated
- **Added**: Malaia Malina (Romanescu 11997) | R-BLACKLIST Malaia Malina (2026-11-21); was published as MAYBE in Telegram msg 537/538 on 21.11 before the rule
- **Fixed**: Gagarin 7 entry corrected from "msg 538" to "msg 537"

### Files updated
- FILTERS.md: R-LOC (added Botanica with Malaia/Bolșaia Malina exception), R-EXCL-BOTANICA (superseded note), R-BLACKLIST (added Malaia/Bolșaia Malina to new "Areas" section), removed Botanica from excluded list, §13 morning message filter summary (updated locations), Russian summary (districts and blacklist updated)
- AGENTS.md: morning message filter summary (updated locations)
- .cursor/rules/real-estate-filters.mdc: R-LOC (added Botanica), R-BLACKLIST (added Malaia/Bolșaia Malina), TELEGRAM POSTING summary (updated locations)
- templates/listing-check.md: R-EXCL-BOTANICA (updated to note Botanica allowed except Malaia/Bolșaia Malina)
- listings/rejected.md: added Malaia Malina row, fixed Gagarin 7 msg number
- CHANGELOG.md: this entry

### All other criteria unchanged
Max price €159k, white variant ≤€90k, area ≥55 m², price/m² ≤€2,200, year ≥2000, floor ≥2 (no upper limit), blacklisted streets (9 streets: Drumul Viilor, Valea Dicescu, Calea Ieșilor, Grădinilor, Pajurii, Ceucari, Braniștii, Gagarin, Tudor Vladimirescu) — all unchanged.

**Historical context:** Whole Botanica sector was excluded from 2026-11-02 to 2026-11-21 23:06. Now allowed except Malaia/Bolșaia Malina blacklisted areas.

## 2026-11-21 23:04 (maximum floor limit removed)

**Floor requirement simplified.** Owner rule change 2026-11-21 23:04 Europe/Chisinau.

### Maximum floor limit removed from R-FLOOR
- **R-FLOOR**: Apartments must be on floor **≥2** (second floor and above). No upper floor limit (was floors 2–8).
- Never ground floor (floor 1) — unchanged.
- Top-floor flag (R-TOPFLOOR) remains informational only — unchanged.
- High floor without lift warning remains informational only — unchanged.
- Single-storey houses exception unchanged (explicit exception to floor ≥2 requirement).

### Filter summaries updated
- Morning "nothing found" message filter summary: "floors 2–8" changed to "этаж от 2-го" (floor from 2nd and up).
- Updated in FILTERS.md §13, AGENTS.md, .cursor/rules/real-estate-filters.mdc.
- Russian summary: "Этажи 2–8 для квартир" changed to "Этажи от 2-го и выше для квартир (с 21.11.2026 23:04; было 2–8 до 21.11.2026); первый этаж — нет; верхний предел снят".

### Files updated
- FILTERS.md: R-FLOOR (updated date to 2026-11-21, removed upper limit), R-HOUSE (updated exception text), §13 morning message filter summary, Russian summary (updated with date and note)
- AGENTS.md: morning message filter summary (changed "floors 2–8" to "этаж от 2-го")
- .cursor/rules/real-estate-filters.mdc: R-FLOOR (added "no upper limit (2026-11-21)"), TELEGRAM POSTING summary (changed "floors 2–8" to "этаж от 2-го")
- templates/listing-check.md: R-FLOOR checklist (changed "floors 2–8" to "floor ≥2 (no upper limit)")
- CHANGELOG.md: this entry

### All other criteria unchanged
Max price €159k, white variant ≤€90k, area ≥55 m², price/m² ≤€2,200, year ≥2000, blacklisted streets (9 streets), location rules — all unchanged.

**Note:** Historical CHANGELOG entries mentioning "floors 2–8" left unchanged as historical records.

## 2026-11-21 21:21 (bd. Gagarin and str. Tudor Vladimirescu blacklisted)

**Street blacklist update.** Owner rule change 2026-11-21 21:21 Europe/Chisinau.

### bd./str. Gagarin and str. Tudor Vladimirescu (re-blacklisted) added to R-BLACKLIST
- **R-BLACKLIST**: Added **bd./str. Gagarin** (Chișinău, Centru; all house numbers, apartments and houses; variants Iuri Gagarin/Gagarin/Гагарина) (added 2026-11-21 21:21).
- **R-BLACKLIST**: Re-added **str. Tudor Vladimirescu** (Chișinău, Rîșcani; all house numbers, apartments and houses; variants Тудор Владимиреску) (added 2026-11-21 21:21; re-blacklisted, was removed 2026-11-19).
- Updated R-BLACKLIST historical note: Tudor Vladimirescu was in CET-1 zone blacklist 2026-11-02 to 2026-11-19, removed 2026-11-19, re-blacklisted 2026-11-21 21:21.
- R-CET1-INFO updated: removed Tudor Vladimirescu from "evaluated by standard filters" list; noted it is re-blacklisted (R-BLACKLIST 2026-11-21 21:21). Updated historical note.
- Russian summary: added Gagarin and Tudor Vladimirescu to blacklist list with full variants and re-blacklisting note for Tudor Vladimirescu.

### Rejected listings added
- Gagarin 7 (dupes 105832341, 105823686) | https://999.md/ro/105966142 | R-BLACKLIST Gagarin (2026-11-21); was published 21.11 as MAYBE in Telegram msg 538 before the rule
- Tudor Vladimirescu 1/4, Chișinău Rîșcani | https://999.md/ro/104749432 | R-BLACKLIST Tudor Vladimirescu (2026-11-21); was published 21.11 as MAYBE in Telegram msg 536 before the rule
- Tudor Vladimirescu 1/1, Chișinău Rîșcani | https://999.md/ro/105936700 | R-BLACKLIST Tudor Vladimirescu (2026-11-21); was published 21.11 as MAYBE in Telegram msg 536 before the rule

### Updated existing rejected listing
- Tudor Vladimirescu 3, Chișinău Rîșcani: reason updated from "R-BLACKLIST-CET1 (2026-11-02)" to "R-BLACKLIST Tudor Vladimirescu (2026-11-21); originally rejected as R-BLACKLIST-CET1 (2026-11-02), street was removed from blacklist 2026-11-19, re-blacklisted 2026-11-21"

### Files updated
- FILTERS.md: R-BLACKLIST (added Gagarin and Tudor Vladimirescu, updated historical note), R-CET1-INFO (removed Tudor Vladimirescu from evaluated list, updated historical note), §5 rejected listings (added Gagarin 7, T.Vladimirescu 1/4, T.Vladimirescu 1/1, updated T.Vladimirescu 3), Russian summary (blacklist with both streets)
- .cursor/rules/real-estate-filters.mdc: R-BLACKLIST (added both streets, updated historical note), R-CET1-INFO (removed Tudor Vladimirescu, noted re-blacklisted)
- templates/listing-check.md: R-BLACKLIST checklist (added both streets), R-BLACKLIST-CET1 (updated Tudor Vladimirescu from ALLOWED to EXCLUDED)
- listings/rejected.md: added Gagarin 7, T.Vladimirescu 1/4, T.Vladimirescu 1/1 rows; updated T.Vladimirescu 3 reason
- CHANGELOG.md: this entry

### All other criteria unchanged
Max price €159k, white variant ≤€90k, area ≥55 m², price/m² ≤€2,200, year ≥2000, floors 2–8, other blacklisted streets (Drumul Viilor, Valea Dicescu, Calea Ieșilor, Grădinilor, Pajurii, Ceucari, Braniștii), location rules — all unchanged.

## 2026-11-21 21:09 (str. Ceucari and str. Braniștii blacklisted)

**Street blacklist update.** Owner rule change 2026-11-21 21:09 Europe/Chisinau.

### str. Ceucari and str. Braniștii added to R-BLACKLIST
- **R-BLACKLIST**: Added **str. Ceucari** (Chișinău, Rîșcani; all house numbers, apartments and houses; variants Ceucari/Чеукарь) (added 2026-11-21 21:09).
- **R-BLACKLIST**: Added **str. Braniștii** (Chișinău, Rîșcani; all house numbers, apartments and houses; variants Braniștii/Branistii/Брэништий/Браништий) (added 2026-11-21 21:09).
- Removed Ceucari from examples of allowed Rîșcani micro-districts in .cursor/rules/real-estate-filters.mdc (now noted as blacklisted along with Braniștii).
- Russian summary blacklist updated with both streets.

### Rejected listings added
- Ceucari 11/1 | https://999.md/ro/105795066 | R-BLACKLIST Ceucari (2026-11-21); was published 21.11 as MAYBE in Telegram msg 536 before the rule
- Braniștii 5/4 (€129.9k) | https://999.md/ro/105552611 | R-BLACKLIST Braniștii (2026-11-21); was published 21.11 as PASS in Telegram msg 535 before the rule

### Files updated
- FILTERS.md: R-BLACKLIST (added Ceucari and Braniștii), §5 rejected listings (added Ceucari 11/1 and Braniștii 5/4), Russian summary (blacklist list with both streets)
- .cursor/rules/real-estate-filters.mdc: R-BLACKLIST (added Ceucari and Braniștii), R-LOC (removed Ceucari from allowed examples, noted both blacklisted)
- templates/listing-check.md: R-BLACKLIST checklist (added Ceucari and Braniștii)
- listings/rejected.md: added Ceucari 11/1 and Braniștii 5/4 rows
- CHANGELOG.md: this entry

### All other criteria unchanged
Max price €159k, white variant ≤€90k, area ≥55 m², price/m² ≤€2,200, year ≥2000, floors 2–8, other blacklisted streets (Drumul Viilor, Valea Dicescu, Calea Ieșilor, Grădinilor, Pajurii), location rules — all unchanged.

## 2026-11-21 21:00 (str. Pajurii blacklisted)

**Street blacklist update.** Owner rule change 2026-11-21 21:00 Europe/Chisinau.

### str. Pajurii added to R-BLACKLIST
- **R-BLACKLIST**: Added **str. Pajurii** (Chișinău, Rîșcani; all house numbers, apartments and houses; variants Pajurii/Păjurii/Пажурий) to excluded streets (added 2026-11-21 21:00).
- Historical note updated: Pajurii was previously in East Rîșcani pocket exclusion (2026-11-01 to 2026-11-20), removed 2026-11-20, now re-blacklisted 2026-11-21 21:00.
- R-CET1-INFO updated to note Pajurii is now blacklisted (R-BLACKLIST 2026-11-21 21:00).
- Russian summary blacklist updated with Pajurii and note about re-blacklisting.

### Rejected listing added
- Pajurii 11, Chișinău Rîșcani (3 rooms, 68 m², 3/5, seria 102, €126.9k) | https://999.md/ro/105823043 | R-BLACKLIST Pajurii (2026-11-21); was published 21.11 in Telegram msg 535 before the rule

### Files updated
- FILTERS.md: R-BLACKLIST (added Pajurii, updated header date to 2026-11-21, updated historical note), R-CET1-INFO (noted Pajurii blacklisted), §5 rejected listings (added Pajurii 11), Russian summary (blacklist list with Pajurii)
- .cursor/rules/real-estate-filters.mdc: R-BLACKLIST (added Pajurii), R-CET1-INFO (noted Pajurii blacklisted)
- templates/listing-check.md: R-BLACKLIST checklist (updated to current blacklist including Pajurii, removed obsolete east Rîșcani references)
- listings/rejected.md: added Pajurii 11 row
- CHANGELOG.md: this entry

### All other criteria unchanged
Max price €159k, white variant ≤€90k, area ≥55 m², price/m² ≤€2,200, year ≥2000, floors 2–8, other blacklisted streets (Drumul Viilor, Valea Dicescu, Calea Ieșilor, Grădinilor), location rules — all unchanged.

## 2026-11-21 20:21 (max price €159k, whole str. Alba Iulia allowed as MAYBE-only)

**Major filter expansion.** Owner rule change 2026-11-21 20:21 Europe/Chisinau.

### 1. Max price raised to €159,000
- **R-BUDGET**: Maximum asking price **€159,000 inclusive** (was €120,000). Asking >€159k => **FAIL R-BUDGET**. Below €80k stays FAIL.
- **R-BANDS**: Single price band **€80,000–159,000 inclusive** (was €80,000–120,000).
- Historical note appended: ", then €80,000–159,000 (2026-11-21 20:21)".
- White variant cap **≤€90,000** unchanged (still applies even within the €159k general cap).
- Fixed stale phrase in R-EXCL-UNFINISHED: "even though the general budget cap is €160,000" changed to "€159,000".

### 2. New location rule R-ALBA-IULIA added
- **R-LOC**: Added **whole str. Alba Iulia, Chișinău** to acceptable locations (added 2026-11-21 20:21).
- Every building on str. Alba Iulia in Chișinău (Buiucani/Sculeanca included) is location-OK regardless of distance from the lake (R-ALBA-IULIA).
- **Alba Iulia listings are ALWAYS MAYBE at best, never PASS**, published with literal note «Алба Юлия — вне основной зоны (Скулянка/Буюканы)».
- Other R-* rules still apply (a confirmed violation is still FAIL).
- Alba Iulia streets in suburbs/other localities remain excluded (R-EXCL-SUBURB).
- Added to .cursor/rules/real-estate-filters.mdc R-LOC line.
- Russian summary updated with equivalent bullet.

### 3. Morning message filter summary updated
- **Publication workflow**: Morning empty-results message updated to reflect new values: €80–159k, ≥55 m², ≤€2200/m², floors 2–8, Rîșcani (except Poșta Veche) / Centru / Komsomol lake–Valea Morilor / whole str. Alba Iulia.

### 4. Template R-LOC checklist updated
- **templates/listing-check.md**: Fixed stale R-LOC checklist line that still said "Rîșcanovca neighbourhood" (outdated since 2026-11-20). Updated to: "ONLY Centru (whole), whole Rîșcani sector except Poșta Veche, Buiucani near Komsomol lake/Valea Morilor (~0–20 min walk), and whole str. Alba Iulia in Chișinău (R-ALBA-IULIA, 2026-11-21: max verdict MAYBE with note «Алба Юлия — вне основной зоны»); everything else excluded".

### Files updated
- FILTERS.md: R-BUDGET (€159k), R-BANDS (€80k–159k with updated historical note), R-EXCL-UNFINISHED (fixed stale €160k mention), R-LOC (whole str. Alba Iulia with R-ALBA-IULIA), §13 morning message filter summary, Russian summary (price, single-block line, districts with Alba Iulia)
- AGENTS.md: reporting format (€80k–159k), morning message filter summary (Alba Iulia)
- .cursor/rules/real-estate-filters.mdc: R-BUDGET (€159k), R-BANDS (€159k), R-LOC (R-ALBA-IULIA), TELEGRAM POSTING (€159k, Alba Iulia)
- templates/listing-check.md: R-BUDGET (€159k), R-BANDS (€159k), R-LOC (fixed stale line, added Alba Iulia)
- CHANGELOG.md: this entry

**Follow-up clarification (2026-11-21 20:28):** Added '(MAYBE only)' suffix to Alba Iulia mentions in filter summaries (AGENTS.md, FILTERS.md, .cursor/rules/real-estate-filters.mdc) and added R-ALBA-IULIA note to AGENTS.md reporting format section.

### All other criteria unchanged
- Area ≥55 m², white variant ≤€90k, price/m² ≤€2,200, year ≥2000 + commissioned (with series exceptions Stalinka/102/143/Czech/individual), floors 2–8, quotas ≤10 PASS / ≤10 MAYBE, street blacklist (Drumul Viilor, Valea Dicescu, Calea Ieșilor, Grădinilor), excluded districts (Telecentru, Ciocana, Botanica, suburbs except Alba Iulia), CET-1 informational only — all unchanged.

**Historical context:** Maximum price was €120k from 2026-11-20 to 2026-11-21 20:21. Alba Iulia was not explicitly mentioned before 2026-11-21 20:21 (would have been excluded as part of Buiucani outside lake area or Sculeanca).

## 2026-11-20 11:51 (R-SANITARY requirement removed)

**Sanitary rooms requirement removed.** Owner rule change 2026-11-20 11:51 Europe/Chisinau.

### Two-separate-sanitary-rooms requirement removed
- **R-SANITARY removed entirely**: No building (new builds included) needs two sanitary rooms any more.
- A single/combined bathroom is neither FAIL nor a MAYBE reason.
- Sanitary rooms are still reported per listing as information only.
- Removed now-redundant wording about series exceptions (Stalinka, seria 102, seria 143, Czech series/project, individual projects) being "exempt from the two-sanitary-rooms requirement," but the series exceptions themselves remain unchanged.

### Files updated
- FILTERS.md: R-SANITARY section removed, Russian summary updated
- AGENTS.md: no changes needed (R-SANITARY not mentioned)
- .cursor/rules/real-estate-filters.mdc: R-SANITARY removed
- templates/listing-check.md: R-SANITARY checklist item removed
- CHANGELOG.md: this entry

### All other criteria unchanged
All filter rules unchanged: budget €80k–120k, area ≥55 m², price/m² ≤€2,200, construction year ≥2000 with series exceptions (Stalinka/102/143/Czech/individual), floors 2–8, location (Rîșcani except Poșta Veche / Centru / Komsomol lake–Valea Morilor), etc.

## 2026-11-20 11:06 (price raised to €120k, price/m² to €2200, whole Rîșcani except Poșta Veche, CET-1 zone removed)

**Major filter expansion.** Owner rule change 2026-11-20 11:06 Europe/Chisinau.

### 1. Max price raised to €120,000
- **R-BUDGET**: Maximum asking price **€120,000 inclusive** (was €100,000). Asking >€120k => **FAIL R-BUDGET**. Below €80k stays FAIL.
- **R-BANDS**: Single price band **€80,000–120,000 inclusive** (was €80,000–100,000).
- White variant cap **≤€90,000** unchanged (still applies even within the €120k general cap).

### 2. Max price per m² raised to €2,200/m²
- **R-PRICE-M2**: Maximum asking price per m² **≤€2,200/m²** (was €2,100/m²). Anything above €2,200/m² excluded immediately.

### 3. Location expanded to whole Rîșcani sector (except Poșta Veche)
- **R-LOC**: Acceptable locations now:
  - **Centru** (whole sector) — unchanged
  - **Rîșcani / Рышкановка (whole sector)** EXCEPT **Poșta Veche** (Poșta Veche specifically excluded; Rîșcanovca, Petricani, Cartierul Moldova, Socoleni, Studenților, Ceucari [later blacklisted 2026-11-21], and all other parts of Rîșcani sector now allowed)
  - **Buiucani area around Komsomol lake / Valea Morilor** (~0–20 min walk including adjacent Buiucani) — unchanged
- Previously (2026-11-19): only Rîșcanovca neighbourhood was acceptable from Rîșcani sector.
- **R-EXCL-BOTANICA** note: Poșta Veche remains excluded (part of Rîșcani sector but specifically excluded).

### 4. CET-1 zone exclusion removed entirely
- **R-BLACKLIST-CET1 removed, replaced with R-CET1-INFO** (informational only): CET-1 proximity is now **informational only**, NOT an exclusion.
- All addresses previously excluded under CET-1 zone rule now evaluated by standard filters:
  - str. Nicolae Dimo (Chișinău Rîșcani) — now allowed
  - str. Tudor Vladimirescu (Chișinău Rîșcani) — already allowed since 2026-11-19, confirmed
  - All addresses within ~800 m of CET-1 (≈47.0331, 28.8635) — now allowed
- Proximity to CET-1 should be flagged as "близко к ТЭЦ-1" for informational purposes only.
- Locality verification still required: must verify from listing, not assume Chișinău.

### 5. Street blacklist reduced (east Rîșcani removed)
- **R-BLACKLIST**: East Rîșcani streets removed from blacklist:
  - str. Florării, str-la Florării, str. Pajurii, str. Forăriei, str. Zimbrului — removed from blacklist (were excluded 2026-11-01 to 2026-11-20)
  - These streets now evaluated by standard filters
- Remaining blacklist unchanged:
  - str. Drumul Viilor (added 2026-11-13)
  - str. Valea Dicescu (added 2026-11-15)
  - str. Calea Ieșilor (added 2026-11-15)
  - str. Grădinilor (added 2026-11-15)

### 6. Morning message filter summary updated
- **Publication workflow**: Morning empty-results message updated to reflect new values: €80–120k, ≥55 m², ≤€2200/m², floors 2–8, Rîșcani (except Poșta Veche) / Centru / Komsomol lake–Valea Morilor.

### Files updated
- FILTERS.md: R-BUDGET (€120k), R-BANDS (€80k–120k), R-PRICE-M2 (€2,200/m²), R-LOC (whole Rîșcani except Poșta Veche), R-BLACKLIST (east Rîșcani removed), R-BLACKLIST-CET1 replaced with R-CET1-INFO (informational only), §13 morning message filter summary, Russian summary (all changes)
- AGENTS.md: reporting format (€80k–120k), morning message filter summary
- .cursor/rules/real-estate-filters.mdc: all rule updates (budget, price/m², location, blacklist, CET-1 info, Telegram posting)
- CHANGELOG.md: this entry

### All other criteria unchanged
- Area ≥55 m², white variant ≤€90k, year ≥2000 + commissioned (with series exceptions Stalinka/102/143/Czech/individual), two sanitary rooms for new builds, floors 2–8, quotas ≤10 PASS / ≤10 MAYBE, remaining street blacklist (Drumul Viilor, Valea Dicescu, Calea Ieșilor, Grădinilor), excluded districts (Telecentru, Ciocana, Botanica, suburbs) — all unchanged.

**Historical context:** Maximum price was €100k from 2026-11-19 to 2026-11-20; €/m² was €2,100 from 2026-11-18 to 2026-11-20; only Rîșcanovca neighbourhood was acceptable from Rîșcani sector from 2026-11-19 to 2026-11-20; CET-1 zone was a hard exclusion from 2026-11-02 to 2026-11-20; east Rîșcani streets were blacklisted from 2026-11-01 to 2026-11-20.

## 2026-11-20 10:11 (morning run empty results message)

**Publication workflow change.** Owner rule change 2026-11-20 10:11 Europe/Chisinau.

### Morning run empty results posting
When the daily morning (~09:00) search run completes and finds **NO fresh eligible PASS or MAYBE** listings, it now posts **ONE short plain-text Russian message** to the Telegram channel 'real estate investments' stating that nothing new was found.

**Message must include:**
- Statement that no new results were found under current filters
- One-line filter summary: €80–100k, ≥55 m², ≤€2100/m², floors 2–8, Rîșcanovca / Centru / Komsomol lake–Valea Morilor
- One-line coverage summary: sources and pages scanned (honest if partial)

**Important notes:**
- **Not posted** if the run itself failed (failure reported in the Grok Bot chat instead)
- The message **adds nothing to posted_ids** (it's not a listing)
- **12:00/19:00 buffer runs unchanged**: empty buffer => no message posted

**Previous rule (superseded 2026-11-20):** morning run finding no fresh results => no messages anywhere.

### Files updated
- FILTERS.md: §13 Publication & Telegram posting rules (NEW section)
- AGENTS.md: Empty results handling (NEW section)
- .cursor/rules/real-estate-filters.mdc: TELEGRAM POSTING rule
- CHANGELOG.md: this entry

### All other criteria unchanged
All filter rules unchanged: budget, location, area, price/m², construction year, floors, quotas, etc.

## 2026-11-20 00:46 (minimum area raised to ≥55 m²)

**R-AREA tightened.** Owner rule change 2026-11-20 00:46 Europe/Chisinau.

### Minimum total area raised to ≥55 m²
- **R-AREA**: Minimum total area **≥55 m²** inclusive (was ≥45 m²). Any room count.
- Known area <55 m² => **FAIL R-AREA** (excluded immediately)
- Unknown area => verdict **MAYBE** with area verification required
- Applies to apartments and houses, all locations, all statuses (PASS/MAYBE/buffer)

### Files updated
- FILTERS.md: R-AREA (≥55 m² with historical note), Russian summary
- .cursor/rules/real-estate-filters.mdc: R-AREA (≥55 m²)
- templates/listing-check.md: R-AREA (≥55 m²)
- CHANGELOG.md: this entry

### All other criteria unchanged
- Budget €80k–100k, location (Centru/Rîșcanovca/lake), €2,100/m², white ≤€90k, year ≥2000, two sanitary rooms for new builds, floors 2–8, quotas ≤10 PASS / ≤10 MAYBE — all unchanged

**Historical context:** Minimum area was ≥40 m² until 2026-11-08 18:32, then ≥45 m² from 2026-11-08 18:32 to 2026-11-20 00:46.

## 2026-11-19 23:29–23:31 (max price lowered to €100k + location narrowed)

**R-BUDGET and R-LOC major tightening.** Owner rule change 2026-11-19 23:28–23:31 Europe/Chisinau.

### 1. Max price lowered to €100k (corrected at 23:31)
- **R-BUDGET**: Maximum asking price **€100,000 inclusive** (was €160,000). Asking >€100k => **FAIL R-PRICE**. Below €80k stays FAIL.
- **R-BANDS**: Single price band **€80,000–100,000 inclusive** (was €80,000–160,000).
- White variant cap **≤€90,000** unchanged (still below general cap).
- **Correction note**: Initially set to €125,000 at 23:29, corrected to €100,000 at 23:31.

### 2. Locations narrowed to Rîșcanovca neighbourhood only (not whole Rîșcani sector)
- **R-LOC**: Acceptable locations now **strictly**:
  - **Centru** (whole sector) — unchanged
  - **Rîșcanovca / Рышкановка neighbourhood ONLY** (not the whole Rîșcani sector; other parts of Rîșcani such as Poșta Veche, Petricani, Cartierul Moldova / Socoleni direction are **EXCLUDED**)
  - **Buiucani area around Komsomol lake / Valea Morilor** (~0–20 min walk including adjacent Buiucani) — unchanged
- **Everything else => FAIL R-EXCL-AREA**, including:
  - Other parts of Rîșcani sector (Poșta Veche, Petricani, Cartierul Moldova / Socoleni direction, etc.)
  - Other Buiucani (outside lake area)
  - Telecentru, all Ciocana, Botanica, suburbs
- **Unclear micro-district** (e.g. only 'Rîșcani' without street/map) => **MAYBE** with map check.
- **R-EXCL-BOTANICA** updated: Poșta Veche clarified as part of Rîșcani sector but not Rîșcanovca neighbourhood.

### 3. All other criteria unchanged
- €/m² cap ≤€2,100 unchanged
- Area ≥45 m² unchanged
- White variant ≤€90k unchanged
- Construction year ≥2000 (with series exceptions) unchanged
- Two sanitary rooms for new builds unchanged
- Floors 2–8 unchanged
- PASS ≤10 / MAYBE ≤10 quotas unchanged
- CET-1 zone (Tudor Vladimirescu allowed per 19.11 19:42) and street blacklists unchanged

### Files updated
- FILTERS.md: R-BUDGET (€100k with correction note), R-BANDS (€80k–100k), R-LOC (Rîșcanovca neighbourhood only with historical note), R-EXCL-BOTANICA (Poșta Veche clarification), §12 reporting format (€80k–100k), Russian summary (both rules)
- .cursor/rules/real-estate-filters.mdc: R-BUDGET (€100k), R-BANDS (€80k–100k), R-LOC (Rîșcanovca neighbourhood)
- AGENTS.md: reporting format (€80k–100k)
- templates/listing-check.md: R-BUDGET (€100k), R-BANDS (€80k–100k), R-LOC (Rîșcanovca neighbourhood)
- CHANGELOG.md: this entry

**Historical context:** Price band was €80k–160k from 2026-11-18 to 2026-11-19 23:29. Whole Rîșcani sector was acceptable from 2026-11-18 to 2026-11-19 23:29.

## 2026-11-19 (Tudor Vladimirescu removed from blacklist)

**R-BLACKLIST-CET1**: str. Tudor Vladimirescu (Chișinău, Rîșcani) removed from the CET-1 zone blacklist. Owner rule change 2026-11-19 19:42 Europe/Chisinau.

### What changed
- **str. Tudor Vladimirescu is now ALLOWED** in Chișinău Rîșcani. Evaluate addresses on this street by all other filters; they can be PASS or MAYBE.
- **Being near CET-1 becomes informational only** — flagged as "близко к ТЭЦ-1" but NOT an exclusion.
- **Rest of R-BLACKLIST-CET1 unchanged**: str. Nicolae Dimo in Chișinău Rîșcani still excluded; any other address within ~800 m of CET-1 (≈47.0331, 28.8635), excluding Tudor Vladimirescu, still excluded.

### Files updated
- FILTERS.md: R-BLACKLIST-CET1 (updated date, reworded rule, updated boundary examples, added historical note), §5 rejected listings (annotated Tudor Vladimirescu 3 entry), Russian summary (updated blacklist description)
- .cursor/rules/real-estate-filters.mdc: R-BLACKLIST-CET1 (updated with date, new wording)
- listings/rejected.md: annotated Tudor Vladimirescu 3 entry with re-evaluation note
- CHANGELOG.md: this entry

### Historical context
str. Tudor Vladimirescu in Chișinău Rîșcani was excluded as part of the CET-1 zone blacklist from 2026-11-02 to 2026-11-19. Tudor Vladimirescu 3 listing (73 m², 3/3, €84.9k, https://999.md/ro/105513974) was rejected on 2026-11-02 for R-BLACKLIST-CET1; may now be re-evaluated if still live.

All other filters unchanged from 2026-11-18 major overhaul.

## 2026-11-18 23:18 (pre-2000 series exception extended)

**R-YEAR and R-SANITARY exception extended** to include three additional building series/types:

### Pre-2000 series exception expanded
- **R-YEAR**: Extended the list of pre-2000 building series/types allowed when explicitly confirmed:
  - Previously (2026-11-15): Stalinka, seria 102 (cotileț)
  - **Now also includes (2026-11-18 23:18):**
    - **seria 143**
    - **Czech series/project** (чешский проект / proiect cehesc)
    - **Individual projects** (индивидуальный проект / proiect individual)
  
- Same conditions apply to all exception objects:
  - Must be explicitly confirmed in the listing
  - Unconfirmed → verdict **MAYBE**
  - Commissioned status satisfied (R-EXCL-NEWBUILD)
  - Flag building-age checks required
  
- Other pre-2000 series (135, MS/Varnița, brejnevka, hrușciovka, etc.) remain **FAIL**.

### R-SANITARY exemption updated
- **R-SANITARY**: Exception updated to include all R-YEAR exception objects. R-YEAR exception objects (Stalinka, seria 102, seria 143, Czech series/project, individual projects) are NOT subject to the two-separate-sanitary-rooms requirement.

### Files updated
- FILTERS.md: R-YEAR (extended exception list with historical note), R-SANITARY (updated exception reference), Russian summary (both rules)
- templates/listing-check.md: R-YEAR and R-SANITARY checklists
- .cursor/rules/real-estate-filters.mdc: R-YEAR and R-SANITARY condensed rules
- CHANGELOG.md: this entry

All other filters unchanged from 2026-11-18 major overhaul.

## 2026-11-18 (major overhaul - single price band + stricter locations + new rules)

**Comprehensive filter update with five major changes:**

### 1. Price band restructure (2026-11-18 23:05)
- **R-BUDGET**: Asking price **€80,000–160,000 inclusive** (single band). Above €160k or below €80k excluded immediately.
- **R-BANDS**: Changed from 2 price blocks (€40k–110k, >€110k–140k) to **ONE single price band €80k–160k**.
- **Quotas updated**: PASS up to 10 listings; MAYBE separate status up to 10 TOTAL (single band).
- White variant cap remains **≤€90,000** (unchanged from 2026-11-08).
- Reporting format updated throughout FILTERS.md, AGENTS.md, templates/listing-check.md.

### 2. €/m² cap raised (2026-11-18 23:06)
- **R-PRICE-M2**: Maximum asking price per m² raised to **≤€2,100/m²** (was €1,900/m²). Anything above €2,100/m² excluded immediately.

### 3. Location restrictions tightened (2026-11-18 23:05)
- **R-LOC**: Now **ONLY** three acceptable locations:
  - Centru (whole sector)
  - Rîșcani / Рышкановка (whole sector)
  - Buiucani area around Komsomol lake / Valea Morilor (~0–20 min actual walking route, including adjacent parts of Buiucani)
- **Everything else now EXCLUDED**:
  - Other parts of Buiucani (outside the ~0–20 min lake area)
  - **Telecentru** (previously acceptable; now excluded as of 2026-11-18)
  - **All Ciocana** (including former Port Mall/Rîșcani edge exception, revoked 2026-11-12)
  - Botanica, Poșta Veche, all suburbs
- Unclear location → MAYBE with map check.

### 4. Street blacklist expanded
- **R-BLACKLIST** extended with four new streets (whole streets, apartments and houses, all statuses):
  - **str. Drumul Viilor** (added 2026-11-13)
  - **str. Valea Dicescu** (added 2026-11-15)
  - **str. Calea Ieșilor** (added 2026-11-15)
  - **str. Grădinilor** (added 2026-11-15)
- Existing blacklist unchanged: east Rîșcani pocket (Florării, str-la Florării, Pajurii, Forăriei, Zimbrului), CET-1 zone.

### 5. Building age exception added (2026-11-15)
- **R-YEAR**: Added **Stalinka and seria 102 (cotileț) exception** — these buildings are allowed even if constructed before 2000, **only when explicitly confirmed**.
- Unconfirmed Stalinka/102 → MAYBE; other pre-2000 series remain FAIL.
- Flag building-age checks required.

### 6. Sanitary rooms requirement added (2026-11-15)
- **R-SANITARY** (NEW): New builds (construction year ≥2000) require **TWO separate sanitary rooms** (separate toilet + separate bathroom/shower).
- Explicitly combined bathroom → FAIL.
- 999.md "Grup sanitar: 1" without explicit text description → UNKNOWN → MAYBE with verification.
- **Exception:** Stalinka and seria 102 (R-YEAR exception objects) are NOT subject to this two-room requirement.

### 7. Unknown finish rule clarified (2026-11-17)
- **R-EXCL-UNFINISHED**: If finishing is not explicitly stated, the white variant cap is UNKNOWN → verdict MAYBE with verification requirement, not FAIL. Only an explicitly stated white variant >€90k is FAIL.

### Files updated
- FILTERS.md: R-BUDGET, R-BANDS, R-PRICE-M2, R-LOC, R-BLACKLIST, R-YEAR (Stalinka/102 exception), R-SANITARY (NEW), R-EXCL-UNFINISHED (unknown finish), §12 reporting format, Russian summary
- AGENTS.md: reporting format (single band)
- .cursor/rules/real-estate-filters.mdc: all rule updates
- templates/listing-check.md: R-BUDGET, R-BANDS, R-PRICE-M2, R-LOC, R-BLACKLIST, R-YEAR, R-SANITARY (NEW), R-EXCL-UNFINISHED
- CHANGELOG.md: this comprehensive entry

All other filters unchanged: white variant €90k cap, area ≥45m², elevator informational, mansards/houses allowed, MAYBE publication with ≤10 separate quota, sources registry, etc.

## 2026-11-08 (evening - Durlești removed + white €90k + area ≥45m² + benchmark removed)

**Supersedes earlier 2026-11-08 changes.** Four mandatory changes:

### 1. Durlești removed (18:28)
Durlești removed from search entirely (all property types, all statuses PASS/MAYBE/buffer).

- **R-EXCL-SUBURB**: Durlești now EXCLUDED (no exceptions). Revokes Nov 7 2026 suburb exception and Nov 8 morning homonymous street permission. Durlești was temporarily allowed 2026-11-07 to 2026-11-08 18:28; revoked 2026-11-08 18:28 Europe/Chisinau.
- **R-LOC**: Removed Durlești from acceptable locations. Priority: Centru, Rîșcani, Buiucani within 0–20 min walk of Valea Morilor/Komsomol lake. Acceptable: other Buiucani, Telecentru, Ciocana near Port Mall/Rîșcani edge.
- **R-BLACKLIST-CET1 boundary examples updated**: str. Tudor Vladimirescu and str. Nicolae Dimo in Durlești now EXCLUDED (R-EXCL-SUBURB suburb exclusion). Chișinău Rîșcani same streets remain EXCLUDED (R-BLACKLIST-CET1 CET-1 zone). Unclear locality → MAYBE until resolved; do NOT assume Chișinău.
- **Locality verification unchanged**: must verify locality/address from listing, not bare street name matching.
- **999.md search method updated**: sectors note changed from "ensure Durlești not omitted" to "Chișinău sectors only; suburbs excluded."
- **Historical note preserved**: Durlești temporary allowance 2026-11-07 to 2026-11-08 18:28 documented in changelog and rules (not erased).

### 2. White variant cap lowered to €90k (18:32)
- **R-EXCL-UNFINISHED**: White variant (variantă albă) asking price cap **≤€90,000 inclusive** (supersedes €110,000 cap from 2026-11-07). White variant asking >€90,000 is FAIL. Applies to apartments and houses, all locations, all statuses (PASS/MAYBE/buffer). Uses asking price, not hypothetical discounted offers. Boundary: €90,000 = PASS, €90,001 = FAIL.
- **Historical note preserved**: cap was €110,000 from 2026-11-07 to 2026-11-08 18:32; superseded by €90,000 cap 2026-11-08 18:32.

### 3. Minimum area increased to 45m² (18:32)
- **R-AREA**: Total area **≥45 m²** (supersedes ≥40 m² from 2026-11-02). Anything below 45 m² is FAIL. Applies to all listings, any room count, all statuses (PASS/MAYBE/buffer).
- **Historical note preserved**: was ≥40 m² from 2026-11-02 to 2026-11-08 18:32; superseded by ≥45 m² 2026-11-08 18:32.

### 4. Benchmark removed entirely (18:33)
- **Matei Basarab 7/5 removed as benchmark.** Not used for valuation or comparison. Price each listing using real comparables per R-PRICE (§7).
- **Historical note preserved**: Matei Basarab 7/5, Rîșcani (https://999.md/ro/105332474, €66,900, 35 m², 3/5, ≈€1,911/m²) was used as benchmark until 2026-11-08 18:33; removed (below current R-AREA ≥45 m², likely pre-2000 construction).
- Updated FILTERS.md §6 (benchmark section), §12 reporting format (removed "comparison with benchmark"), AGENTS.md reporting format, templates/listing-check.md pricing section, listings/shortlist.md (Matei Basarab entry marked as removed), Russian summary.

### Files updated
- FILTERS.md: R-EXCL-SUBURB, R-LOC, R-BLACKLIST-CET1, R-EXCL-UNFINISHED (white €90k), R-AREA (≥45m²), §6 benchmark removed, §12 reporting format, Russian summary (white cap, area, districts, blacklist, benchmark removed)
- AGENTS.md: reporting format (removed benchmark comparison)
- .cursor/rules/real-estate-filters.mdc: white €90k, area ≥45m²
- templates/listing-check.md: R-BUDGET white €90k, R-AREA ≥45m², pricing section (removed benchmark)
- listings/shortlist.md: Matei Basarab marked as removed 2026-11-08 18:33

All other filters unchanged: 2 price blocks (€40k-110k, >€110k-140k), elevator informational, year ≥2000, mansards/houses allowed, MAYBE publication with ≤10 separate quota, sources registry, Rîșcani CET-1 zone blacklist, etc.

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
