# Daily Close Job Spec

## Goal
Run the daily portfolio update after the latest relevant market close and refresh Sheets + alerts.

## Schedule
- 23:00 BRT, Monday to Friday

## Inputs
- current `Posicoes` sheet
- market-data output
- macro-monitor output
- thesis status / kill-switch sheet

## Steps
1. Read current positions
2. Normalize tickers for market-data
3. Fetch prices and benchmarks
4. Fetch macro dashboard values
5. Update agent-owned fields in `Posicoes`
6. Update `Macro Dashboard`
7. Compute/update V1 analytics
8. Evaluate material alert conditions
9. Send Discord alert only if threshold or failure condition is met
10. Record run log

## Alert Conditions
- any position move greater than configured daily threshold
- any kill switch triggered manually
- full or partial job failure

## Failure Handling
- partial data updates are flagged explicitly
- if Sheets write fails, mark run failed and alert
- if macro fails but prices succeed, mark partial success

## Output
- updated Google Sheets tabs
- optional Discord daily alert
- run log entry
