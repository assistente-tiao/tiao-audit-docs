# Live Position Panel

Operational cockpit for active portfolio management.

## Current operating rules
- this panel is the daily management surface for the CIO
- every position must have an owner, thesis status, CIO action, and monitoring priority
- `pending` thesis does **not** mean unmanaged position
- `CAIXA` is treated as an active strategic position

## Current summary
- **Core / highest-importance cluster:** INBR32, ENGI4, EQTL3, ALOS3, SUZB3, KLBN4
- **Special structures needing explicit handling:** FIDC Microcrédito, FMP FGTS Eletrobrás
- **Tactical / lighter-monitoring cluster:** BRAV3, PLPL3, RAPT4, GMAT3, EWY, smaller US names
- **Immediate process gap:** all positions are still `pending` at thesis level, so the portfolio can now be monitored operationally, but not yet judged with full conviction discipline

## Source files
- panel data: `portfolio/ops/live-position-panel.csv`
- schema: `portfolio/ops/live-panel-schema.md`
- vocabulary: `portfolio/ops/status-vocabulary.md`
- trigger taxonomy: `portfolio/ops/trigger-taxonomy.md`
- trigger matrix: `portfolio/ops/trigger-matrix.csv`
- decision log: `portfolio/ops/cio-decision-log.csv`
- decision workflow: `portfolio/ops/cio-decision-workflow.md`
