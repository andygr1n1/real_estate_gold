# SOURCES.md — Prioritized Real Estate Source Registry

Owner: Andrew Grini · Last updated: 2026-11-07

This registry lists real estate listing sources in **priority order** for apartment and house searches in Chișinău, Moldova.

## Purpose
- Provide agents with explicit, owner-editable source list
- Ensure consistent coverage across automated and manual searches
- Track source availability and coverage
- Allow easy addition/removal of sources by owner

## Instructions for Owner
To add a new source:
1. Add a new row to the table below
2. Set priority (1 = highest; sources checked in priority order)
3. Mark enabled: `yes` (search this source) or `no` (skip)
4. Fill in name, full HTTPS catalogue URL, coverage type
5. Add verification notes (date checked, any access issues)
6. Commit and push changes
7. Update routine prompts if needed

## Registry

| Priority | Enabled | Source Name | Full Catalogue URL | Coverage | Verification |
|:--------:|:-------:|-------------|-------------------|----------|--------------|
| 1 | yes | **999.md** | https://999.md/ro/list/real-estate/apartments-and-rooms | Apartments, houses | 2026-11-07: apartments URL reachable (200); houses URL path unknown (houses-and-villas returns 404) |
| 2 | yes | **Acces Imobil** | https://accesimobil.md | Unknown | 2026-11-07: homepage reachable (200); specific listing path unverified (404 on /ro/imobil/vanzare/chisinau) |
| 3 | yes | **Pro Imobil** | https://proimobil.md | Unknown | 2026-11-07: homepage reachable (200); specific listing path unverified (404 on /ro/imobil/vanzare/chisinau) |
| 4 | yes | **Realist.md** | https://www.realist.md/proprietati-de-vanzare/ | Unknown | 2026-11-07: properties for sale page reachable (200) |
| 5 | yes | **Romanescu** | https://romanescu.md | Unknown | 2026-11-07: homepage reachable (200); specific listing paths unverified (404 on /ro/vanzare and /ro/cumparare) |
| 6 | yes | **All Invest Realty (AIR)** | https://air.md/ro/vanzare | Unknown | 2026-11-07: sale page reachable (200) |

**Note:** "Unknown" coverage means apartments/houses coverage not yet verified from public catalogue. Agents must check actual available property types when searching each source.

## Search Agent Instructions

1. **Read this registry before each search run.**
2. **Process enabled sources in priority order** (lowest priority number first).
3. **Log which sources were checked and which were skipped** (disabled, temporarily unavailable, access blocked) with reasons in search results.
4. **Do NOT claim comprehensive coverage** unless all enabled sources were successfully searched.
5. **Continue on transient errors** (timeout, temporary unavailability) — mark source as checked/failed in logs, proceed to next source.
6. **Deduplicate cross-site listings** by comparing with 999.md and historical data (same address, agency, phone, description patterns).
7. **Never weaken filters** to increase results from any source — all R-* rules from FILTERS.md apply equally.
8. **No account signups, contacts, or messages** — public catalogue access only.
9. **Respect robots.txt and rate limits** — add delays between requests to same source.

## Source Addition Criteria

Before adding a new source, verify:
- Public access (no mandatory signup/login)
- Active Chișinău real estate listings
- Reliable availability (not frequently down)
- Sufficient coverage (not just 1-2 properties)

Do NOT add sources based on:
- Claimed market share without evidence
- Popularity/size rankings without verification
- Duplicate aggregators that only mirror 999.md

## Historical Notes

- **2026-11-07**: Initial registry created. Six sources listed: 999.md (primary), Acces Imobil, Pro Imobil, Realist.md, Romanescu, All Invest Realty. Coverage details and specific listing paths remain to be verified for most sources.
- **Capital Imobil**: Not added — domain unreachable during verification (2026-11-07).

## Disclaimer

- This registry reflects **owner preferences**, not verified market share or agency size.
- "Enabled" does not guarantee listings will be found — source may have no matching properties at search time.
- Specific API endpoints, GraphQL schemas, or search parameters are documented separately in agent implementation, not in this registry.
- Previously mentioned sources as "optional" does not mean they were searched in every historical run.
