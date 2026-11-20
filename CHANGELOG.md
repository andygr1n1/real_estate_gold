# Changelog — filter rules

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
  - **Rîșcani / Рышкановка (whole sector)** EXCEPT **Poșta Veche** (Poșta Veche specifically excluded; Rîșcanovca, Petricani, Cartierul Moldova, Socoleni, Studenților, Ceucari, and all other parts of Rîșcani sector now allowed)
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
