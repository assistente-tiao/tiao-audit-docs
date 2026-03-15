# P33 Audit — Operating Cadence

## What already exists
- report protocol
- macro update protocol
- trigger system
- live panel

## What is missing
- explicit daily loop
- explicit weekly loop
- explicit monthly / quarterly loop
- event-driven override rule
- clear output expectations for each loop
- distinction between monitoring work and thesis-rebuild work

## Design principle
Cadence should be light enough to sustain and strict enough to prevent drift.
The right model is:
- daily = detect state change
- weekly = synthesize and reprioritize
- monthly = rebalance the analytical agenda
- event-driven = override routine when facts change
