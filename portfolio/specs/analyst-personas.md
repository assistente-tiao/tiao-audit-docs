# Analyst Persona Derivation Workflow

## Goal
Define the final analyst set from the real portfolio rather than locking it prematurely.

## Permanent Personas
- CIO
- Macro

## Derivation Process
1. Read actual current positions after bootstrap.
2. Group positions by practical coverage clusters.
3. Create the smallest analyst set that covers the portfolio without overlap-heavy fragmentation.
4. Assign each position a primary analyst.
5. Record analyst scope, watch metrics, and writing style.

## Initial Clustering Heuristics
- Brasil utilities / infraestrutura
- Brasil materiais / commodities
- Brasil consumo / real estate / industrials
- US tech / semis / AI
- financeiro / crédito when relevant

## Rules
- Start from the portfolio, not from a fixed theory of seven analysts.
- Prefer fewer analysts with clear jurisdiction over many thin personas.
- Every analyst must own a concrete coverage universe.
- New analysts can be added later only if a new coverage cluster justifies it.

## Output Per Analyst
- name
- coverage scope
- representative tickers
- key metrics watched
- voice / style notes

## Validation
- every position has exactly one primary analyst
- no analyst exists without at least one real coverage target
- CIO and Macro remain cross-portfolio layers, not replacements for sector ownership
