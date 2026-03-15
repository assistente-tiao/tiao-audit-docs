# Architecture — Portfolio Intelligence Agent

## Core Decisions
- Source of truth: Google Sheets
- Delivery surface: Discord
- Runtime: OpenClaw on existing VPS
- Market data: yfinance
- Macro BR data: BCB API
- PnL base currency: BRL

## Topology
- Workspace contains specs, skills, scripts, knowledge, reports.
- Cron-style scheduled tasks run daily and weekly.
- Outputs are written to Sheets and summarized in Discord.

## Constraints
- Use positions current-state bootstrap, not transaction-led accounting.
- No crypto in V1.
- No Sharpe/Sortino/VaR/Max Drawdown in V1.
