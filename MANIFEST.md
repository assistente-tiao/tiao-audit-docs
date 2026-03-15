# Manifesto do Export de Auditoria

## Inclusão deliberada
Foram considerados relevantes para diagnóstico:
- `AGENTS.md`, `SOUL.md`, `USER.md`, `TOOLS.md`, `HEARTBEAT.md`, `MEMORY.md`
- docs de calendário e projetos anteriores que possam mostrar padrões de operação
- todo o diretório `portfolio/`
- documentação e dados do `dashboard/` relevantes para kanban
- memórias de trabalho em `memory/`

## Exclusão deliberada
Não devem entrar no repositório remoto, salvo ordem explícita do usuário:
- caches (`.mypy_cache`, `.pytest_cache`, `node_modules`)
- binários e arquivos enormes sem valor diagnóstico direto
- credenciais, tokens, segredos, arquivos sensíveis não documentais

## Motivação
O objetivo não é “embelezar” o sistema, mas expor material suficiente para diagnóstico externo.
