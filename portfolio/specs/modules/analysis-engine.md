# Module Spec — analysis-engine

## Purpose
Produce investor-facing analysis and briefing outputs from portfolio state, knowledge files, and current market context.

## Inputs
- Sheets data
- thesis status
- knowledge directory
- market-data and macro-monitor outputs
- optional web research

## Outputs
- Discord-ready summaries
- appendix/detail blocks
- thesis commentary by ticker or sector

## Dependencies
- portfolio/knowledge/
- reporting contract
- active analyst personas

## Edge Cases
- no knowledge file for ticker
- no relevant weekly news
- stale market data
- command references ticker outside portfolio

## Validation
- every output ties back to portfolio implications when relevant
- no unsupported numerical claims
- uncertainty and stale inputs are explicit
