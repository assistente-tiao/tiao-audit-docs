# Module Spec — portfolio-sheets

## Purpose
Encapsulate all Google Sheets reads/writes for the portfolio project.

## Inputs
- Spreadsheet ID
- schema definition
- structured row payloads from market-data, macro-monitor, and analytics

## Outputs
- updated tabs in Google Sheets
- read payloads for positions, thesis status, and config values

## Dependencies
- Google Sheets access via gws / authenticated Google account
- google-sheets schema spec

## Edge Cases
- missing tab
- missing header
- insufficient permissions
- manual edits changed column order

## Validation
- headers are matched by name, not by blind column index when possible
- batch update succeeds or reports exact failed block
- manual / formula ownership rules are respected
