# P32 Audit — Monitoring Trigger Design

## Current trigger needs identified
### Position-level
- earnings / results
- guidance change
- management change
- regulatory event
- abnormal price move
- thesis kill switch
- valuation compression/expansion
- company-specific execution event

### Portfolio-level
- factor concentration worsening
- macro regime change
- FX shock
- rates shock
- commodity shock
- cross-position correlation stress
- cash deployment / funding decision

## Design constraint
A trigger system that is too detailed becomes unreadable and dies. The right design is:
- small stable taxonomy
- explicit mapping from trigger to action
- one row per position plus one layer for shared factors

## Operational implication
The trigger system should not only say **what happened**.
It must imply **who reacts**, **how fast**, and **whether CIO action is required**.
