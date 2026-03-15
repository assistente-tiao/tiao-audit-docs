# Observability Spec — Portfolio Intelligence Agent

## Goal
Make every scheduled or manual run understandable without digging through raw logs.

## Required Run Metadata
Every run should record:
- run_id
- job_name
- started_at
- finished_at
- status (`success`, `partial`, `failed`)
- steps_completed
- failed_steps
- stale_data_flags
- operator_message_summary

## Required Failure Context
When a run fails or is partial, record:
- failing module
- failing source
- affected tickers or metrics
- whether Sheets may now be stale
- recommended next action

## Output Locations
- human summary in Discord when material
- machine-readable run log in workspace / project logs
- status reflected in Kanban only for development work, not routine production jobs

## Logging Rules
- Concise, structured, and timestamped
- No silent failures
- Partial success must be explicit
- Missing data must be marked, not skipped

## Daily Job Observability
- Report only on material movement, kill switch, or failure
- No routine noise if daily job completes without issue

## Sunday Job Observability
- Always produce a human-readable briefing
- If some sources fail, note what is stale in the appendix

## Validation
- Operator should be able to answer: what ran, what failed, what is stale, and what to do next.
