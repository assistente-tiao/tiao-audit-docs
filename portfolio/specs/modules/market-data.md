# Module Spec — market-data

## Purpose
Provide normalized market data payloads for positions and benchmarks in V1.

## Inputs
- current positions from Sheets
- market-data contract
- benchmark configuration

## Outputs
- position price payloads
- benchmark payloads
- row-level error states

## Dependencies
- yfinance
- market-data contract spec

## Edge Cases
- stale or missing ticker
- delisted ticker
- market holiday / missing close
- FX unavailable

## Validation
- payload keeps input ticker intact
- BR and US assets follow correct normalization rules
- missing data is explicit, never fabricated
