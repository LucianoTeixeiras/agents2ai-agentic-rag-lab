---
jira_key: AILAB-5
tipo: Tarefa
lab: LAB-04
fase: "1"
epico_pai: AILAB-1
executor: vscode
risco: medium
status_jira_snapshot: A fazer
prompt_version: 2.0.0
legacy_prompt_id: AILAB-PROMPT-004-MCP-ANP
supersedes: prompts/vscode/AILAB-PROMPT-004-MCP-ANP.v1.md
atualizado: "2026-11-09 14:21 America/Sao_Paulo"
---

# AILAB-5 — [LAB-04] LangGraph + MCP ANP GLP read-only (API/snapshot)

**Tipo:** Tarefa  
**Status no Jira:** A fazer (snapshot 2026-11-09 14:21 America/Sao_Paulo)  
**Projeto:** AILAB  
**Épico Pai:** AILAB-1  
**Fase:** 1 · **Risco:** medium  
**Papéis:** Executor: agente no VS Code | Arquiteto / Revisor: **Luciano Teixeira**  
**Precedência:** bloqueada por AILAB-3 · bloqueia AILAB-6  
**Governança:** Issue-as-a-Prompt — este arquivo espelha a issue [AILAB-5](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-5) (Jira exige login)

---

## 1. Conteúdo do Prompt Canônico

## 📋 [ISSUE-AS-A-PROMPT] — AILAB-5: [LAB-04] LangGraph + MCP ANP GLP read-only (API/snapshot)

### 1.1 Contexto & Objetivo

Servidor MCP real (SDK oficial, versão pinada) com allowlist read-only sobre a API ANP GLP, cliente HTTP com paginação, timeout, retry/backoff e cache (`source`, `retrieved_at`), e grafo LangGraph classify → docs | query → compose. Default snapshot; live opt-in. Contagens em código sobre o escopo recuperado.

- Endpoint: `https://revendedoresapi.anp.gov.br/v1/glp` (Swagger oficial).
- Filtros comprovados apenas: `uf`, `municipio` (+`uf`), `cnpj`; página até 5000 registros via `numeropagina`.
- ADR-002 (MCP read-only) e ADR-006 (minimização).

### 1.2 Escopo técnico & arquivos

- `src/anp_lab/anp_client.py`
- `src/anp_lab/mcp_server.py`
- `src/anp_lab/graph.py`
- `data/snapshots/anp_glp_<data>.json` (mínimo, sanitizado)
- `tests/mcp/`

### 1.3 Fora de escopo

- Tools de escrita.
- Scrapers.
- Métricas via LLM.
- Dump nacional no Git.

### 1.4 Passos de execução do agente

1. Cliente HTTP com paginação, timeout, retry/backoff e cache.
2. Snapshot mínimo sanitizado (sem endereço/contato/CNPJ desnecessários).
3. Servidor MCP stdio com tools: `get_revenda_glp_by_cnpj`, `list_revendas_glp(uf, municipio=None, page=1)`, `count_revendas_glp(...)` (contagem em código).
4. Grafo LangGraph classify → docs | query → compose.
5. Testes contra o snapshot.

### 1.5 Testes / verificação

- G04 count UF no snapshot = N calculado em código.
- G05 CNPJ do snapshot → tool get.
- Host permitido somente ANP/snapshot; nenhuma chamada live no CI.

### 1.6 Definition of Done (DoD)

- [ ] MCP real com SDK pinado
- [ ] Contagem em código com escopo explícito
- [ ] Testes snapshot verdes
- [ ] Snapshot mínimo documentado

### 1.7 Ações proibidas

- Chamar hosts que não sejam da ANP.
- Commitar segredos (API keys, tokens, `.env`) ou dados pessoais.
- Republicar o cadastro ANP completo: snapshot mínimo, datado e sanitizado.
- Calcular métricas/contagens com o LLM — sempre em código (Python/SQL).
- Usar FakeProvider fora de testes rotulados.
- Marcar a issue como Done, aceitar ADRs ou fazer merge sem revisão do Luciano.
- Provisionar cloud ou gerar custo sem autorização explícita.

### 1.8 Escalonamento

- API ANP indisponível → operar só com snapshot e registrar.

---

## 2. Prompt Executivo (colar no chat do agente no VS Code)

```markdown
Atue sob as regras de `AGENTS.md` e `docs/prompts/CORE-RULES.md`.
Tarefa: AILAB-5 — [LAB-04] LangGraph + MCP ANP GLP read-only (API/snapshot)
Prompt canônico: `docs/prompts/tasks/AILAB-5_langgraph-mcp-anp-glp-readonly.md` (v2.0.0).

### 🛡️ RITUAL OBRIGATÓRIO DE INÍCIO DE TURNO
1. Idempotência: rode `git log --oneline --grep="AILAB-5"`. Se a entrega já estiver no histórico e os testes passarem, pare e responda: `[IDEMPOTÊNCIA] AILAB-5 já executada`.
2. Branch: `git branch --show-current` deve ser `feature/AILAB-5-mcp-anp`. Se não for, crie-a a partir de `main` atualizada.
3. Imersão: leia o prompt canônico, os docs/ADRs citados na seção 1.1 e o código existente antes de editar. Arquivos-alvo (criar ou alterar): `src/anp_lab/anp_client.py`, `src/anp_lab/mcp_server.py`, `src/anp_lab/graph.py`, `data/snapshots/anp_glp_<data>.json`, `tests/mcp/`.
4. Runner: use somente o Python do `.venv` (`python -m pytest`, `python -m ruff check .`).
5. Pré-requisitos: confirme que AILAB-3 está concluída. Caso contrário, pare e avise.

### 📋 ESCOPO (AILAB-5)
1. Cliente HTTP com paginação, timeout, retry/backoff e cache.
2. Snapshot mínimo sanitizado (sem endereço/contato/CNPJ desnecessários).
3. Servidor MCP stdio com tools: `get_revenda_glp_by_cnpj`, `list_revendas_glp(uf, municipio=None, page=1)`, `count_revendas_glp(...)` (contagem em código).
4. Grafo LangGraph classify → docs | query → compose.
5. Testes contra o snapshot.

### ✅ SAÍDA ESPERADA
- Testes da seção 1.5 do prompt canônico executados, com saída real colada no relatório.
- Relatório de fechamento em `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-5.md` (template `docs/prompts/templates/RELATORIO-FECHAMENTO.md`).
- Não invente resultados. Se algo falhar ou estiver bloqueado, registre e pare.

Commit ao concluir:
`AILAB-5 feat(mcp): servidor MCP read-only ANP GLP e grafo LangGraph`
```

---

## 3. Rastreabilidade

| Campo | Valor |
| --- | --- |
| Jira | [AILAB-5](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-5) (login) |
| Épico | [AILAB-1](../epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md) |
| Prompt canônico | `docs/prompts/tasks/AILAB-5_langgraph-mcp-anp-glp-readonly.md` |
| Versão do prompt | `2.0.0` |
| ID legado | `AILAB-PROMPT-004-MCP-ANP` |
| Branch sugerida | `feature/AILAB-5-mcp-anp` |
| Convenção de commit | `AILAB-5 feat(mcp): servidor MCP read-only ANP GLP e grafo LangGraph` |
| Relatório de fechamento | `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-5.md` |
| Mapa / manifesto | [EPIC-TASK-MAP](../../map/EPIC-TASK-MAP.md) · [jira-manifest.json](../../map/jira-manifest.json) |

## 4. Histórico de Versões do Prompt

* **v1.0.0 (2026-11-08):** `prompts/vscode/AILAB-PROMPT-004-MCP-ANP.v1.md` — formato frontmatter + seções curtas (removido; consultar histórico Git).
* **v2.0.0 (2026-11-09 — Atual):** reestruturado no padrão de catálogo canônico: arquivo nomeado pela chave Jira, prompt canônico espelhando a issue, prompt executivo com ritual de início de turno, rastreabilidade e relatório de fechamento.
