# Tasks — calendar-workflow

## Dependency Graph
T1 ──→ T3 ──→ T5
T2 ──→ T3
T3 ──→ T4
T4 ──→ T6
T5 ──→ T6

(T1 e T2 podem rodar em paralelo. T3 depende de ambos. T4 e T5 dependem de T3. T6 depende de T4 e T5.)

## Tasks

### T1: Implementar ingest de calendários por URL (ICS/webcal)
- **Branch:** `feat/t1-calendar-ingest`
- **Status:** [ ] Pending
- **Files:** `calendar/ingest.py`, `calendar/models.py`, `tests/test_ingest.py`
- **Depends on:** none
- **Complexity:** medium
- **Acceptance criteria:** consegue carregar Outlook ICS, Cora ICS e iCloud webcal em um formato comum de entrada.

### T2: Definir config e carregamento seguro de credenciais/fontes
- **Branch:** `feat/t2-calendar-config`
- **Status:** [ ] Pending
- **Files:** `calendar/config.py`, `.env.example`, `tests/test_config.py`
- **Depends on:** none
- **Complexity:** small
- **Acceptance criteria:** URLs e configs carregam de arquivo seguro/ambiente sem hardcode e sem vazar secrets.

### T3: Normalizar eventos em modelo único
- **Branch:** `feat/t3-calendar-normalizer`
- **Status:** [ ] Pending
- **Files:** `calendar/normalize.py`, `calendar/models.py`, `tests/test_normalize.py`
- **Depends on:** T1, T2
- **Complexity:** medium
- **Acceptance criteria:** eventos de múltiplas fontes viram um modelo único com campos mínimos: título, início, fim, fonte, localização, descrição, all-day.

### T4: Implementar engine de conflitos e resumo consolidado
- **Branch:** `feat/t4-calendar-conflicts`
- **Status:** [ ] Pending
- **Files:** `calendar/conflicts.py`, `calendar/summary.py`, `tests/test_conflicts.py`
- **Depends on:** T3
- **Complexity:** medium
- **Acceptance criteria:** detecta sobreposição, proximidade perigosa e gera resumo do dia e próximos 7 dias.

### T5: Implementar roteador de destino e regras de negócio
- **Branch:** `feat/t5-calendar-router`
- **Status:** [ ] Pending
- **Files:** `calendar/router.py`, `calendar/rules.py`, `tests/test_router.py`
- **Depends on:** T3
- **Complexity:** medium
- **Acceptance criteria:** classifica evento e sugere Outlook, iCloud ou confirmação obrigatória conforme regras definidas com o Roger.

### T6: Integrar ao Discord com comandos em linguagem natural + briefing 7h
- **Branch:** `feat/t6-calendar-discord`
- **Status:** [ ] Pending
- **Files:** `calendar/discord_flow.md`, `calendar/briefing.py`, `tests/test_briefing.py`
- **Depends on:** T4, T5
- **Complexity:** medium
- **Acceptance criteria:** recebe pedido textual, devolve interpretação + sugestão de destino, e gera briefing diário utilizável.
