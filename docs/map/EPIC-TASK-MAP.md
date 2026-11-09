# Mapa legível — Epic + Tasks AILAB

**Gerado:** 2026-11-09 14:21 America/Sao_Paulo · **Status snapshot:** todos **A fazer** (não Done) · **ADRs:** Proposto 
**Catálogo de prompts:** [`docs/prompts/README.md`](../prompts/README.md) (um arquivo por issue).

## Diagrama de dependências

```
AILAB-1 (Epic)
├── AILAB-2 [LAB-01] review docs ──► AILAB-3 [LAB-02] bootstrap
│ ├──► AILAB-4 [LAB-03] RAG docs ──┐
│ └──► AILAB-5 [LAB-04] MCP ANP ──┼──► AILAB-6 [LAB-05] FastAPI
│ └──► AILAB-7 [LAB-06] evals
│ └──► AILAB-8 [LAB-07] CI/demo
│ ├──► AILAB-9 [LAB-08] Azure (fase2)
│ └──► AILAB-10 [LAB-09] Databricks (fase2)
```

## Tabela

| Temp | Key | URL | Parent | Fase | Bloqueada por | Bloqueia | Prompt (chave) | Arquivo canônico | Status snap |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| EPIC-1 | AILAB-1 | [AILAB-1](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-1) | — | 1+2 | — | — | `AILAB-1` v2.0.0 (legado `AILAB-PROMPT-000-EPIC`) | [`epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md`](../prompts/epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md) | A fazer |
| LAB-01 | AILAB-2 | [AILAB-2](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-2) | AILAB-1 | 1 | — | AILAB-3 | `AILAB-2` v2.0.0 (legado `AILAB-PROMPT-001-REVIEW-DOCS`) | [`tasks/AILAB-2_revisar-pacote-documental-anp-glp.md`](../prompts/tasks/AILAB-2_revisar-pacote-documental-anp-glp.md) | A fazer |
| LAB-02 | AILAB-3 | [AILAB-3](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-3) | AILAB-1 | 1 | AILAB-2 | AILAB-4, AILAB-5 | `AILAB-3` v2.0.0 (legado `AILAB-PROMPT-002-BOOTSTRAP`) | [`tasks/AILAB-3_bootstrap-vscode-repo-existente.md`](../prompts/tasks/AILAB-3_bootstrap-vscode-repo-existente.md) | A fazer |
| LAB-03 | AILAB-4 | [AILAB-4](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-4) | AILAB-1 | 1 | AILAB-3 | AILAB-6 | `AILAB-4` v2.0.0 (legado `AILAB-PROMPT-003-RAG-DOCS`) | [`tasks/AILAB-4_rag-corpus-oficial-anp-citacoes.md`](../prompts/tasks/AILAB-4_rag-corpus-oficial-anp-citacoes.md) | A fazer |
| LAB-04 | AILAB-5 | [AILAB-5](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-5) | AILAB-1 | 1 | AILAB-3 | AILAB-6 | `AILAB-5` v2.0.0 (legado `AILAB-PROMPT-004-MCP-ANP`) | [`tasks/AILAB-5_langgraph-mcp-anp-glp-readonly.md`](../prompts/tasks/AILAB-5_langgraph-mcp-anp-glp-readonly.md) | A fazer |
| LAB-05 | AILAB-6 | [AILAB-6](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-6) | AILAB-1 | 1 | AILAB-4, AILAB-5 | AILAB-7 | `AILAB-6` v2.0.0 (legado `AILAB-PROMPT-005-FASTAPI-E2E`) | [`tasks/AILAB-6_fastapi-e2e-snapshot-live-optin.md`](../prompts/tasks/AILAB-6_fastapi-e2e-snapshot-live-optin.md) | A fazer |
| LAB-06 | AILAB-7 | [AILAB-7](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-7) | AILAB-1 | 1 | AILAB-6 | AILAB-8 | `AILAB-7` v2.0.0 (legado `AILAB-PROMPT-006-EVALS-GUARDRAILS`) | [`tasks/AILAB-7_evals-tracing-guardrails-minimizacao.md`](../prompts/tasks/AILAB-7_evals-tracing-guardrails-minimizacao.md) | A fazer |
| LAB-07 | AILAB-8 | [AILAB-8](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-8) | AILAB-1 | 1 | AILAB-7 | AILAB-9, AILAB-10 | `AILAB-8` v2.0.0 (legado `AILAB-PROMPT-007-CI-DEMO`) | [`tasks/AILAB-8_ci-snapshot-demo-readme.md`](../prompts/tasks/AILAB-8_ci-snapshot-demo-readme.md) | A fazer |
| LAB-08 | AILAB-9 | [AILAB-9](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-9) | AILAB-1 | 2 | AILAB-8 | — | `AILAB-9` v2.0.0 (legado `AILAB-PROMPT-008-AZURE-OPENAI`) | [`tasks/AILAB-9_fase2-azure-openai-pratico.md`](../prompts/tasks/AILAB-9_fase2-azure-openai-pratico.md) | A fazer |
| LAB-09 | AILAB-10 | [AILAB-10](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-10) | AILAB-1 | 2 | AILAB-8 | — | `AILAB-10` v2.0.0 (legado `AILAB-PROMPT-009-DATABRICKS`) | [`tasks/AILAB-10_fase2-databricks-medallion-mlflow.md`](../prompts/tasks/AILAB-10_fase2-databricks-medallion-mlflow.md) | A fazer |

## Entregáveis por issue

### AILAB-1 — Lab ANP GLP: RAG docs oficiais + MCP API + FastAPI (fase 2 Azure/Databricks)
Prompt: [`epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md`](../prompts/epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md)
- Visão épica
- Orquestração AILAB-2..10
- Critérios DoD fase 1

### AILAB-2 — [LAB-01] Revisar e aceitar pacote documental ANP GLP
Prompt: [`tasks/AILAB-2_revisar-pacote-documental-anp-glp.md`](../prompts/tasks/AILAB-2_revisar-pacote-documental-anp-glp.md)
- Aceite humano ou lista de diffs
- ADRs permanecem Proposto até aceite

### AILAB-3 — [LAB-02] Bootstrap VS Code no repo existente (docs ANP)
Prompt: [`tasks/AILAB-3_bootstrap-vscode-repo-existente.md`](../prompts/tasks/AILAB-3_bootstrap-vscode-repo-existente.md)
- pyproject + venv
- src/ e tests/ mínimos
- README ANP
- .gitignore e .env.example
- zero secrets

### AILAB-4 — [LAB-03] RAG: corpus oficial ANP (manual/metadata) + citações
Prompt: [`tasks/AILAB-4_rag-corpus-oficial-anp-citacoes.md`](../prompts/tasks/AILAB-4_rag-corpus-oficial-anp-citacoes.md)
- corpus oficial versionado
- retrieve+citations
- testes G01–G03

### AILAB-5 — [LAB-04] LangGraph + MCP ANP GLP read-only (API/snapshot)
Prompt: [`tasks/AILAB-5_langgraph-mcp-anp-glp-readonly.md`](../prompts/tasks/AILAB-5_langgraph-mcp-anp-glp-readonly.md)
- cliente ANP paginado
- snapshot mínimo
- MCP allowlist
- LangGraph

### AILAB-6 — [LAB-05] FastAPI E2E (snapshot default, live opt-in)
Prompt: [`tasks/AILAB-6_fastapi-e2e-snapshot-live-optin.md`](../prompts/tasks/AILAB-6_fastapi-e2e-snapshot-live-optin.md)
- /health
- /ask
- schemas
- e2e snapshot

### AILAB-7 — [LAB-06] Evals + tracing + guardrails + minimização de dados
Prompt: [`tasks/AILAB-7_evals-tracing-guardrails-minimizacao.md`](../prompts/tasks/AILAB-7_evals-tracing-guardrails-minimizacao.md)
- goldens
- trace_id
- redaction
- política snapshot

### AILAB-8 — [LAB-07] CI snapshot + demo 5 min + README ANP
Prompt: [`tasks/AILAB-8_ci-snapshot-demo-readme.md`](../prompts/tasks/AILAB-8_ci-snapshot-demo-readme.md)
- CI sem live
- demo 5 min
- README atribuição/limites

### AILAB-9 — [LAB-08][Fase 2] Azure OpenAI prático (credenciais/custo autorizados)
Prompt: [`tasks/AILAB-9_fase2-azure-openai-pratico.md`](../prompts/tasks/AILAB-9_fase2-azure-openai-pratico.md)
- adapter Azure autorizado OU bloqueio explícito
- rollback fase 1
- zero secrets

### AILAB-10 — [LAB-09][Fase 2] Databricks Bronze/Silver/Gold + MLflow mínimo
Prompt: [`tasks/AILAB-10_fase2-databricks-medallion-mlflow.md`](../prompts/tasks/AILAB-10_fase2-databricks-medallion-mlflow.md)
- pipeline B/S/G mínimo autorizado OU bloqueio
- MLflow mín. se viável
- VS opcional não artificial

> URLs Jira na tabela exigem login no Atlassian do mantenedor.

## Avisos

- Reprodução de **processo** ≠ determinismo de **saídas LLM**. Registrar versões de prompt/modelo/config e evidências; não esperar bit-identical answers.
- Não republicar cadastro ANP completo nem dados pessoais/clientes/legacy indevido.
- Fase 2 (AILAB-9/10): prática sob autorização — **sem provisioning/custos** nesta preparação.
