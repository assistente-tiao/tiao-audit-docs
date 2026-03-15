# Test Strategy and Quality Gates — V1

## Goal
Define the minimum test and verification strategy before implementation begins.

## Test Layers
1. Contract tests for Sheets schema and module output shapes
2. Fixture-based tests for market-data normalization
3. Fixture-based tests for analytics formulas and reconciliation
4. Smoke tests for Google Sheets access and scheduled job dry runs
5. Output-format checks for Discord summary structure

## Required Fixtures
- sample BR position rows
- sample US position rows
- sample FX series
- sample benchmark payloads
- sample thesis-status rows
- sample macro dashboard payloads

## Quality Gates
- no card implementing logic closes without at least one relevant validation artifact
- module output contracts must be tested against fixtures
- BRL aggregation math must reconcile
- Discord outputs must conform to reporting contract
- stale/missing data paths must be exercised at least once in tests or smoke checks

## Smoke Test Targets
- sheet bootstrap
- daily close job dry run
- sunday briefing dry run
- market-data fetch sanity
- BCB availability sanity

## Explicitly Not Required for V1
- vanity coverage thresholds
- full end-to-end integration environment before first implementation
- performance optimization tests unless a concrete bottleneck appears
