# SDD — Portfolio Intelligence Agent

## Architecture Summary
- OpenClaw agent is the orchestration layer.
- Google Sheets is the source of truth for portfolio state.
- Discord is the primary output interface.
- Market and macro data come from yfinance + BCB, with minimal fallbacks.
- Knowledge files anchor thesis quality and reduce hallucination risk.

## Module Boundaries
1. portfolio-sheets
2. market-data
3. macro-monitor
4. analysis-engine
5. portfolio-analytics
6. scheduling and reporting

## Data Flow
1. Current positions are loaded into Google Sheets.
2. Daily close job fetches prices and macro inputs.
3. Sheets are updated.
4. Analytics derive BRL-normalized outputs.
5. Sunday job enriches with research and sends Discord summary + appendix.

## Execution Rules
- Cards are the execution driver.
- Dependencies are respected strictly.
- Work remains KISS: no advanced analytics outside backlog.
