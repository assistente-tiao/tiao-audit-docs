# Analytics Contract — Portfolio Intelligence Agent (V1)

## Objective
Define the exact V1 portfolio analytics outputs, formulas, and benchmark references.

## Base Currency
- All consolidated portfolio outputs are expressed in BRL.

## Required V1 Metrics
1. Daily PnL (BRL)
2. Cumulative PnL (BRL)
3. Concentration by position (%)
4. Concentration by sector (%)
5. Simple beta by position
6. Simple portfolio beta
7. FX exposure (%)
8. Top winners
9. Top losers
10. Benchmark snapshot

## Position-Level Output Fields
- ticker
- sector
- value_brl
- weight_pct
- pnl_brl
- pnl_pct
- day_change_pct
- beta_reference
- beta_simple
- fx_exposed (`true|false`)

## Portfolio-Level Output Fields
- total_value_brl
- total_pnl_brl
- total_pnl_pct
- portfolio_beta_ibov
- portfolio_beta_spx
- fx_exposure_pct
- top_5_concentration_pct
- largest_position_ticker
- largest_position_weight_pct
- winners_list
- losers_list
- benchmark_ibov_change_pct
- benchmark_spx_change_pct
- benchmark_cdi_snapshot

## Formula Rules
### Daily PnL
- Sum of each position daily change in BRL.

### Cumulative PnL
- `sum(position.value_brl) - sum(position.cost_total_brl)`

### Concentration by Position
- `position.value_brl / total_portfolio_value_brl`

### Concentration by Sector
- `sum(position.value_brl where sector=X) / total_portfolio_value_brl`

### FX Exposure
- `sum(value_brl of USD-denominated positions) / total_portfolio_value_brl`

### Simple Beta by Position
- V1 uses a simple externally sourced beta or rolling simplified estimate when available.
- If unavailable, return `null` and surface as missing data.

### Simple Portfolio Beta
- Weighted sum of available position betas by portfolio weight.
- Missing betas do not get fabricated.

## Benchmarks
- Brazil benchmark: Ibovespa
- US benchmark: S&P 500
- Cash reference: CDI/Selic snapshot
- Long-term hurdle reference: IPCA + 15

## Output Locations
- Analytics tab in Google Sheets
- Sunday briefing summary in Discord
- Appendix section for detail expansion

## Explicitly Out of Scope for V1
- Sharpe
- Sortino
- VaR
- Max Drawdown
- Full factor model
- Automated DF ingestion

## Validation Rules
- Every analytics run must preserve BRL as the aggregate currency.
- Missing beta must be explicit, never inferred without basis.
- Top winners/losers must be derived from current portfolio only.
- Sector aggregation must use operator-maintained sector labels from Sheets.
