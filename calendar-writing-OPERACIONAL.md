# Calendar Writing — Plano Operacional

## Objetivo
Implementar escrita real assistida no **Google (Tião Calendar)** usando a conta `assistente.tiao@gmail.com`, mantendo Outlook, Cora e iCloud como leitura.

## Regras de execução
- Executar em sequência, até blocker real ou decisão grande.
- Atualizar Roger a cada 30 min, ao concluir tarefa, ao mudar de contexto ou ao travar.
- Não abrir nova frente antes de fechar a atual.
- KISS: Google como escrita única, outros calendários como leitura.

## Checklist operacional

### Fase 1 — Escrita real no Google
- [x] M1 Autenticar `gws` com a conta `assistente.tiao@gmail.com`
- [x] M2 Confirmar acesso ao Google Calendar no VPS
- [x] M3 Criar o calendário `Tião Calendar`
- [x] M4 Criar um evento de teste simples no Tião Calendar
- [x] M5 Confirmar que o evento foi criado corretamente
- [x] M6 Registrar resultado/observações

### Fase 2 — Encapsular escrita no código
- [x] M7 Criar payload mínimo de criação de evento
- [x] M8 Criar interface `create_google_event(payload)`
- [x] M9 Retornar sucesso/erro estruturado

### Fase 3 — Integrar ao roteador
- [x] M10 Integrar Google Writer ao roteador
- [x] M11 Implementar fluxo: interpretar -> confirmar -> criar -> responder
- [x] M12 Aplicar regras: Google sem invite / Google + invite Letícia / confirmar trabalho
- [x] M13 Garantir mensagens claras de confirmação

### Fase 4 — Invite Letícia
- [x] M14 Confirmar o e-mail da Letícia a ser usado no invite
- [x] M15 Implementar inclusão de attendee quando aplicável
- [x] M16 Testar evento familiar com invite

### Fase 5 — Segurança e QA
- [x] M17 Bloquear trabalho sem confirmação
- [x] M18 Bloquear convidados além da Letícia sem permissão
- [x] M19 Evitar submit duplicado
- [x] M20 Adicionar tratamento de erro útil
- [x] M21 Adicionar/atualizar testes unitários
- [x] M22 Rodar smoke tests Google + leitura consolidada
- [x] M23 Validar briefing + conflitos após escrita
- [x] M24 Atualizar docs/checkpoint/learnings
- [ ] M25 Commit, push e PR final da escrita real

## Blockers reais que justificam pausa
- `gws` autenticado mas incapaz de criar/listar calendários/eventos no VPS
- `Tião Calendar` não aceita criação de eventos
- Falha estrutural do modelo de attendee/invite da Letícia
- Decisão grande sobre trabalho: criar ou não criar eventos de trabalho derivados no Google

## Critério de pronto
- Google cria evento real no Tião Calendar
- fluxo assistido em Google funciona ponta a ponta
- invite da Letícia funciona quando aplicável
- regras de segurança ativas
- QA básico passando
- docs e checkpoint atualizados
