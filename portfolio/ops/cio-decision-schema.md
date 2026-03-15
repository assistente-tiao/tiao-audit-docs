# CIO Decision Schema

## Canonical fields
- decision_id
- decision_date
- scope (`position` | `factor` | `portfolio`)
- subject
- action (`build-now` | `hold` | `trim` | `exit` | `watch-trigger` | `preserve-cash`)
- previous_state
- new_state
- rationale
- supporting_evidence
- key_risk
- invalidation_condition
- next_review
- status (`open` | `superseded` | `closed`)

## State-transition logic
### Position states
- monitor
- review
- decide
- actioned
- closed

### Rules
- every `decide` event should produce a log entry
- every material CIO action should identify what invalidates it
- a newer decision can supersede an older one, but should not erase it
- `hold` is a real decision, not a non-decision
