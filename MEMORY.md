# MEMORY.md

## Product / Project Decisions
- Calendar Workflow pivoted to Google Calendar as the single source of truth for writes.
- Outlook, iCloud, and Cora remain read-only sources for conflict checking, availability, and briefing.
- The Google calendar `Tião Calendar` is the canonical target calendar.
- Every created event must include `roger.oliveira.silva@outlook.com` as an attendee.
- Family/travel cases should also include `leticia@jea.com.br` as an attendee.
- Event creation should check for existing events in the same time window before inserting, to avoid duplicates.

## Stable Lessons
- Direct browser automation for Outlook/iCloud was judged too risky relative to its benefit for calendar writing.
- Setup, authentication, and documentation do not count as delivery; only a proven functional result counts.
- Never claim an event was created without proof from the raw command result plus a real calendar listing.
- Successful Google write capability was validated with `gws events insert` followed by `gws events list`; project status after that was mainly commit/push/PR wrap-up.
