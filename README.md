# real_estate_gold

Apartment search rules for Chișinău (Andrew Grini), structured for AI agents (Claude, Cursor, Grok Bot).

| File | Purpose |
|---|---|
| `FILTERS.md` | Single source of truth: all filter rules with stable IDs |
| `SOURCES.md` | Prioritized real estate source registry (owner-editable) |
| `AGENTS.md` | Workflow for any AI agent |
| `CLAUDE.md` | Claude Code entry point (imports AGENTS.md + FILTERS.md) |
| `.cursor/rules/real-estate-filters.mdc` | Cursor always-on rule |
| `listings/shortlist.md` | Candidates + benchmark |
| `listings/rejected.md` | Rejected listings with reasons |
| `templates/listing-check.md` | Checklist for one listing |
| `CHANGELOG.md` | Dated rule history |
