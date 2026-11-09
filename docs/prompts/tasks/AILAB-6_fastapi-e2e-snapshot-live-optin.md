---
jira_key: AILAB-6
tipo: Tarefa
lab: LAB-05
fase: "1"
epico_pai: AILAB-1
executor: vscode
risco: medium
status_jira_snapshot: A fazer
prompt_version: 2.0.0
legacy_prompt_id: AILAB-PROMPT-005-FASTAPI-E2E
supersedes: prompts/vscode/AILAB-PROMPT-005-FASTAPI-E2E.v1.md
atualizado: "2026-11-09 14:21 America/Sao_Paulo"
---

# AILAB-6 — [LAB-05] FastAPI E2E (snapshot default, live opt-in)

**Tipo:** Tarefa  
**Status no Jira:** A fazer (snapshot 2026-11-09 14:21 America/Sao_Paulo)  
**Projeto:** AILAB  
**Épico Pai:** AILAB-1  
**Fase:** 1 · **Risco:** medium  
**Papéis:** Executor: agente no VS Code | Arquiteto / Revisor: **Luciano Teixeira**  
**Precedência:** bloqueada por AILAB-4, AILAB-5 · bloqueia AILAB-7  
**Governança:** Issue-as-a-Prompt — este arquivo espelha a issue [AILAB-6](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-6) (Jira exige login)

---

## 1. Conteúdo do Prompt Canônico

## 📋 [ISSUE-AS-A-PROMPT] — AILAB-6: [LAB-05] FastAPI E2E (snapshot default, live opt-in)

### 1.1 Contexto & Objetivo

Expor `GET /health` e `POST /ask` integrando RAG (AILAB-4) e MCP/LangGraph (AILAB-5). `data_mode=snapshot` por padrão; `live` opt-in. FakeProvider fora do caminho padrão da demo.

- Contratos em `docs/01-ARCHITECTURE.md`.
- Resposta: answer, citations, tool_calls?, metrics?, data_mode, snapshot_id?, retrieved_at?, provider, trace_id.

### 1.2 Escopo técnico & arquivos

- `src/anp_lab/api/main.py`
- `src/anp_lab/api/schemas.py`
- `tests/e2e/`

### 1.3 Fora de escopo

- Azure/Databricks.
- Live no CI.
- UI rica (ADR-004: Swagger first).

### 1.4 Passos de execução do agente

1. Schemas Pydantic de request/response.
2. Ligar grafo LangGraph + MCP ao `/ask`.
3. Implementar `data_mode` snapshot|live (live só via variável de ambiente).
4. Swagger/OpenAPI honesto (sem filtros não comprovados).
5. Testes e2e com snapshot.

### 1.5 Testes / verificação

- `/health` 200 com `data_mode`.
- Pergunta documental → resposta com citação.
- Pergunta de contagem → métrica em código + escopo.

### 1.6 Definition of Done (DoD)

- [ ] E2E snapshot verde
- [ ] Swagger honesto
- [ ] Live opt-in documentado
- [ ] FakeProvider ausente do default

### 1.7 Ações proibidas

- Esconder o uso de FakeProvider.
- Commitar segredos (API keys, tokens, `.env`) ou dados pessoais.
- Republicar o cadastro ANP completo: snapshot mínimo, datado e sanitizado.
- Calcular métricas/contagens com o LLM — sempre em código (Python/SQL).
- Usar FakeProvider fora de testes rotulados.
- Marcar a issue como Done, aceitar ADRs ou fazer merge sem revisão do Luciano.
- Provisionar cloud ou gerar custo sem autorização explícita.

### 1.8 Escalonamento

- MCP instável → snapshot only + nota no README.

---

## 2. Prompt Executivo (colar no chat do agente no VS Code)

```markdown
Atue sob as regras de `AGENTS.md` e `docs/prompts/CORE-RULES.md`.
Tarefa: AILAB-6 — [LAB-05] FastAPI E2E (snapshot default, live opt-in)
Prompt canônico: `docs/prompts/tasks/AILAB-6_fastapi-e2e-snapshot-live-optin.md` (v2.0.0).

### 🛡️ RITUAL OBRIGATÓRIO DE INÍCIO DE TURNO
1. Idempotência: rode `git log --oneline --grep="AILAB-6"`. Se a entrega já estiver no histórico e os testes passarem, pare e responda: `[IDEMPOTÊNCIA] AILAB-6 já executada`.
2. Branch: `git branch --show-current` deve ser `feature/AILAB-6-fastapi-e2e`. Se não for, crie-a a partir de `main` atualizada.
3. Imersão: leia o prompt canônico, os docs/ADRs citados na seção 1.1 e o código existente antes de editar. Arquivos-alvo (criar ou alterar): `src/anp_lab/api/main.py`, `src/anp_lab/api/schemas.py`, `tests/e2e/`.
4. Runner: use somente o Python do `.venv` (`python -m pytest`, `python -m ruff check .`).
5. Pré-requisitos: confirme que AILAB-4, AILAB-5 estão concluídas. Caso contrário, pare e avise.

### 📋 ESCOPO (AILAB-6)
1. Schemas Pydantic de request/response.
2. Ligar grafo LangGraph + MCP ao `/ask`.
3. Implementar `data_mode` snapshot|live (live só via variável de ambiente).
4. Swagger/OpenAPI honesto (sem filtros não comprovados).
5. Testes e2e com snapshot.

### ✅ SAÍDA ESPERADA
- Testes da seção 1.5 do prompt canônico executados, com saída real colada no relatório.
- Relatório de fechamento em `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-6.md` (template `docs/prompts/templates/RELATORIO-FECHAMENTO.md`).
- Não invente resultados. Se algo falhar ou estiver bloqueado, registre e pare.

Commit ao concluir:
`AILAB-6 feat(api): endpoints /health e /ask ponta a ponta`
```

---

## 3. Rastreabilidade

| Campo | Valor |
| --- | --- |
| Jira | [AILAB-6](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-6) (login) |
| Épico | [AILAB-1](../epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md) |
| Prompt canônico | `docs/prompts/tasks/AILAB-6_fastapi-e2e-snapshot-live-optin.md` |
| Versão do prompt | `2.0.0` |
| ID legado | `AILAB-PROMPT-005-FASTAPI-E2E` |
| Branch sugerida | `feature/AILAB-6-fastapi-e2e` |
| Convenção de commit | `AILAB-6 feat(api): endpoints /health e /ask ponta a ponta` |
| Relatório de fechamento | `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-6.md` |
| Mapa / manifesto | [EPIC-TASK-MAP](../../map/EPIC-TASK-MAP.md) · [jira-manifest.json](../../map/jira-manifest.json) |

## 4. Histórico de Versões do Prompt

* **v1.0.0 (2026-11-08):** `prompts/vscode/AILAB-PROMPT-005-FASTAPI-E2E.v1.md` — formato frontmatter + seções curtas (removido; consultar histórico Git).
* **v2.0.0 (2026-11-09 — Atual):** reestruturado no padrão de catálogo canônico: arquivo nomeado pela chave Jira, prompt canônico espelhando a issue, prompt executivo com ritual de início de turno, rastreabilidade e relatório de fechamento.
