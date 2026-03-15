# Market Data Contract — Portfolio Intelligence Agent

## Objective
Provide deterministic daily market and macro inputs for V1 portfolio monitoring.

## Supported Assets in V1
- BR equities
- US equities
- ETFs
- cash proxies
- crypto excluded from V1

## Primary Sources
- yfinance for equities, ETFs, FX, indexes, Brent, VIX, Treasury 10Y
- BCB API for Selic and IPCA

## Ticker Normalization Rules
### BR assets
- Input ticker stored without suffix in Sheets, example: `SUZB3`
- Provider ticker for yfinance = `{ticker}.SA`

### US assets
- Input ticker stored as raw symbol, example: `NVDA`
- Provider ticker = same symbol

### FX and benchmarks
- USD/BRL = `BRL=X`
- Ibovespa = `^BVSP`
- S&P 500 = `^GSPC`
- Brent = `CL=F`
- DXY = `DX-Y.NYB`
- VIX = `^VIX`
- Treasury 10Y = `^TNX`

## Output Contract per Position
- ticker
- provider_ticker
- market
- currency_local
- price_local
- previous_close_local
- day_change_pct
- fx_brl
- price_brl
- as_of
- source
- status
- error

## BRL Normalization Rules
- BRL assets: `fx_brl = 1`
- USD assets: `fx_brl = USDBRL close`
- `price_brl = price_local * fx_brl`

## Macro Output Contract
- key
- value
- unit
- source
- as_of
- status
- error

## Error Handling
- If a single ticker fails, record `status=error` for that ticker and continue batch.
- If source responds with partial data, keep successful rows and annotate failed rows.
- If yfinance fails entirely, abort update and surface blocker to operator.
- If BCB fails, do not block price update; mark macro series as stale/error.

## Fallback Rules
- No secondary paid vendor in V1.
- Fallback is limited to retry once and surface operator-visible error.
- Do not silently substitute a different ticker.

## Validation Checks
- Every BR ticker must resolve to `.SA` before fetch.
- Every USD asset must produce non-1 `fx_brl`.
- `day_change_pct` must be computed from fetched local values, not estimated.
- Output rows must preserve input ticker exactly as stored in Sheets.
