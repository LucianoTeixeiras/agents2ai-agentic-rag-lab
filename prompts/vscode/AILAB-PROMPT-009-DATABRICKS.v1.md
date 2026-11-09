---
id: AILAB-PROMPT-009-DATABRICKS
version: 1.0.0
jira_key: AILAB-10
temp: LAB-09
phase: "2"
kind: vscode-issue-as-prompt
executor: vscode
locale: pt-BR
status: draft
created: "2026-11-08 21:42 America/Sao_Paulo"
supersedes: null
---

# AILAB-PROMPT-009-DATABRICKS — [LAB-09][Fase 2] Databricks Bronze/Silver/Gold + MLflow mínimo

**Tipo:** Issue-as-a-Prompt (**vscode**). Não confundir com prompts futuros de runtime/agent/evals em `prompts/runtime/`. 
**Jira:** [AILAB-10](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-10) · Parent: AILAB-1 · Fase: 2

## Objetivo
Databricks Bronze→Silver→Gold + MLflow mínimo se viável; Vector Search só se útil/disponível — não requisito artificial.

## Contexto
- Repo: https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab (docs/prompts publicados neste repositório; implementação de app ainda não iniciada).
- Dados: API ANP GLP + corpus oficial; FakeProvider só testes rotulados.
- ADRs: **Proposto**. Issues: **A fazer**.
- Mapa: `docs/map/EPIC-TASK-MAP.md` · Manifesto: `docs/map/jira-manifest.json`.

## Inputs
- Autorização acesso/DBUs; JSON/páginas ANP.

## Precondições
- AILAB-8; acesso autorizado.

## Output esperado
- Pipeline mínimo **ou** bloqueio; tabela real vs planejado.

> Não inventar implementação nem resultados: este arquivo é o **contrato do trabalho**. Evidências → `templates/EXECUTION-RECORD.md`.

## Testes / verificação
- Colunas honestas; sem alegar VS falso.

## Definition of Done
- [ ] Pipeline autorizado OU bloqueio; sem VS artificial

## Proibições
- Gastar DBUs sem ok; UC/VS produção sem evidência.
- Sem dados pessoais/clientes/legacy indevido; snapshot ANP mínimo.
- Sem provisioning Azure/Databricks / gastos não autorizados.
- Sem Done automático; sem issues duplicadas; sem comentários externos como mensagens.

## Escalonamento
- Sem workspace → bloquear e documentar.

## Rastreabilidade
| Campo | Valor |
| --- | --- |
| prompt_id | `AILAB-PROMPT-009-DATABRICKS` |
| version | `1.0.0` |
| path | `prompts/vscode/AILAB-PROMPT-009-DATABRICKS.v1.md` |
| jira | AILAB-10 |
| blocked_by | AILAB-8 |
| blocks | — |
