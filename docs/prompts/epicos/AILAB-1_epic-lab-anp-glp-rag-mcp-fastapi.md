---
jira_key: AILAB-1
tipo: Epic
lab: null
fase: "1+2"
epico_pai: null
executor: mixed
risco: null
status_jira_snapshot: A fazer
prompt_version: 2.0.0
legacy_prompt_id: AILAB-PROMPT-000-EPIC
supersedes: prompts/vscode/AILAB-PROMPT-000-EPIC.v1.md
atualizado: "2026-11-09 14:21 America/Sao_Paulo"
---

# AILAB-1 — Lab ANP GLP: RAG docs oficiais + MCP API + FastAPI (fase 2 Azure/Databricks)

**Tipo:** Epic  
**Status no Jira:** A fazer (snapshot 2026-11-09 14:21 America/Sao_Paulo)  
**Projeto:** AILAB  
**Épico Pai:** —  
**Fase:** 1+2  
**Papéis:** Executor: agente no VS Code + Luciano | Arquiteto / Revisor: **Luciano Teixeira**  
**Precedência:** bloqueada por — · bloqueia —  
**Governança:** Issue-as-a-Prompt — este arquivo espelha a issue [AILAB-1](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-1) (Jira exige login)

---

## 1. Conteúdo do Prompt Canônico

## 🏛️ [PROMPT DE ARQUITETURA] — AILAB-1: Lab ANP GLP: RAG docs oficiais + MCP API + FastAPI (fase 2 Azure/Databricks)

### 1.1 Contexto & Objetivo

Laboratório público fim a fim: RAG com citações sobre a documentação oficial da ANP, MCP read-only sobre a API real de Revendedores GLP (`https://revendedoresapi.anp.gov.br/v1/glp`), orquestração LangGraph e FastAPI, com evals/CI sobre snapshot mínimo e métricas calculadas em código. A fase 2 (Azure OpenAI + Databricks) só acontece com credenciais e custo autorizados. Este documento é o prompt de arquitetura do épico: orienta as tasks AILAB-2..10 e não é executável isoladamente.

- Repo público com documentação, mapa Jira e catálogo de prompts publicados; implementação de aplicação ainda não iniciada.
- Fonte de dados: API ANP Revendedores GLP (cadastro de revendas; não contém vendas nem preços). Paginação de até 5000 registros via `numeropagina`. Filtros comprovados: `uf`, `municipio` (+`uf`), `cnpj`.
- Corpus RAG: manual oficial da API Revendedores, Swagger e páginas de dados abertos da ANP (ver `docs/SOURCES.md`).
- ADRs 001–006 em status Proposto; todas as issues em A fazer.

### 1.2 Escopo técnico & arquivos

- `docs/00-PRD.md`
- `docs/01-ARCHITECTURE.md`
- `docs/adrs/`
- `docs/05-TEST-EVAL-STRATEGY.md`
- `docs/map/EPIC-TASK-MAP.md`
- `docs/prompts/README.md`

### 1.3 Fora de escopo

- Implementar código diretamente a partir do épico.
- Aceitar ADRs ou marcar Done em nome do Luciano.

### 1.4 Metas de entrega do épico

1. Fase 1 — AILAB-2 revisão documental → AILAB-3 bootstrap → (AILAB-4 RAG ∥ AILAB-5 MCP) → AILAB-6 FastAPI → AILAB-7 evals/guardrails → AILAB-8 CI/demo.
2. Fase 2 — AILAB-9 Azure OpenAI ∥ AILAB-10 Databricks Bronze/Silver/Gold + MLflow mínimo, somente com autorização.
3. Cada task tem prompt canônico em `docs/prompts/tasks/` e gera relatório de fechamento em `docs/relatorios/`.

### 1.5 Testes / verificação

- Mapa, manifesto e catálogo apontam para arquivos existentes.
- Cada task fechada tem relatório de fechamento com evidências reais.

### 1.6 Definition of Done (DoD)

- [ ] AILAB-2..8 aceitas pelo Luciano
- [ ] Zero segredos e nenhum dump nacional no Git
- [ ] Respostas com citações oficiais; métricas em código
- [ ] Demo de 5 min reproduzível a partir do README
- [ ] Fase 2 executada sob autorização ou bloqueio documentado

### 1.7 Ações proibidas

- Commitar segredos (API keys, tokens, `.env`) ou dados pessoais.
- Republicar o cadastro ANP completo: snapshot mínimo, datado e sanitizado.
- Calcular métricas/contagens com o LLM — sempre em código (Python/SQL).
- Usar FakeProvider fora de testes rotulados.
- Marcar a issue como Done, aceitar ADRs ou fazer merge sem revisão do Luciano.
- Provisionar cloud ou gerar custo sem autorização explícita.

### 1.8 Escalonamento

- Conflito de escopo ou de prioridade → Luciano decide.

### 1.9 Tasks filhas

| Chave | LAB | Fase | Resumo |
| --- | --- | --- | --- |
| [AILAB-2](../tasks/AILAB-2_revisar-pacote-documental-anp-glp.md) | LAB-01 | 1 | [LAB-01] Revisar e aceitar pacote documental ANP GLP |
| [AILAB-3](../tasks/AILAB-3_bootstrap-vscode-repo-existente.md) | LAB-02 | 1 | [LAB-02] Bootstrap VS Code no repo existente (docs ANP) |
| [AILAB-4](../tasks/AILAB-4_rag-corpus-oficial-anp-citacoes.md) | LAB-03 | 1 | [LAB-03] RAG: corpus oficial ANP (manual/metadata) + citações |
| [AILAB-5](../tasks/AILAB-5_langgraph-mcp-anp-glp-readonly.md) | LAB-04 | 1 | [LAB-04] LangGraph + MCP ANP GLP read-only (API/snapshot) |
| [AILAB-6](../tasks/AILAB-6_fastapi-e2e-snapshot-live-optin.md) | LAB-05 | 1 | [LAB-05] FastAPI E2E (snapshot default, live opt-in) |
| [AILAB-7](../tasks/AILAB-7_evals-tracing-guardrails-minimizacao.md) | LAB-06 | 1 | [LAB-06] Evals + tracing + guardrails + minimização de dados |
| [AILAB-8](../tasks/AILAB-8_ci-snapshot-demo-readme.md) | LAB-07 | 1 | [LAB-07] CI snapshot + demo 5 min + README ANP |
| [AILAB-9](../tasks/AILAB-9_fase2-azure-openai-pratico.md) | LAB-08 | 2 | [LAB-08][Fase 2] Azure OpenAI prático (credenciais/custo autorizados) |
| [AILAB-10](../tasks/AILAB-10_fase2-databricks-medallion-mlflow.md) | LAB-09 | 2 | [LAB-09][Fase 2] Databricks Bronze/Silver/Gold + MLflow mínimo |

---

## 2. Rastreabilidade

| Campo | Valor |
| --- | --- |
| Jira | [AILAB-1](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-1) (login) |
| Épico | — |
| Prompt canônico | `docs/prompts/epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md` |
| Versão do prompt | `2.0.0` |
| ID legado | `AILAB-PROMPT-000-EPIC` |
| Branch sugerida | — |
| Convenção de commit | Commits filhos usam a chave da task |
| Relatório de fechamento | `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-1.md` |
| Mapa / manifesto | [EPIC-TASK-MAP](../../map/EPIC-TASK-MAP.md) · [jira-manifest.json](../../map/jira-manifest.json) |

## 3. Histórico de Versões do Prompt

* **v1.0.0 (2026-11-08):** `prompts/vscode/AILAB-PROMPT-000-EPIC.v1.md` — formato frontmatter + seções curtas (removido; consultar histórico Git).
* **v2.0.0 (2026-11-09 — Atual):** reestruturado no padrão de catálogo canônico: arquivo nomeado pela chave Jira, prompt canônico espelhando a issue, rastreabilidade e relatório de fechamento.
