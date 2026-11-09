---
id: AILAB-PROMPT-007-CI-DEMO
version: 1.0.0
jira_key: AILAB-8
temp: LAB-07
phase: "1"
kind: vscode-issue-as-prompt
executor: vscode
locale: pt-BR
status: draft
created: "2026-11-08 21:42 America/Sao_Paulo"
supersedes: null
---

# AILAB-PROMPT-007-CI-DEMO — [LAB-07] CI snapshot + demo 5 min + README ANP

**Tipo:** Issue-as-a-Prompt (**vscode**). Não confundir com prompts futuros de runtime/agent/evals em `prompts/runtime/`. 
**Jira:** [AILAB-8](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-8) · Parent: AILAB-1 · Fase: 1

## Objetivo
CI sem live ANP; demo 5 min; README atribuição/limites/fase2.

## Contexto
- Repo: https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab (docs/prompts publicados neste repositório; implementação de app ainda não iniciada).
- Dados: API ANP GLP + corpus oficial; FakeProvider só testes rotulados.
- ADRs: **Proposto**. Issues: **A fazer**.
- Mapa: `docs/map/EPIC-TASK-MAP.md` · Manifesto: `docs/map/jira-manifest.json`.

## Inputs
- 06-RUNBOOK-DEMO; goldens.

## Precondições
- AILAB-7.

## Output esperado
- Workflow CI; script demo; README honesto.

> Não inventar implementação nem resultados: este arquivo é o **contrato do trabalho**. Evidências → `templates/EXECUTION-RECORD.md`.

## Testes / verificação
- CI verde; demo uma vez.

## Definition of Done
- [ ] CI·demo·gaps explícitos

## Proibições
- Live CI; alegar app GitHub↔Jira; 
- Sem dados pessoais/clientes/legacy indevido; snapshot ANP mínimo.
- Sem provisioning Azure/Databricks / gastos não autorizados.
- Sem Done automático; sem issues duplicadas; sem comentários externos como mensagens.

## Escalonamento
- Falha CI → corrigir sem inventar dados.

## Rastreabilidade
| Campo | Valor |
| --- | --- |
| prompt_id | `AILAB-PROMPT-007-CI-DEMO` |
| version | `1.0.0` |
| path | `prompts/vscode/AILAB-PROMPT-007-CI-DEMO.v1.md` |
| jira | AILAB-8 |
| blocked_by | AILAB-7 |
| blocks | AILAB-9, AILAB-10 |
