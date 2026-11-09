---
id: AILAB-PROMPT-001-REVIEW-DOCS
version: 1.0.0
jira_key: AILAB-2
temp: LAB-01
phase: "1"
kind: vscode-issue-as-prompt
executor: humano
locale: pt-BR
status: draft
created: "2026-11-08 21:42 America/Sao_Paulo"
supersedes: null
---

# AILAB-PROMPT-001-REVIEW-DOCS — [LAB-01] Revisar e aceitar pacote documental ANP GLP

**Tipo:** Issue-as-a-Prompt (**humano**). Não confundir com prompts futuros de runtime/agent/evals em `prompts/runtime/`. 
**Jira:** [AILAB-2](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-2) · Parent: AILAB-1 · Fase: 1

## Objetivo
Revisar pacote documental ANP (PRD, ADRs Proposto, threat, evals, runbook, backlog, mapa, catálogo) e aceitar ou listar diffs. Sem código.

## Contexto
- Repo: https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab (docs/prompts publicados neste repositório; implementação de app ainda não iniciada).
- Dados: API ANP GLP + corpus oficial; FakeProvider só testes rotulados.
- ADRs: **Proposto**. Issues: **A fazer**.
- Mapa: `docs/map/EPIC-TASK-MAP.md` · Manifesto: `docs/map/jira-manifest.json`.

## Inputs
- Tar/docs-pack atual; Jira AILAB; README; `map/`; `prompts/`.

## Precondições
- Pacote local disponível; issues não Done.

## Output esperado
- Aceite humano **ou** lista de ajustes; ADRs continuam Proposto até aceite explícito.

> Não inventar implementação nem resultados: este arquivo é o **contrato do trabalho**. Evidências → `templates/EXECUTION-RECORD.md`.

## Testes / verificação
- Checklist J1–J3; sem pedidos fictícios nos docs ativos; fase2 explícita.

## Definition of Done
- [ ] Aceite ou diffs registrados
- [ ] Registro de revisão (template REVIEW-RECONCILE)

## Proibições
- Não implementar; não provisionar; não Aceitar ADR automaticamente.
- Sem dados pessoais/clientes/legacy indevido; snapshot ANP mínimo.
- Sem provisioning Azure/Databricks / gastos não autorizados.
- Sem Done automático; sem issues duplicadas; sem comentários externos como mensagens.

## Escalonamento
- Diff pontual de ADR; não redesenhar épico sem Luciano.

## Rastreabilidade
| Campo | Valor |
| --- | --- |
| prompt_id | `AILAB-PROMPT-001-REVIEW-DOCS` |
| version | `1.0.0` |
| path | `prompts/vscode/AILAB-PROMPT-001-REVIEW-DOCS.v1.md` |
| jira | AILAB-2 |
| blocked_by | — |
| blocks | AILAB-3 |
