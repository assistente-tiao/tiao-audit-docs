# Module Spec — macro-monitor

## Purpose
Maintain the macro dashboard used by daily and weekly reporting.

## Inputs
- macro series definition
- source mapping
- update timestamp

## Outputs
- normalized macro rows for Google Sheets
- status flags for stale/failed metrics

## Dependencies
- BCB API
- yfinance
- macro dashboard schema

## Edge Cases
- missing BCB response
- holiday gaps
- inconsistent units
- stale market-linked series

## Validation
- all metrics have source, unit, timestamp, status
- BR macro and market macro remain distinguishable by source
- no metric is silently dropped from the batch
