# Reporting Contract — Discord Outputs

## Objective
Define deterministic Discord output formats for V1 daily alerts and sunday briefing.

## Delivery Surface
- Primary surface: Discord DM / direct thread with investor
- Format must favor compact summary first, appendix after

## Daily Alert Contract
### Trigger Conditions
- Position move greater than configured threshold
- Kill switch triggered manually in Sheets
- Daily close job failed partially or fully

### Daily Alert Sections
1. Headline
2. What changed
3. Impact on portfolio
4. Next action / watch item

### Daily Alert Format
- No tables
- Bullets only
- Max 8 bullets in summary
- If no material alert, do not send daily discretionary noise

## Sunday Briefing Contract
### Required Section Order
1. Panorama macro
2. Performance snapshot da carteira
3. Top winners / losers
4. Bloco por analista
5. Releases / eventos da semana
6. Implicações para a carteira
7. Apêndice

### Section Rules
#### 1. Panorama macro
- Explain the week in Brazil first, then global, then portfolio relevance.

#### 2. Performance snapshot
- Show BRL portfolio view.
- Reference IBOV, S&P and CDI/Selic snapshot.

#### 3. Top winners / losers
- Only current positions.
- State whether move appears thesis-consistent or thesis-threatening.

#### 4. Bloco por analista
- One block per active analyst persona.
- 2–5 bullets each.
- No filler if a sector had no relevant change.

#### 5. Releases / eventos
- Highlight only releases, earnings, press releases or macro items relevant to existing positions or near-term thesis.

#### 6. Implicações para a carteira
- Must end with explicit takeaways.
- No generic summary without judgment.

#### 7. Apêndice
- Extra detail for deeper reading.
- Can be longer than summary but must stay structured.

## Tone Rules
- Portuguese formal
- Direct
- Opinionated when implication is clear
- Explicitly state uncertainty when confidence is low
- Not investment recommendation language

## Formatting Constraints
- No markdown tables
- Use bullets and short subheadings
- Summary should fit normal Discord reading without wall-of-text behavior

## Failure Reporting
- If a job fails, message must include:
  - what failed
  - what succeeded
  - whether portfolio data may be stale
  - next corrective step
