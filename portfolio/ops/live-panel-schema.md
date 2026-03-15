# Live Position Panel Schema

## Purpose
Define the canonical structure of the active-management panel used by the CIO.

## Primary table columns
| Column | Meaning |
|---|---|
| ticker | Canonical asset identifier |
| empresa | Human-readable asset name |
| owner | Principal analyst / CIO owner |
| sleeve | Coverage sleeve / sector |
| role | Core / Watchlist / Tactical / Hedge / Liquidity / Special |
| quantidade | Current quantity or unit count |
| preco_medio | Average cost |
| moeda | BRL / USD |
| valor_base | Base value in local currency |
| thesis_status | Current thesis state |
| cio_action | Current portfolio action from CIO |
| monitor_priority | Monitoring intensity |
| key_risk | Main risk worth watching now |
| next_event | Next material event expected |
| next_review | Date or trigger for mandatory review |
| notes | Brief operating note |
| active_decision_ref | Optional pointer to latest relevant CIO decision |

## Status vocabulary
### thesis_status
- `pending` — no formal thesis yet
- `active` — thesis documented and intact
- `under-review` — thesis being re-evaluated
- `threatened` — thesis materially pressured
- `exited` — no longer active in portfolio

### cio_action
- `build-now` — add now / build position now
- `hold` — maintain current position
- `trim` — reduce position
- `exit` — close position
- `watch-trigger` — no action until trigger happens
- `preserve-cash` — do not reallocate into this now
- `n-a` — not applicable

### monitor_priority
- `P1` — highest attention / event-sensitive / concentration risk
- `P2` — important but not urgent
- `P3` — lighter monitoring

### role
- `core`
- `watchlist`
- `tactical`
- `hedge`
- `liquidity`
- `special`

## Rules
- one row per active position
- one principal owner per position
- no blank `cio_action` field
- `pending` thesis is allowed, but every pending position still needs a monitoring priority and current CIO action
- `next_review` can be a date or an event trigger label when exact date is unknown
