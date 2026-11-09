# Catálogo de Prompts Canônicos — agents2ai-agentic-rag-lab

Este catálogo versiona os **Prompts de Arquitetura (Épicos)** e as **Ordens de Serviço (Issues-as-a-Prompt)** do laboratório ANP GLP (RAG + MCP read-only + FastAPI; fase 2 Azure OpenAI/Databricks).

Cada arquivo espelha a issue correspondente do projeto Jira **AILAB**. A chave Jira é o identificador do prompt e prefixa o nome do arquivo, a branch, o commit e o relatório de fechamento.

**Snapshot:** 2026-11-09 14:21 America/Sao_Paulo · **Versão do catálogo:** 2.0.0 · **Status:** fonte operacional = Jira; versão do prompt = Git · **Sync:** manual (sem integração automática alegada)

---

## 🏛️ Épicos (Prompts de Arquitetura)

| Chave | Fase | Status | Arquivo Canônico | Resumo |
| --- | --- | --- | --- | --- |
| **AILAB-1** | 1+2 | A fazer | [`epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md`](epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md) | Lab ANP GLP: RAG docs oficiais + MCP API + FastAPI (fase 2 Azure/Databricks) |

---

## 📋 Tasks (Issues-as-a-Prompt)

| Chave | LAB | Fase | Status | Precedência / Vínculo | Arquivo Canônico | Resumo |
| --- | --- | --- | --- | --- | --- | --- |
| **AILAB-2** | LAB-01 | 1 | A fazer | bloqueia AILAB-3 | [`tasks/AILAB-2_revisar-pacote-documental-anp-glp.md`](tasks/AILAB-2_revisar-pacote-documental-anp-glp.md) | Revisar e aceitar pacote documental ANP GLP |
| **AILAB-3** | LAB-02 | 1 | A fazer | bloqueada por AILAB-2; bloqueia AILAB-4, AILAB-5 | [`tasks/AILAB-3_bootstrap-vscode-repo-existente.md`](tasks/AILAB-3_bootstrap-vscode-repo-existente.md) | Bootstrap VS Code no repo existente (docs ANP) |
| **AILAB-4** | LAB-03 | 1 | A fazer | bloqueada por AILAB-3; bloqueia AILAB-6 | [`tasks/AILAB-4_rag-corpus-oficial-anp-citacoes.md`](tasks/AILAB-4_rag-corpus-oficial-anp-citacoes.md) | RAG: corpus oficial ANP (manual/metadata) + citações |
| **AILAB-5** | LAB-04 | 1 | A fazer | bloqueada por AILAB-3; bloqueia AILAB-6 | [`tasks/AILAB-5_langgraph-mcp-anp-glp-readonly.md`](tasks/AILAB-5_langgraph-mcp-anp-glp-readonly.md) | LangGraph + MCP ANP GLP read-only (API/snapshot) |
| **AILAB-6** | LAB-05 | 1 | A fazer | bloqueada por AILAB-4, AILAB-5; bloqueia AILAB-7 | [`tasks/AILAB-6_fastapi-e2e-snapshot-live-optin.md`](tasks/AILAB-6_fastapi-e2e-snapshot-live-optin.md) | FastAPI E2E (snapshot default, live opt-in) |
| **AILAB-7** | LAB-06 | 1 | A fazer | bloqueada por AILAB-6; bloqueia AILAB-8 | [`tasks/AILAB-7_evals-tracing-guardrails-minimizacao.md`](tasks/AILAB-7_evals-tracing-guardrails-minimizacao.md) | Evals + tracing + guardrails + minimização de dados |
| **AILAB-8** | LAB-07 | 1 | A fazer | bloqueada por AILAB-7; bloqueia AILAB-9, AILAB-10 | [`tasks/AILAB-8_ci-snapshot-demo-readme.md`](tasks/AILAB-8_ci-snapshot-demo-readme.md) | CI snapshot + demo 5 min + README ANP |
| **AILAB-9** | LAB-08 | 2 | A fazer | bloqueada por AILAB-8 | [`tasks/AILAB-9_fase2-azure-openai-pratico.md`](tasks/AILAB-9_fase2-azure-openai-pratico.md) | Azure OpenAI prático (credenciais/custo autorizados) |
| **AILAB-10** | LAB-09 | 2 | A fazer | bloqueada por AILAB-8 | [`tasks/AILAB-10_fase2-databricks-medallion-mlflow.md`](tasks/AILAB-10_fase2-databricks-medallion-mlflow.md) | Databricks Bronze/Silver/Gold + MLflow mínimo |

Status = snapshot; o valor operacional vive no Jira (links exigem login).

---

## 🗂️ Estrutura

| Caminho | Uso |
| --- | --- |
| [`CORE-RULES.md`](CORE-RULES.md) | Regras embarcadas em todo prompt executivo |
| [`epicos/`](epicos/) | Prompts de arquitetura (um por épico) |
| [`tasks/`](tasks/) | Issues-as-a-Prompt (um por task, `<CHAVE>_<slug>.md`) |
| [`templates/`](templates/) | Relatório de fechamento, revisão/reconciliação, rollback |
| [`runtime/`](runtime/) | Reservado para prompts de runtime (system/tools/evals) — vazio nesta versão |
| [`../relatorios/`](../relatorios/) | Relatórios de fechamento por task (`AAAA/AAAA-MM-DD-fechamento-<CHAVE>.md`) |

## 🧩 Anatomia de um prompt de task

1. **Cabeçalho** — tipo, status no Jira (snapshot), épico pai, fase, papéis, precedência.
2. **Conteúdo do Prompt Canônico** — contexto & objetivo, escopo técnico & arquivos, fora de escopo, passos, testes, DoD, ações proibidas, escalonamento. Espelha a descrição da issue.
3. **Prompt Executivo** — bloco pronto para colar no agente do VS Code, com o ritual de início de turno e a mensagem de commit.
4. **Rastreabilidade** — Jira, prompt, versão, branch, commit, relatório, mapa.
5. **Histórico de Versões do Prompt** — v1, v2… dentro do próprio arquivo.

## 🔁 Versionamento

- O nome do arquivo é estável (`<CHAVE>_<slug>.md`); a versão vive no frontmatter (`prompt_version`) e no histórico ao final do arquivo.
- Mudança de conteúdo → incrementar `prompt_version`, adicionar entrada no histórico, atualizar o manifesto (`docs/map/jira-manifest.json`) e a descrição da issue.
- IDs legados `AILAB-PROMPT-00N-*` (v1) ficam registrados em `legacy_prompt_id` para rastreabilidade.

## 🛡️ Padrão de Engenharia Agêntica (Core Rules Embarcadas)

Todas as tasks seguem [`CORE-RULES.md`](CORE-RULES.md):
1. **Ritual de início de turno:** idempotência via `git log --grep=<CHAVE>`, branch ativa conferida, imersão no código antes de editar, runner do `.venv`.
2. **Dados:** API ANP real com snapshot mínimo sanitizado; live só opt-in; métricas sempre em código.
3. **Fechamento:** relatório com evidências reais; Done e aceite de ADR só pelo Luciano.

## ⚠️ Aviso de não determinismo

Reprodutibilidade aqui é de **processo** (mesmo prompt, dependências, corpus e snapshot), não de texto idêntico gerado por LLM. Registre modelo, configuração e evidências no relatório.
