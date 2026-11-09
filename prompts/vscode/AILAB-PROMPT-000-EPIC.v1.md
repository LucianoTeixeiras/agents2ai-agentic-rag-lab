---
id: AILAB-PROMPT-000-EPIC
version: 1.0.0
jira_key: AILAB-1
temp: EPIC-1
phase: "1+2"
kind: epic-context
executor: mixed
locale: pt-BR
status: draft
created: "2026-11-08 21:42 America/Sao_Paulo"
supersedes: null
---

# AILAB-PROMPT-000-EPIC — Lab ANP GLP: RAG docs oficiais + MCP API + FastAPI (fase 2 Azure/Databricks)

**Tipo:** Issue-as-a-Prompt (**mixed**). Não confundir com prompts futuros de runtime/agent/evals em `prompts/runtime/`. 
**Jira:** [AILAB-1](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-1) · Parent: — · Fase: 1+2

## Objetivo
Manter visão única do lab ANP GLP (RAG+MCP+FastAPI; fase2 Azure/Databricks autorizada). Orquestrar AILAB-2..10 sem implementação neste prompt.

## Contexto
- Repo: https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab (docs/prompts publicados neste repositório; implementação de app ainda não iniciada).
- Dados: API ANP GLP + corpus oficial; FakeProvider só testes rotulados.
- ADRs: **Proposto**. Issues: **A fazer**.
- Mapa: `docs/map/EPIC-TASK-MAP.md` · Manifesto: `docs/map/jira-manifest.json`.
- Este arquivo é contexto de épico, não tarefa executável isolada.

## Inputs
- Pacote docs-pack; manifesto; catálogo de prompts.

## Precondições
- Issues AILAB-1..10 existem; sem duplicar.

## Output esperado
- Épico coerente; referências a prompts filhos; DoD fase1 listado.

> Não inventar implementação nem resultados: este arquivo é o **contrato do trabalho**. Evidências → `templates/EXECUTION-RECORD.md`.

## Testes / verificação
- Conferir mapa e manifesto alinhados às issues.

## Definition of Done
- [ ] Mapa/manifesto/prompts referenciados
- [ ] Sem alegação de implementação

## Proibições
- Não implementar código via este prompt.
- Sem dados pessoais/clientes/legacy indevido; snapshot ANP mínimo.
- Sem provisioning Azure/Databricks / gastos não autorizados.
- Sem Done automático; sem issues duplicadas; sem comentários externos como mensagens.

## Escalonamento
- Conflito de escopo → Luciano.

## Rastreabilidade
| Campo | Valor |
| --- | --- |
| prompt_id | `AILAB-PROMPT-000-EPIC` |
| version | `1.0.0` |
| path | `prompts/vscode/AILAB-PROMPT-000-EPIC.v1.md` |
| jira | AILAB-1 |
| blocked_by | — |
| blocks | — |
