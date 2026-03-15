# CLAUDE.md — Portfolio Intelligence Agent

## Fixed Development Rules
- Prefer explicit over clever.
- One task at a time unless dependency graph allows safe parallelism.
- Do not invent scope beyond cards in the Kanban.
- Treat Google Sheets as the only operational source of truth for portfolio state.
- PnL and consolidated outputs must be reported in BRL.
- Kill switches are manual inputs; the system may read and alert, never infer or overwrite them.

## Anti-Patterns
- Do not add analytics beyond V1 cards without an explicit backlog item.
- Do not build premium-data abstractions before validating yfinance and BCB coverage.
- Do not hide formulas or business rules in prose; put them in specs or code.
- Do not mark a card done without an artifact and a satisfied acceptance criterion.

## Playbooks
### New module spec
1. Read the card acceptance criteria.
2. Create the target spec file.
3. Define inputs, outputs, edge cases, and failure modes.
4. Keep the module independent from unrelated cards.
5. Reflect the result in the Kanban.

### Data integration
1. Define source and fallback.
2. Normalize identifiers.
3. Define output contract.
4. Define retry/error behavior.
5. Define validation checks.

## Quality Gates
- No card closes without a created/updated artifact.
- No implementation starts before the external-access readiness card is done.
- No report format changes without updating the reporting contract.

## Project Placeholders
- Spreadsheet ID: [PROJECT-SPECIFIC]
- Final analyst set: [PROJECT-SPECIFIC]
- Portfolio positions bootstrap: [PROJECT-SPECIFIC]
- Knowledge base source files: [PROJECT-SPECIFIC]
