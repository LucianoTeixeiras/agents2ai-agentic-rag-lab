---
id: AILAB-PROMPT-006-EVALS-GUARDRAILS
version: 1.0.0
jira_key: AILAB-7
temp: LAB-06
phase: "1"
kind: vscode-issue-as-prompt
executor: vscode
locale: pt-BR
status: draft
created: "2026-11-08 21:42 America/Sao_Paulo"
supersedes: null
---

# AILAB-PROMPT-006-EVALS-GUARDRAILS — [LAB-06] Evals + tracing + guardrails + minimização de dados

**Tipo:** Issue-as-a-Prompt (**vscode**). Não confundir com prompts futuros de runtime/agent/evals em `prompts/runtime/`. 
**Jira:** [AILAB-7](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-7) · Parent: AILAB-1 · Fase: 1

## Objetivo
Evals/goldens, tracing, guardrails, minimização snapshot; metas propostas.

## Contexto
- Repo: https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab (docs/prompts publicados neste repositório; implementação de app ainda não iniciada).
- Dados: API ANP GLP + corpus oficial; FakeProvider só testes rotulados.
- ADRs: **Proposto**. Issues: **A fazer**.
- Mapa: `docs/map/EPIC-TASK-MAP.md` · Manifesto: `docs/map/jira-manifest.json`.

## Inputs
- 05-TEST-EVAL-STRATEGY; ADR-006.

## Precondições
- AILAB-6.

## Output esperado
- Runner eval; política campos; sem live CI.

> Não inventar implementação nem resultados: este arquivo é o **contrato do trabalho**. Evidências → `templates/EXECUTION-RECORD.md`.

## Testes / verificação
- Smoke eval; negativos sintéticos.

## Definition of Done
- [ ] Eval smoke; snapshot mínimo documentado

## Proibições
- Dump; afirmar licença não confirmada.
- Sem dados pessoais/clientes/legacy indevido; snapshot ANP mínimo.
- Sem provisioning Azure/Databricks / gastos não autorizados.
- Sem Done automático; sem issues duplicadas; sem comentários externos como mensagens.

## Escalonamento
- MLflow completo → fase2 AILAB-10.

## Rastreabilidade
| Campo | Valor |
| --- | --- |
| prompt_id | `AILAB-PROMPT-006-EVALS-GUARDRAILS` |
| version | `1.0.0` |
| path | `prompts/vscode/AILAB-PROMPT-006-EVALS-GUARDRAILS.v1.md` |
| jira | AILAB-7 |
| blocked_by | AILAB-6 |
| blocks | AILAB-8 |
