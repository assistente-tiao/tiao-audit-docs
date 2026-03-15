# macro-monitor

## Purpose
Collect and normalize core macro indicators relevant to the portfolio.

## Sources
- BCB API for Selic and IPCA
- yfinance for DXY, VIX, Treasury 10Y, Brent, USD/BRL, Ibovespa, S&P 500
- Optional web-search fallback for niche indicators later; not required for V1 core path

## Inputs
- macro indicator list
- run timestamp

## Outputs
- normalized macro rows for `Macro Dashboard`

## Rules
- BCB fields are authoritative for Selic and IPCA in V1.
- yfinance is authoritative for market-linked macro series in V1.
- Do not block the whole run if one macro series fails.
- Mark stale/error explicitly.

## Failure Handling
- Retry once for network/provider issue.
- Surface stale values with status metadata.
- If BCB is down, continue market-linked series and mark BR macro as stale.

## Validation
- Every macro row must carry source and timestamp.
- Unit must be explicit.
- No silent substitution between BCB and yfinance for the same metric.
