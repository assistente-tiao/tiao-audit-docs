# Validation Checklist — Market and Analytics Outputs

## Goal
Define the minimum checks that make market and analytics outputs trustworthy enough for V1.

## Market Data Checks
- every BR ticker resolves with `.SA`
- every USD ticker preserves original symbol
- every USD asset has non-1 `fx_brl`
- every BR asset has `fx_brl = 1`
- benchmark payloads exist for IBOV and S&P
- failed symbols are explicit, not omitted

## Portfolio Math Checks
- total portfolio value equals sum of position values in BRL
- every position weight reconciles to total value
- sector concentration equals grouped position totals
- cumulative PnL reconciles to value minus cost total

## Analytics Checks
- portfolio beta is weighted only from available betas
- missing beta remains explicit null
- winners/losers are limited to current positions
- FX exposure equals USD-denominated holdings share

## Output Consistency Checks
- all aggregate metrics are in BRL where applicable
- benchmark references are consistent with config
- stale data flags are surfaced if any source failed

## Failure Policy
- if reconciliation fails, analytics run must be marked invalid/partial
- if a single ticker fails, continue but mark affected outputs
