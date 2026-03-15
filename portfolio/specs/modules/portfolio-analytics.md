# Module Spec — portfolio-analytics

## Purpose
Transform normalized position and benchmark data into investor-facing portfolio analytics for V1.

## Inputs
- position rows from Sheets / portfolio-sheets
- market-data outputs
- benchmark references
- analytics contract

## Outputs
- analytics rows for Sheets
- summary block for Sunday briefing

## Dependencies
- analytics contract
- market-data contract
- Google Sheets schema

## Edge Cases
- missing beta
- missing FX for USD asset
- zero-value portfolio
- inconsistent sector labels

## Validation
- all aggregate outputs reconcile to BRL totals
- weight and concentration fields are mathematically consistent
- out-of-scope metrics are not introduced silently
