# portfolio-analytics

## Purpose
Compute the V1 portfolio analytics used by Sheets and Discord outputs.

## Inputs
- BRL-normalized position dataset
- benchmark snapshots
- sector labels from Sheets
- optional simple beta inputs

## Outputs
- portfolio-level analytics block
- position-level analytics block
- winners/losers list
- benchmark comparison snapshot

## V1 Scope
- daily PnL
- cumulative PnL
- concentration by position
- concentration by sector
- simple beta by position
- simple portfolio beta
- FX exposure
- top winners
- top losers

## Rules
- Consolidated outputs must be BRL.
- Missing beta remains explicit null.
- Sector aggregation depends on sheet-maintained sector labels.
- No Sharpe/Sortino/VaR/Max Drawdown in V1.

## Failure Handling
- If beta is unavailable, continue analytics without blocking the rest.
- If FX conversion is missing for a USD asset, mark analytics run invalid for portfolio totals.

## Validation
- Sum of position weights must reconcile with total portfolio value.
- Winners/losers must be limited to current positions.
- FX exposure must reconcile to USD-denominated holdings only.
