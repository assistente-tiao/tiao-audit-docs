# market-data

## Purpose
Fetch deterministic daily market data for portfolio positions and key benchmarks.

## Sources
- yfinance for BR equities, US equities, ETFs, FX, indexes, Brent, VIX, Treasury 10Y
- BCB handled by macro-monitor, not here

## Inputs
- normalized ticker list
- benchmark list
- run date / timestamp

## Outputs
- JSON rows with local price, prior close, day change, BRL conversion metadata, source status, and timestamp

## Rules
- Use `.SA` suffix for BR assets only.
- Do not mutate stored tickers in the sheet.
- Return explicit errors for failed symbols.
- Continue partial batches unless provider-wide failure occurs.

## Failure Handling
- Retry once for provider/network failure.
- If all fetches fail, raise batch blocker.
- If individual tickers fail, return row-level error and continue.

## Validation
- Ensure every USD asset gets FX conversion data.
- Ensure every BR asset gets fx=1.
- Ensure benchmark outputs are included in every daily batch.
