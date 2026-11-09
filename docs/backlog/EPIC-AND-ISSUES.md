**Mapa:** [`../map/EPIC-TASK-MAP.md`](../map/EPIC-TASK-MAP.md) · **Manifesto:** [`../map/jira-manifest.json`](../map/jira-manifest.json) · **Catálogo:** [`../prompts/README.md`](../prompts/README.md)

# Backlog — Epic + Issues-as-a-Prompt (ANP GLP)

**Repo:** https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab (docs; app não iniciada) · **Jira:** AILAB · **Issues:** AILAB-1..10 (reutilizar; não duplicar)

## Resumo

| Temp | Jira | Título | Fase | Risk |
| --- | --- | --- | --- | --- |
| EPIC-1 | AILAB-1 | Lab ANP GLP: RAG docs + MCP API + FastAPI | 1+2 | — |
| LAB-01 | AILAB-2 | Revisar/aceitar pacote documental ANP | 1 | low |
| LAB-02 | AILAB-3 | Bootstrap VS Code no repo existente | 1 | low |
| LAB-03 | AILAB-4 | RAG corpus oficial ANP (manual/metadata) | 1 | medium |
| LAB-04 | AILAB-5 | LangGraph + MCP ANP GLP read-only | 1 | medium |
| LAB-05 | AILAB-6 | FastAPI E2E snapshot + live opt-in | 1 | medium |
| LAB-06 | AILAB-7 | Evals + tracing + guardrails + minimização | 1 | medium |
| LAB-07 | AILAB-8 | CI snapshot + demo 5 min + README | 1 | low |
| LAB-08 | AILAB-9 | [Fase 2] Azure OpenAI prático (autorizado) | 2 | high |
| LAB-09 | AILAB-10 | [Fase 2] Databricks medallion + MLflow mín. | 2 | high |

**Deps Blocks (já existentes):** 2→3; 3→4; 3→5; 4→6; 5→6; 6→7; 7→8; 8→9; 8→10.

---

## EPIC AILAB-1

Objetivo: lab público com **API ANP Revendedores GLP**, RAG sobre **manual/metadata oficiais**, MCP read-only, FastAPI, evals/CI com snapshot mínimo; fase 2 Azure+Databricks prática sob autorização — **sem provisionar agora**.

DoD fase 1: AILAB-2..8 aceitas; zero secrets; sem dump nacional; FakeProvider só testes; docs commitados no repo existente.

---

## 📋 [ISSUE-AS-A-PROMPT] AILAB-2 / LAB-01 — Revisar pacote documental ANP

**Papéis:** Arquiteto=Grok Bot · Executor=Luciano · Review=Luciano

### Objetivo
Revisar PRD/ADRs/DS/threat/evals/runbook/backlog alinhados à API ANP; aceitar ou listar diffs. **Não** marcar ADRs Aceito automaticamente.

### Fora de escopo
Código; provisionar cloud; criar issues novas.

### Contexto
Pacote local `docs-pack/`; repo com docs (app não iniciada) https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab; Jira AILAB.

### Passo a passo
1. Ler README + PRD 0.2 
2. Validar ADRs 001–006 (**Proposto**) 
3. Confirmar fase 1 vs fase 2 
4. Registrar aceite/diffs

### DoD
- [ ] Aceite humano ou lista de ajustes

### Ações proibidas
Aceitar ADRs em nome do Luciano; Done sem revisão.

### Escalonamento / PR
N/A docs.

**Labels:** spec review:luciano qa:risk-low 
**Bloqueia:** AILAB-3

---

## 📋 [ISSUE-AS-A-PROMPT] AILAB-3 / LAB-02 — Bootstrap repo existente

**Papéis:** Arquiteto=Grok Bot · Executor=VS Code · Review=Luciano

### Objetivo
Estrutura mínima no repo **já existente** https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab: venv, README ANP, gitignore, copiar `docs/` do pacote local, **sem criar outro repo**.

### Fora de escopo
Implementar RAG/MCP além de stub; Azure; novo GitHub.

### Passo a passo
1. Clone repo com docs (app não iniciada); `code .`; Create Environment 
2. Copiar docs-pack → `docs/` 
3. README: fonte ANP, snapshot, fase 2 planejada 
4. Scan secrets; push

### DoD
- [ ] Docs no GitHub · zero secrets · Luciano aceita README

### Ações proibidas
Novo repo; dump ANP completo; alegar features feitas.

**Labels:** spec exec:vscode review:luciano qa:risk-low 
**Depende:** AILAB-2 · **Bloqueia:** AILAB-4, AILAB-5

---

## 📋 [ISSUE-AS-A-PROMPT] AILAB-4 / LAB-03 — RAG corpus oficial ANP

**Papéis:** Executor=VS Code · Review=Luciano

### Objetivo
Ingerir **manual PDF + metadata/páginas oficiais** (texto extraído versionado); índice lexical; citations; abstém fora do corpus.

### Fora de escopo
Usar pedidos fictícios; embeddings pagos; inventar campos.

### Arquivos
`data/corpus/anp/` (texto derivado do manual/portal); `rag.py`

### Passo a passo
1. Extrair/guardar trechos oficiais com atribuição ANP 
2. Chunk + ids estáveis 
3. Retrieve top-k + citations 
4. Testes G01–G03

### DoD
- [ ] Citations do corpus oficial · abstém ok · testes verdes

### Ações proibidas
Corpus inventado; alegar licença não confirmada.

**Labels:** spec exec:vscode review:luciano qa:risk-medium 
**Depende:** AILAB-3 · **Bloqueia:** AILAB-6

---

## 📋 [ISSUE-AS-A-PROMPT] AILAB-5 / LAB-04 — LangGraph + MCP ANP GLP

**Papéis:** Executor=VS Code · Review=Luciano

### Objetivo
Grafo + MCP real allowlist: get_by_cnpj, list(uf, municipio?), count(**código**). Cliente HTTP com timeout/retry/backoff/cache; default **snapshot**; live opt-in.

### Fora de escopo
Write tools; filtros não comprovados; métricas via LLM.

### Passo a passo
1. Cliente ANP paginado + cache `retrieved_at`/`source` 
2. Snapshot mínimo sanitizado 
3. MCP stdio allowlist 
4. LangGraph classify→docs|query→compose 
5. Testes snapshot

### DoD
- [ ] MCP real · count em código · escopo explícito · pin SDK

### Ações proibidas
Dump nacional no repo; HTTP fora do host ANP.

**Labels:** spec exec:vscode review:luciano qa:risk-medium 
**Depende:** AILAB-3 · **Bloqueia:** AILAB-6

---

## 📋 [ISSUE-AS-A-PROMPT] AILAB-6 / LAB-05 — FastAPI E2E

### Objetivo
`/health` + `/ask` com `data_mode` snapshot|live; citations/tool_calls/metrics; FakeProvider **não** no caminho demo default.

### DoD
- [ ] E2E snapshot verde · Swagger honesto · live opt-in documentado

**Labels:** spec exec:vscode review:luciano qa:risk-medium 
**Depende:** AILAB-4, AILAB-5 · **Bloqueia:** AILAB-7

---

## 📋 [ISSUE-AS-A-PROMPT] AILAB-7 / LAB-06 — Evals, tracing, guardrails, minimização

### Objetivo
Goldens; trace_id; redaction; guardrails; política de campos do snapshot.

### DoD
- [ ] Eval smoke · metas propostas rotuladas · sem live no CI

**Labels:** spec exec:vscode review:luciano qa:risk-medium 
**Depende:** AILAB-6 · **Bloqueia:** AILAB-8

---

## 📋 [ISSUE-AS-A-PROMPT] AILAB-8 / LAB-07 — CI + demo + README

### Objetivo
CI sem live ANP; demo 5 min; README com atribuição ANP e limites.

### DoD
- [ ] CI verde · demo uma vez · gaps honestos

**Labels:** spec exec:vscode review:luciano qa:risk-low 
**Depende:** AILAB-7 · **Bloqueia:** AILAB-9, AILAB-10

---

## 📋 [ISSUE-AS-A-PROMPT] AILAB-9 / LAB-08 — [Fase 2] Azure OpenAI prático

### Objetivo
Integrar Azure OpenAI **de fato** quando Luciano autorizar credenciais/custo. Não é stub cosmétique. Default fase 1 permanece sem cobrança.

### Fora de escopo
Provisionar recurso sem aprovação; keys no git; CI pago.

### DoD
- [ ] Adapter real testado com autorização · rollback para fase 1 · zero secrets

### Limitações
Bloqueado sem subscription/budget. Não alegar produção.

**Labels:** spec exec:vscode review:luciano qa:risk-high phase:2 
**Depende:** AILAB-8

---

## 📋 [ISSUE-AS-A-PROMPT] AILAB-10 / LAB-09 — [Fase 2] Databricks medallion + MLflow mín.

### Objetivo
Prática autorizada: Bronze (JSON/páginas ANP) → Silver → Gold; MLflow mínimo para eval/tracing se viável. Vector Search **somente** se útil/disponível para docs — não requisito artificial.

### Fora de escopo
Gastar DBUs sem aprovação; afirmar UC/VS em produção sem evidência.

### DoD
- [ ] Pipeline mínimo documentado+executado sob autorização **ou** bloqueio explícito por falta de acesso 
- [ ] Coluna real vs planejado honesta

**Labels:** spec exec:vscode review:luciano qa:risk-high phase:2 
**Depende:** AILAB-8
