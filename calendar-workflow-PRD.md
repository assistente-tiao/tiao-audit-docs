# PRD — Calendar Workflow

## Objetivo
Consolidar múltiplas agendas do Roger em uma camada operacional única no Tião, com leitura de Outlook, Google Calendar da Cora e iCloud família, além de criação assistida de eventos no calendário correto com baixo erro.

## Problema
Hoje os compromissos estão espalhados em múltiplas fontes:
- Outlook pessoal
- Google Calendar da Cora
- iCloud família

Isso dificulta visão consolidada, detecção de conflitos, planejamento semanal e registro correto de eventos.

## Princípio
Ler tudo. Escrever com cautela. Aprender com uso.

## Interfaces
- Entrada: Discord em linguagem natural
- Saídas:
  - briefing diário às 7h
  - resumo dos próximos 7 dias
  - alertas de conflito
  - criação assistida de eventos
  - lembretes via Discord

## Fontes de calendário
### Leitura
- Outlook pessoal via ICS publicado
- Google Calendar da Cora via ICS/API
- iCloud família via webcal publicado

### Escrita
- Outlook pessoal
- iCloud família

### Fora do MVP
- Escrita no calendário da Cora
- Sync bidirecional entre calendários
- Cancelamento ou remarcação automática

## Regras de roteamento
### Outlook pessoal
Destino padrão para:
- médico
- compromissos pessoais
- amigos
- festas
- tarefas externas pessoais
- itens sem coordenação familiar explícita

### iCloud família
Destino para eventos com coordenação familiar / Letícia, especialmente:
- aniversários
- família
- sogro/sogra
- Jacareí
- praia
- viagens internacionais
- eventos do tipo "Leticia em Curitiba"
- eventos do tipo "Roger na Kaszek"
- itens que sinalizem ausência, deslocamento ou indisponibilidade entre o casal

### Trabalho
- sempre pedir confirmação antes
- nunca criar diretamente no calendário de trabalho no MVP

### Ambiguidade
No começo, o Tião deve perguntar mais. Exemplo:
- "isso vai pro iCloud da família ou pro Outlook pessoal?"

Depois, reduzir perguntas conforme aprender padrões do Roger.

## Categorias
- trabalho
- pessoal
- família
- viagem
- amigos
- festas
- outros

## Lembretes padrão
- trabalho: nenhum por padrão
- pessoal: 1 dia antes
- médico/saúde: 24h + 2h antes
- viagem: 1 semana antes + 24h antes
- família: 1 dia antes
- amigos/festas: 1 dia antes
- outros: 2h antes

## Briefing diário 7h
Formato recomendado:
- agenda do dia em ordem cronológica
- conflitos / sobreposições / janelas apertadas
- principais itens dos próximos 7 dias
- 1 alerta prático

## Regras de segurança
O Tião nunca faz sem permissão explícita:
- cancelar evento
- mover evento
- adicionar convidados
- criar evento no calendário de trabalho
- gerar Meet/Zoom
- convidar Letícia automaticamente sem confirmação
- escrever em calendário ambíguo sem perguntar no começo

## Arquitetura
### Componentes
1. Calendar Ingest
   - Outlook ICS
   - Cora ICS/API
   - iCloud webcal
2. Normalizer
   - formato comum de eventos
3. Conflict Engine
   - sobreposição e indisponibilidade
4. Router
   - decide Outlook, iCloud ou pedir confirmação
5. Discord Interface
   - recebe linguagem natural e responde
6. Memory Layer
   - aprende padrões com correções do Roger

## Ordem de implementação
### Fase 1 — Consolidação de leitura
- conectar Outlook ICS
- conectar Cora ICS/API
- conectar iCloud webcal
- normalizar eventos
- listar agenda consolidada

### Fase 2 — Inteligência operacional
- detecção de conflitos
- resumo do dia
- visão dos próximos 7 dias
- briefing das 7h

### Fase 3 — Escrita assistida
- criar no Outlook
- criar no iCloud
- perguntar quando houver ambiguidade
- aplicar lembretes padrão

### Fase 4 — Aprendizado
- registrar correções
- reduzir perguntas
- melhorar roteamento

## O que está fora do MVP
- sync entre calendários
- edição automática de eventos existentes
- cancelamento automático
- criação em calendário de trabalho
- Meet/Zoom automático
- integração sofisticada via API em tudo

## Risco principal
O maior risco é semântico: a agenda do Roger carrega significado contextual que precisa ser aprendido com uso, e não só inferido por nome de evento.
