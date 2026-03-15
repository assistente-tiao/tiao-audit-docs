# P31 Audit — Live Position Panel

## Current source files reviewed
- `portfolio/knowledge/positions-snapshot.csv`
- `portfolio/knowledge/portfolio-overview.md`
- `portfolio/knowledge/thesis-registry.md`
- `portfolio/committee/coverage-map.md`

## What already exists
### Strong
- current validated portfolio snapshot with quantities, PM, currency, dividends/proceeds and value base
- clear coverage ownership by analyst/persona
- thesis registry with initial prioritization
- overview with class totals and current snapshot date

### Weak
- no single operational panel combining ownership + thesis + action + next trigger
- thesis registry is still backlog-oriented, not monitoring-oriented
- no explicit CIO action field per position
- no monitoring priority or watch intensity field
- no next-event / next-review date field
- no distinction between core position, watchlist, hedge, liquidity, or special-situation role

## Required live-panel fields
- ticker
- company
- owner
- sleeve / sector
- role in portfolio
- quantity
- average cost
- currency
- base value
- thesis status
- current CIO action
- monitoring priority
- key risk
- next event
- next review
- notes

## Design decision
The live position panel should become the **operational cockpit**.
Other files remain specialized:
- snapshot = raw holdings view
- overview = class totals view
- thesis registry = thesis backlog / thesis state index
- coverage map = ownership map
- live panel = daily management surface
