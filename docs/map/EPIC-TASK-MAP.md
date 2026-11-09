# Mapa legível — Epic + Tasks AILAB

**Gerado:** 2026-11-08 21:42 America/Sao_Paulo · **Status snapshot:** todos **A fazer** (não Done) · **ADRs:** Proposto 
**Publicação GitHub:** bloqueada nesta etapa (sem commit/PR). 

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

| Temp | Key | URL | Parent | Fase | Bloqueada por | Bloqueia | Prompt ID | Path | Status snap |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| EPIC-1 | AILAB-1 | [AILAB-1](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-1) | — | 1+2 | — | — | `AILAB-PROMPT-000-EPIC` v1.0.0 | `prompts/vscode/AILAB-PROMPT-000-EPIC.v1.md` | A fazer |
| LAB-01 | AILAB-2 | [AILAB-2](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-2) | AILAB-1 | 1 | — | AILAB-3 | `AILAB-PROMPT-001-REVIEW-DOCS` v1.0.0 | `prompts/vscode/AILAB-PROMPT-001-REVIEW-DOCS.v1.md` | A fazer |
| LAB-02 | AILAB-3 | [AILAB-3](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-3) | AILAB-1 | 1 | AILAB-2 | AILAB-4, AILAB-5 | `AILAB-PROMPT-002-BOOTSTRAP` v1.0.0 | `prompts/vscode/AILAB-PROMPT-002-BOOTSTRAP.v1.md` | A fazer |
| LAB-03 | AILAB-4 | [AILAB-4](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-4) | AILAB-1 | 1 | AILAB-3 | AILAB-6 | `AILAB-PROMPT-003-RAG-DOCS` v1.0.0 | `prompts/vscode/AILAB-PROMPT-003-RAG-DOCS.v1.md` | A fazer |
| LAB-04 | AILAB-5 | [AILAB-5](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-5) | AILAB-1 | 1 | AILAB-3 | AILAB-6 | `AILAB-PROMPT-004-MCP-ANP` v1.0.0 | `prompts/vscode/AILAB-PROMPT-004-MCP-ANP.v1.md` | A fazer |
| LAB-05 | AILAB-6 | [AILAB-6](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-6) | AILAB-1 | 1 | AILAB-4, AILAB-5 | AILAB-7 | `AILAB-PROMPT-005-FASTAPI-E2E` v1.0.0 | `prompts/vscode/AILAB-PROMPT-005-FASTAPI-E2E.v1.md` | A fazer |
| LAB-06 | AILAB-7 | [AILAB-7](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-7) | AILAB-1 | 1 | AILAB-6 | AILAB-8 | `AILAB-PROMPT-006-EVALS-GUARDRAILS` v1.0.0 | `prompts/vscode/AILAB-PROMPT-006-EVALS-GUARDRAILS.v1.md` | A fazer |
| LAB-07 | AILAB-8 | [AILAB-8](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-8) | AILAB-1 | 1 | AILAB-7 | AILAB-9, AILAB-10 | `AILAB-PROMPT-007-CI-DEMO` v1.0.0 | `prompts/vscode/AILAB-PROMPT-007-CI-DEMO.v1.md` | A fazer |
| LAB-08 | AILAB-9 | [AILAB-9](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-9) | AILAB-1 | 2 | AILAB-8 | — | `AILAB-PROMPT-008-AZURE-OPENAI` v1.0.0 | `prompts/vscode/AILAB-PROMPT-008-AZURE-OPENAI.v1.md` | A fazer |
| LAB-09 | AILAB-10 | [AILAB-10](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-10) | AILAB-1 | 2 | AILAB-8 | — | `AILAB-PROMPT-009-DATABRICKS` v1.0.0 | `prompts/vscode/AILAB-PROMPT-009-DATABRICKS.v1.md` | A fazer |

## Entregáveis por issue

### AILAB-1 — Lab ANP GLP: RAG docs oficiais + MCP API + FastAPI (fase 2 Azure/Databricks)
- Visão épica
- Orquestração AILAB-2..10
- Critérios DoD fase 1

### AILAB-2 — [LAB-01] Revisar e aceitar pacote documental ANP GLP
- Aceite humano ou lista de diffs
- ADRs permanecem Proposto até aceite

### AILAB-3 — [LAB-02] Bootstrap VS Code no repo existente (docs ANP)
- docs/ no repo
- README ANP
- .gitignore
- venv
- zero secrets

### AILAB-4 — [LAB-03] RAG: corpus oficial ANP (manual/metadata) + citações
- corpus oficial versionado
- retrieve+citations
- testes G01–G03

### AILAB-5 — [LAB-04] LangGraph + MCP ANP GLP read-only (API/snapshot)
- cliente ANP paginado
- snapshot mínimo
- MCP allowlist
- LangGraph

### AILAB-6 — [LAB-05] FastAPI E2E (snapshot default, live opt-in)
- /health
- /ask
- schemas
- e2e snapshot

### AILAB-7 — [LAB-06] Evals + tracing + guardrails + minimização de dados
- goldens
- trace_id
- redaction
- política snapshot

### AILAB-8 — [LAB-07] CI snapshot + demo 5 min + README ANP
- CI sem live
- demo 5 min
- README atribuição/limites

### AILAB-9 — [LAB-08][Fase 2] Azure OpenAI prático (credenciais/custo autorizados)
- adapter Azure autorizado OU bloqueio explícito
- rollback fase 1
- zero secrets

### AILAB-10 — [LAB-09][Fase 2] Databricks Bronze/Silver/Gold + MLflow mínimo
- pipeline B/S/G mínimo autorizado OU bloqueio
- MLflow mín. se viável
- VS opcional não artificial

> URLs Jira na tabela exigem login no Atlassian do mantenedor.

## Avisos

- Reprodução de **processo** ≠ determinismo de **saídas LLM**. Registrar versões de prompt/modelo/config e evidências; não esperar bit-identical answers.
- Não republicar cadastro ANP completo nem dados pessoais/clientes/legacy indevido.
- Fase 2 (AILAB-9/10): prática sob autorização — **sem provisioning/custos** nesta preparação.
