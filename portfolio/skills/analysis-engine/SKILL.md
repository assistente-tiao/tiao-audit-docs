# analysis-engine

## Purpose
Generate portfolio-aware analysis outputs anchored in the knowledge base and current portfolio state.

## Supported Commands in V1
- `/deepdive [TICKER]`
- `/relatorio`
- `/macro`
- `/tese [TICKER]`
- `/valuation [TICKER]`
- `/risco`
- `/comite [tema]`

## Inputs
- current positions and thesis status from Sheets
- knowledge files from `portfolio/knowledge/`
- macro and market snapshots
- web research for current-week developments

## Rules
- Always anchor analysis in portfolio context.
- Prefer thesis update over generic company summary.
- Use web search only for material updates, results, releases, macro or sector signals.
- Do not fabricate multiples, guidance, or release content when source data is missing.
- End with explicit implication for the portfolio when relevant.

## Failure Handling
- If a knowledge file is missing, continue with explicit gap noted.
- If live research is unavailable, fall back to knowledge-base-only mode and state staleness.
- If ticker is not in portfolio, answer only if command permits out-of-portfolio analysis.

## Validation
- Output must distinguish fact, interpretation, and uncertainty.
- Output must not contradict thesis status without explaining why.
- Reports must stay concise-first, appendix-second.
