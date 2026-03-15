# portfolio-sheets

## Purpose
Read and write the Portfolio Intelligence Google Sheet as the operational source of truth.

## Inputs
- Spreadsheet ID
- Target tab
- Row payloads
- Update mode (`read`, `append`, `batch-update`)

## Responsibilities
- Read current positions from `Posicoes`
- Update price and analytics fields in batch
- Update macro dashboard values
- Read thesis status and kill-switch values without overwriting manual fields

## Rules
- Never overwrite manual columns.
- Never overwrite formula columns.
- Prefer batch writes over one-row-at-a-time updates.
- Preserve input ticker exactly as stored in the sheet.
- Write timestamps whenever agent-owned fields change.

## Failure Handling
- Abort on missing spreadsheet access.
- Surface partial-write failures with row context.
- Do not silently create new columns.

## Validation
- Confirm tab names exist before writes.
- Confirm required headers before writes.
- Confirm formulas remain intact after bootstrap.
