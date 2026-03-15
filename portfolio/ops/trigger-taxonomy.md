# Trigger Taxonomy

## Purpose
Stable trigger classes for active portfolio monitoring.

## Trigger classes
### T1 — Earnings / operating update
Used when results, KPIs, guidance, or management commentary materially change the operating picture.

### T2 — Macro / factor shock
Used when rates, FX, commodity, inflation, growth, or liquidity move enough to alter portfolio assumptions.

### T3 — Regulatory / policy event
Used for ANEEL, housing policy, banking regulation, tariffs, export controls, tax, sanctions, or wrapper-rule changes.

### T4 — Price / valuation dislocation
Used when price moves are large enough to force re-underwriting, or when upside/downside changes materially.

### T5 — Thesis break / kill-switch risk
Used when evidence suggests the core investment logic may be weakening or invalid.

### T6 — Concentration / funding event
Used when sizing, correlation, or a source-of-funds decision changes portfolio-level risk.

## Escalation rules
- `observe` — note only; no CIO action yet
- `review` — owner must reassess and update the panel
- `decide` — CIO decision required

## Response time target
- P1 positions: same day or next market day
- P2 positions: within 2 business days
- P3 positions: within the week unless the move is extreme
