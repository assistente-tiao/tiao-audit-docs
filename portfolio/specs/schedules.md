# Scheduling Spec — Portfolio Intelligence Agent

## Daily Close Job
- Schedule: 23:00 BRT
- Frequency: Monday to Friday
- Purpose: run after the latest relevant market close for the V1 portfolio mix

## Daily Job Steps
1. Fetch market data
2. Fetch macro dashboard inputs
3. Update Google Sheets
4. Compute V1 analytics
5. Send alert only if there is a material trigger or failure

## Sunday Briefing Job
- Schedule: 09:00 BRT on Sunday
- Purpose: generate weekly research and portfolio briefing

## Sunday Job Steps
1. Read latest portfolio state
2. Read macro and market snapshots
3. Run weekly research on relevant positions/sectors/events
4. Compile summary + appendix for Discord

## Timezone Rules
- Primary operator timezone: BRT
- Internal implementation may store UTC timestamps, but all human-facing schedules are described in BRT

## DST Handling
- V1 may use explicit timezone-aware scheduling rather than fixed UTC hardcoding
- Operator-facing expectation remains 23:00 BRT and Sunday 09:00 BRT

## Retry Rules
- One retry for transient failures in job execution
- If retry fails, mark job failed and surface operator-visible status
