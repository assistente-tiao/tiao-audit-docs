# Google Sheet Bootstrap Spec

## Goal
Create the operational Google Sheet for the portfolio project in the Tião Google account.

## Spreadsheet Name
- `Portfolio Intelligence Agent`

## Required Tabs
1. `Posicoes`
2. `Macro Dashboard`
3. `Teses e Status`
4. `Analytics`
5. `Config`

## Bootstrap Sequence
1. Create spreadsheet in authenticated Google account.
2. Rename default sheet and create remaining tabs.
3. Write headers for each tab exactly as defined in schema.
4. Seed formula columns in `Posicoes`.
5. Seed config defaults in `Config`.
6. Verify write access and readback.
7. Persist spreadsheet ID to project config.

## Required Defaults
### Config Tab
- benchmark_br = IBOV
- benchmark_us = S&P 500
- hurdle = IPCA+15
- daily_run_time = 23:00 BRT
- sunday_run_time = 09:00 BRT

## Permissions Rule
- Spreadsheet must remain writable by the Tião authenticated account.
- Additional sharing is optional and explicit, not implicit.

## Validation Checklist
- all required tabs exist
- headers match schema
- formula columns evaluate without syntax error
- sheet readback succeeds after bootstrap
- spreadsheet ID is captured for later jobs
