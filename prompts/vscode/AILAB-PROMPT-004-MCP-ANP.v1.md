---
id: AILAB-PROMPT-004-MCP-ANP
version: 1.0.0
jira_key: AILAB-5
temp: LAB-04
phase: "1"
kind: vscode-issue-as-prompt
executor: vscode
locale: pt-BR
status: draft
created: "2026-11-08 21:42 America/Sao_Paulo"
supersedes: null
---

# AILAB-PROMPT-004-MCP-ANP — [LAB-04] LangGraph + MCP ANP GLP read-only (API/snapshot)

**Tipo:** Issue-as-a-Prompt (**vscode**). Não confundir com prompts futuros de runtime/agent/evals em `prompts/runtime/`. 
**Jira:** [AILAB-5](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-5) · Parent: AILAB-1 · Fase: 1

## Objetivo
MCP real read-only allowlist + LangGraph; cliente ANP paginado timeout/retry/backoff/cache; snapshot default; live opt-in; métricas em código.

## Contexto
- Repo: https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab (docs/prompts publicados neste repositório; implementação de app ainda não iniciada).
- Dados: API ANP GLP + corpus oficial; FakeProvider só testes rotulados.
- ADRs: **Proposto**. Issues: **A fazer**.
- Mapa: `docs/map/EPIC-TASK-MAP.md` · Manifesto: `docs/map/jira-manifest.json`.

## Inputs
- Swagger ANP; ADR-002/006; snapshot mínimo sanitizado.

## Precondições
- AILAB-3.

## Output esperado
- Cliente+MCP+grafo; testes snapshot. Não inventar resultados runtime.

> Não inventar implementação nem resultados: este arquivo é o **contrato do trabalho**. Evidências → `templates/EXECUTION-RECORD.md`.

## Testes / verificação
- Count código; escopo explícito; host só ANP/snapshot.

## Definition of Done
- [ ] MCP real·count código·pin SDK (na implementação futura)

## Proibições
- Write tools; dump nacional; métricas via LLM.
- Sem dados pessoais/clientes/legacy indevido; snapshot ANP mínimo.
- Sem provisioning Azure/Databricks / gastos não autorizados.
- Sem Done automático; sem issues duplicadas; sem comentários externos como mensagens.

## Escalonamento
- ANP down → snapshot only.

## Rastreabilidade
| Campo | Valor |
| --- | --- |
| prompt_id | `AILAB-PROMPT-004-MCP-ANP` |
| version | `1.0.0` |
| path | `prompts/vscode/AILAB-PROMPT-004-MCP-ANP.v1.md` |
| jira | AILAB-5 |
| blocked_by | AILAB-3 |
| blocks | AILAB-6 |
