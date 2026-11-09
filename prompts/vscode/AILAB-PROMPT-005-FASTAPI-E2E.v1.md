---
id: AILAB-PROMPT-005-FASTAPI-E2E
version: 1.0.0
jira_key: AILAB-6
temp: LAB-05
phase: "1"
kind: vscode-issue-as-prompt
executor: vscode
locale: pt-BR
status: draft
created: "2026-11-08 21:42 America/Sao_Paulo"
supersedes: null
---

# AILAB-PROMPT-005-FASTAPI-E2E — [LAB-05] FastAPI E2E (snapshot default, live opt-in)

**Tipo:** Issue-as-a-Prompt (**vscode**). Não confundir com prompts futuros de runtime/agent/evals em `prompts/runtime/`. 
**Jira:** [AILAB-6](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-6) · Parent: AILAB-1 · Fase: 1

## Objetivo
FastAPI `/health`+`/ask` integrando RAG+MCP; `data_mode` snapshot|live; FakeProvider só testes rotulados.

## Contexto
- Repo: https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab (docs/prompts publicados neste repositório; implementação de app ainda não iniciada).
- Dados: API ANP GLP + corpus oficial; FakeProvider só testes rotulados.
- ADRs: **Proposto**. Issues: **A fazer**.
- Mapa: `docs/map/EPIC-TASK-MAP.md` · Manifesto: `docs/map/jira-manifest.json`.

## Inputs
- Contratos 01-ARCHITECTURE; saídas de AILAB-4/5.

## Precondições
- AILAB-4 e AILAB-5.

## Output esperado
- API E2E snapshot; Swagger honesto.

> Não inventar implementação nem resultados: este arquivo é o **contrato do trabalho**. Evidências → `templates/EXECUTION-RECORD.md`.

## Testes / verificação
- Health 200; citation; métrica+escopo.

## Definition of Done
- [ ] E2E snapshot; live opt-in documentado; FakeProvider fora do demo default

## Proibições
- Live no CI; Azure na fase1.
- Sem dados pessoais/clientes/legacy indevido; snapshot ANP mínimo.
- Sem provisioning Azure/Databricks / gastos não autorizados.
- Sem Done automático; sem issues duplicadas; sem comentários externos como mensagens.

## Escalonamento
- MCP flaky → snapshot + nota README.

## Rastreabilidade
| Campo | Valor |
| --- | --- |
| prompt_id | `AILAB-PROMPT-005-FASTAPI-E2E` |
| version | `1.0.0` |
| path | `prompts/vscode/AILAB-PROMPT-005-FASTAPI-E2E.v1.md` |
| jira | AILAB-6 |
| blocked_by | AILAB-4, AILAB-5 |
| blocks | AILAB-7 |
