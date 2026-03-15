# Google Sheets Schema — Portfolio Intelligence Agent

## Source of Truth Rule
Google Sheets is the operational source of truth for portfolio state in V1.

## Tabs
1. `Posicoes`
2. `Macro Dashboard`
3. `Teses e Status`
4. `Analytics`
5. `Config`

## Tab 1 — Posicoes
### Columns
- A `ticker` — manual
- B `empresa` — manual
- C `setor` — manual
- D `analista` — manual initially, later agent-maintained after persona mapping
- E `broker` — manual
- F `moeda` — manual (`BRL` or `USD`)
- G `quantidade` — manual
- H `preco_medio_local` — manual
- I `preco_atual_local` — agent daily update
- J `fx_brl` — agent daily update (`1` for BRL assets)
- K `valor_atual_brl` — formula
- L `custo_total_brl` — formula
- M `pnl_brl` — formula
- N `pnl_pct` — formula
- O `variacao_dia_pct` — agent daily update
- P `peso_pct` — formula
- Q `status_tese` — manual / agent read-only semantics in V1
- R `ultima_atualizacao` — agent daily update timestamp

### Formulas
- `valor_atual_brl = quantidade * preco_atual_local * fx_brl`
- `custo_total_brl = quantidade * preco_medio_local * fx_brl`
- `pnl_brl = valor_atual_brl - custo_total_brl`
- `pnl_pct = IF(custo_total_brl=0,0,pnl_brl/custo_total_brl)`
- `peso_pct = IF(total_carteira=0,0,valor_atual_brl/total_carteira)`

## Tab 2 — Macro Dashboard
### Rows / Fields
- Selic
- IPCA 12m
- USD/BRL
- DXY
- Brent
- VIX
- Treasury 10Y
- Ibovespa
- S&P 500
- Timestamp

## Tab 3 — Teses e Status
### Columns
- ticker
- status_tese
- kill_switch
- ultima_revisao
- proximo_catalisador
- conviccao
- notas

### Rule
- Kill switch is manual input.
- Agent may read and alert, never overwrite automatically in V1.

## Tab 4 — Analytics
### Blocks
- total carteira em BRL
- top 5 posições
- concentração por setor
- beta simples por posição
- beta simples da carteira
- FX exposure
- top winners
- top losers
- benchmark snapshot

## Tab 5 — Config
### Fields
- benchmark_br = IBOV
- benchmark_us = S&P 500
- hurdle = IPCA+15
- daily_run_time = 23:00 BRT
- sunday_run_time = 09:00 BRT

## Ownership Rules
- Manual fields are only changed by the operator.
- Agent-updated fields are only changed by daily/weekly routines.
- Formula fields are never overwritten by the agent.
