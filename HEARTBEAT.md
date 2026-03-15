# HEARTBEAT.md — Loop de trabalho autônomo

## Prioridade de cada ciclo
1. Mensagem direta do Roger ou menção direta
2. Incidente crítico de VPS/pipeline
3. Primeiro item de `## Em Andamento` em `TASKS.md`
4. Se `## Em Andamento` estiver vazio, primeiro item de `## Próximos`
5. Se não houver nada relevante, silêncio

## Execução
- Se houver tarefa ativa, execute o próximo passo material. Não fique só verificando.
- O objetivo de cada ciclo é mudar o estado do projeto de forma real.
- Não pare em leitura, pesquisa, setup, auth, planejamento ou status se não houver blocker real.

## O que conta como progresso real
- Código escrito ou corrigido
- Teste executado com resultado útil
- Bug corrigido
- Integração validada
- Arquivo de projeto atualizado após execução real
- Commit realizado

## O que NÃO conta sozinho como progresso
- Ler documentação
- Pesquisar
- Planejar
- Diagnosticar sem executar o próximo passo
- Fazer setup/auth sem usar
- Escrever status

## Status update
- Reporte no Discord apenas se:
  - houve avanço material
  - mudou de fase
  - surgiu blocker real
  - houve incidente de VPS
  - Roger enviou mensagem
- Formato:
  - `[HEARTBEAT] {tarefa} — feito: {X} | próximo: {Y}`
- Se não houve mudança material, não reporte.

## Bloqueios
- Se a mesma causa raiz travar a tarefa por 2 ciclos seguidos, reporte no Discord:
  - o que tentou
  - por que falhou
  - qual é o próximo passo proposto
- Não repetir o mesmo alerta na mesma sessão sem informação nova.

## Monitoramento
- VPS: alertar se:
  - disco >85%
  - serviço crítico caiu
  - erro recorrente aparecer no pipeline
- Discord:
  - se Roger mandar mensagem ou mencionar diretamente, responder
- Monitoramento não deve interromper o trabalho, exceto incidente crítico ou mensagem do Roger.

## Regras
- Não inventar tarefa nova.
- Não trocar de tarefa sem blocker real ou instrução do Roger.
- Não reabrir tarefa concluída sem motivo claro.
- Fora de 8h-22h: trabalhar silenciosamente, logar progresso no workspace, não notificar no Discord.
- Se não houver tarefa ativa nem incidente nem mensagem do Roger, fique em silêncio.

## Task Queue Check
0. Record heartbeat: POST http://localhost:3333/api/heartbeat via exec (curl -X POST)

1. Check in-progress tasks: GET http://localhost:3333/api/tasks and filter for status "in-progress" with pickedUp=true.
   For each in-progress task that has a subagentId:
   - Use sessions_list or /subagents info to check the sub-agent's status
   - If sub-agent COMPLETED: POST http://localhost:3333/api/tasks/{id}/status-check with { "status": "completed", "message": "<result summary from sub-agent>" }
   - If sub-agent FAILED: POST with { "status": "failed", "message": "<error details>" }
   - If sub-agent STILL RUNNING: POST with { "status": "running", "message": "Sub-agent active" }
   - If sub-agent NOT FOUND (crashed/disappeared) and task started > 15 min ago: POST with { "status": "timeout", "message": "Sub-agent session not found after 15min" }
   - If sub-agent NOT FOUND but task started < 15 min ago: POST with { "status": "running", "message": "Sub-agent recently started, waiting" }

2. Pick up new tasks: Fetch http://localhost:3333/api/tasks/queue?limit=capacity via exec (curl).
   Parse the JSON response — format: { tasks: [...], maxConcurrent, activeCount, remainingSlots }
   For each task in .tasks (already limited to available capacity):
   a. POST http://localhost:3333/api/tasks/{id}/pickup with { "subagentId": "<session-uuid>" }
   b. Spawn a sub-agent (sessions_spawn) with the task title + description as the prompt
   c. If a skill is assigned, tell the sub-agent to read that skill's SKILL.md first
   d. The sub-agent should call POST http://localhost:3333/api/tasks/{id}/complete with { "result": "<summary>" } when done, or { "error": "<what went wrong>" } if failed
