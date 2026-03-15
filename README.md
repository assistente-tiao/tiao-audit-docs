# Audit Export — Tiao / OpenClaw Workspace

Este repositório/pacote foi preparado para auditoria externa do comportamento, regras, estrutura e operação do agente.

## Objetivo
Permitir que outra LLM ou humano avalie:
- regras de identidade e operação
- protocolos e frameworks
- arquitetura do projeto de investimentos
- camada operacional (`portfolio/ops`)
- backlog / artefatos do kanban
- documentos que possam explicar falhas de execução, autonomia e disciplina operacional

## Princípio de montagem
Este pacote foi preparado com **mínima curadoria**. A ideia é preservar evidência, inclusive documentação potencialmente redundante, conflitante, excessiva ou “ruidosa”, porque isso pode ser parte do problema.

## Estrutura principal incluída
- raiz do workspace: docs operacionais e de identidade
- `portfolio/`: arquitetura, specs, frameworks, protocolos, ops, teses
- `dashboard/`: artefatos do kanban e documentação do dashboard
- `memory/`: memória relevante de trabalho

## Observação
Segredos/credenciais não devem ser incluídos no push remoto. Fora isso, a lógica aqui é maximizar auditabilidade.
