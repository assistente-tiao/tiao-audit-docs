# Position Bootstrap Spec

## Goal
Load the initial current-state portfolio into the project without using transaction-led accounting.

## Input Model
Operator provides, per position:
- ticker
- quantity
- average price (local currency)
- broker
- currency
- optional sector
- optional company name
- optional analyst assignment placeholder

## Bootstrap Flow
1. Operator provides the current position set.
2. System writes rows into `Posicoes`.
3. Missing optional metadata is left blank or inferred later by dedicated cards.
4. Daily job enriches prices, FX, and portfolio metrics after bootstrap.

## Required Fields for Bootstrap
- ticker
- quantity
- average price local
- currency

## Optional Fields at Bootstrap
- company name
- sector
- broker
- analyst
- thesis status

## Rules
- Current positions are authoritative, not transaction history.
- No transaction reconstruction in V1.
- Input tickers must be preserved exactly as operator provides them.
- USD positions must remain in local price with BRL conversion handled later.

## Validation
- no duplicate ticker rows unless explicitly intended
- quantity must be positive for long-only V1
- average price must be non-negative
- currency must be BRL or USD in V1
