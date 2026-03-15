# External Access Readiness — GWS + yfinance + BCB

## Goal
Validate critical external dependencies before implementation begins.

## Dependency 1 — Google Sheets via authenticated Tião account
### Must Validate
- authenticated account is active
- spreadsheet create/read/write is possible
- spreadsheet ID can be captured

### Failure Impact
- blocks all sheet-backed implementation

## Dependency 2 — yfinance market data coverage
### Must Validate
- BR `.SA` tickers resolve
- US tickers resolve
- FX `BRL=X` resolves
- benchmark symbols resolve (`^BVSP`, `^GSPC`, `^VIX`, `^TNX`, `CL=F`, `DX-Y.NYB`)

### Failure Impact
- blocks market-data implementation or requires fallback decision

## Dependency 3 — BCB API availability
### Must Validate
- Selic series reachable
- IPCA series reachable
- response format can be parsed deterministically

### Failure Impact
- blocks macro-monitor completeness for BR macro layer

## Validation Output
A readiness check should produce:
- dependency name
- status (`ok`, `partial`, `failed`)
- tested endpoint/symbol
- timestamp
- blocker yes/no
- next action

## Execution Rule
- If GWS fails, stop implementation that depends on Sheets.
- If yfinance partially fails, document exactly which symbols fail before continuing.
- If BCB fails, continue only with explicit stale/missing macro note.
