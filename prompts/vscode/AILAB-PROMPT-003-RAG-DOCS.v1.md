---
id: AILAB-PROMPT-003-RAG-DOCS
version: 1.0.0
jira_key: AILAB-4
temp: LAB-03
phase: "1"
kind: vscode-issue-as-prompt
executor: vscode
locale: pt-BR
status: draft
created: "2026-11-08 21:42 America/Sao_Paulo"
supersedes: null
---

# AILAB-PROMPT-003-RAG-DOCS — [LAB-03] RAG: corpus oficial ANP (manual/metadata) + citações

**Tipo:** Issue-as-a-Prompt (**vscode**). Não confundir com prompts futuros de runtime/agent/evals em `prompts/runtime/`. 
**Jira:** [AILAB-4](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-4) · Parent: AILAB-1 · Fase: 1

## Objetivo
RAG lexical sobre corpus **oficial** ANP (manual/metadata); citations; abstém fora do corpus.

## Contexto
- Repo: https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab (docs/prompts publicados neste repositório; implementação de app ainda não iniciada).
- Dados: API ANP GLP + corpus oficial; FakeProvider só testes rotulados.
- ADRs: **Proposto**. Issues: **A fazer**.
- Mapa: `docs/map/EPIC-TASK-MAP.md` · Manifesto: `docs/map/jira-manifest.json`.

## Inputs
- Fontes SOURCES.md; texto derivado versionado; golden docs.

## Precondições
- AILAB-3 (docs no repo).

## Output esperado
- `data/corpus/anp/`; módulo retrieve; testes G01–G03. **Sem afirmar execução já feita.**

> Não inventar implementação nem resultados: este arquivo é o **contrato do trabalho**. Evidências → `templates/EXECUTION-RECORD.md`.

## Testes / verificação
- Citations oficiais; abstém; sem corpus inventado.

## Definition of Done
- [ ] Citations·abstém·testes verdes (quando implementado)
- [ ] Atribuição ANP

## Proibições
- Pedidos fictícios; embeddings pagos sem autorização; licença não confirmada como fato.
- Sem dados pessoais/clientes/legacy indevido; snapshot ANP mínimo.
- Sem provisioning Azure/Databricks / gastos não autorizados.
- Sem Done automático; sem issues duplicadas; sem comentários externos como mensagens.

## Escalonamento
- PDF pesado → texto pré-extraído com nota de origem.

## Rastreabilidade
| Campo | Valor |
| --- | --- |
| prompt_id | `AILAB-PROMPT-003-RAG-DOCS` |
| version | `1.0.0` |
| path | `prompts/vscode/AILAB-PROMPT-003-RAG-DOCS.v1.md` |
| jira | AILAB-4 |
| blocked_by | AILAB-3 |
| blocks | AILAB-6 |
