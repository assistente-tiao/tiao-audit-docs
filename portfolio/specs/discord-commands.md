# Discord Commands Spec

## Goal
Define the supported V1 Discord command surface for the portfolio agent.

## Supported Commands
- `/relatorio`
- `/macro`
- `/deepdive [TICKER]`
- `/tese [TICKER]`
- `/valuation [TICKER]`
- `/risco`
- `/comite [tema]`

## Routing Rules
### `/relatorio`
- returns consolidated portfolio view
- uses latest sheet state + latest analytics + latest macro context

### `/macro`
- returns macro update with explicit portfolio implications

### `/deepdive [TICKER]`
- prioritizes current portfolio positions
- if ticker is outside portfolio, may answer but must state it is outside tracked portfolio

### `/tese [TICKER]`
- returns current thesis state anchored in knowledge base and latest status

### `/valuation [TICKER]`
- qualitative/semi-structured in V1
- must not invent precise fundamentals if not sourced

### `/risco`
- returns key portfolio risk map, concentration, FX and thesis pressure points

### `/comite [tema]`
- structured multi-voice output using CIO + relevant analyst frames when useful

## Output Rules
- concise first
- deeper detail only when useful
- no markdown tables
- always connect answer to current portfolio when relevant

## Side-Effect Rules
- commands are read/analyze by default
- no command mutates portfolio state unless explicitly designed later
- no command edits kill switches automatically

## Failure Handling
- if data is stale, say so explicitly
- if ticker knowledge is missing, continue with limited-confidence mode
