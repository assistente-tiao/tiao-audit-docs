# Sunday Briefing Job Spec

## Goal
Produce the weekly portfolio briefing with summary + appendix in Discord.

## Schedule
- Sunday, 09:00 BRT

## Inputs
- latest Sheets portfolio state
- macro dashboard snapshot
- analytics snapshot
- thesis status sheet
- weekly research findings for relevant positions/sectors/events

## Required Section Order
1. Panorama macro
2. Performance snapshot da carteira
3. Top winners / losers
4. Bloco por analista
5. Releases / eventos da semana
6. Implicações para a carteira
7. Apêndice

## Steps
1. Read latest portfolio and analytics state
2. Refresh relevant weekly macro/market context
3. Gather relevant releases, earnings, and press releases tied to current positions
4. Build analyst blocks from active coverage map
5. Compose concise Discord summary
6. Compose appendix for deeper reading
7. Send summary + appendix
8. Record run log

## Rules
- Focus on current positions first
- Brazil first, then global where relevant
- Every major section should connect back to portfolio implications
- No filler sector commentary with no real change

## Failure Handling
- if some research sources fail, note staleness in appendix and continue if core state exists
- if core portfolio state is missing, abort and alert operator
