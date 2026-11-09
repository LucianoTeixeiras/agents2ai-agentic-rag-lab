---
jira_key: AILAB-10
tipo: Tarefa
lab: LAB-09
fase: "2"
epico_pai: AILAB-1
executor: vscode
risco: high
status_jira_snapshot: A fazer
prompt_version: 2.0.0
legacy_prompt_id: AILAB-PROMPT-009-DATABRICKS
supersedes: prompts/vscode/AILAB-PROMPT-009-DATABRICKS.v1.md
atualizado: "2026-11-09 14:21 America/Sao_Paulo"
---

# AILAB-10 — [LAB-09][Fase 2] Databricks Bronze/Silver/Gold + MLflow mínimo

**Tipo:** Tarefa  
**Status no Jira:** A fazer (snapshot 2026-11-09 14:21 America/Sao_Paulo)  
**Projeto:** AILAB  
**Épico Pai:** AILAB-1  
**Fase:** 2 · **Risco:** high  
**Papéis:** Executor: agente no VS Code | Arquiteto / Revisor: **Luciano Teixeira**  
**Precedência:** bloqueada por AILAB-8 · bloqueia —  
**Governança:** Issue-as-a-Prompt — este arquivo espelha a issue [AILAB-10](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-10) (Jira exige login)

---

## 1. Conteúdo do Prompt Canônico

## 📋 [ISSUE-AS-A-PROMPT] — AILAB-10: [LAB-09][Fase 2] Databricks Bronze/Silver/Gold + MLflow mínimo

### 1.1 Contexto & Objetivo

Prática autorizada no Databricks: ingestão das páginas JSON da ANP em Bronze → normalização Silver → agregados Gold, com MLflow mínimo para evals/tracing se viável. Vector Search só se útil e disponível — não é requisito.

- ADR-005.
- Dados: páginas JSON da API ANP GLP (cadastro, sem PII desnecessária).

### 1.2 Escopo técnico & arquivos

- `databricks/notebooks/` (bronze, silver, gold)
- `databricks/README.md`
- `docs/relatorios/`

### 1.3 Fora de escopo

- Gastar DBUs sem aprovação.
- Afirmar Unity Catalog/Vector Search em produção sem evidência.

### 1.4 Passos de execução do agente

1. Confirmar acesso e orçamento.
2. Bronze: ingestão bruta paginada com `retrieved_at`.
3. Silver: normalização e minimização de campos.
4. Gold: agregados por UF/município calculados em código.
5. MLflow mínimo se viável.
6. Tabela real vs planejado no relatório.

### 1.5 Testes / verificação

- Contagens Gold batem com contagem em código sobre a Silver.
- Sem alegação falsa de Vector Search.

### 1.6 Definition of Done (DoD)

- [ ] Pipeline mínimo executado sob autorização ou bloqueio documentado
- [ ] Sem alegações falsas de Vector Search

### 1.7 Ações proibidas

- Commitar segredos (API keys, tokens, `.env`) ou dados pessoais.
- Republicar o cadastro ANP completo: snapshot mínimo, datado e sanitizado.
- Calcular métricas/contagens com o LLM — sempre em código (Python/SQL).
- Usar FakeProvider fora de testes rotulados.
- Marcar a issue como Done, aceitar ADRs ou fazer merge sem revisão do Luciano.
- Provisionar cloud ou gerar custo sem autorização explícita.

### 1.8 Escalonamento

- Sem workspace → bloquear e documentar.

---

## 2. Prompt Executivo (colar no chat do agente no VS Code)

```markdown
Atue sob as regras de `AGENTS.md` e `docs/prompts/CORE-RULES.md`.
Tarefa: AILAB-10 — [LAB-09][Fase 2] Databricks Bronze/Silver/Gold + MLflow mínimo
Prompt canônico: `docs/prompts/tasks/AILAB-10_fase2-databricks-medallion-mlflow.md` (v2.0.0).

### 🛡️ RITUAL OBRIGATÓRIO DE INÍCIO DE TURNO
1. Idempotência: rode `git log --oneline --grep="AILAB-10"`. Se a entrega já estiver no histórico e os testes passarem, pare e responda: `[IDEMPOTÊNCIA] AILAB-10 já executada`.
2. Branch: `git branch --show-current` deve ser `feature/AILAB-10-databricks`. Se não for, crie-a a partir de `main` atualizada.
3. Imersão: leia o prompt canônico, os docs/ADRs citados na seção 1.1 e o código existente antes de editar. Arquivos-alvo (criar ou alterar): `databricks/notebooks/`, `databricks/README.md`, `docs/relatorios/`.
4. Runner: use somente o Python do `.venv` (`python -m pytest`, `python -m ruff check .`).
5. Pré-requisitos: confirme que AILAB-8 está concluída. Caso contrário, pare e avise.

### 📋 ESCOPO (AILAB-10)
1. Confirmar acesso e orçamento.
2. Bronze: ingestão bruta paginada com `retrieved_at`.
3. Silver: normalização e minimização de campos.
4. Gold: agregados por UF/município calculados em código.
5. MLflow mínimo se viável.
6. Tabela real vs planejado no relatório.

### ✅ SAÍDA ESPERADA
- Testes da seção 1.5 do prompt canônico executados, com saída real colada no relatório.
- Relatório de fechamento em `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-10.md` (template `docs/prompts/templates/RELATORIO-FECHAMENTO.md`).
- Não invente resultados. Se algo falhar ou estiver bloqueado, registre e pare.

Commit ao concluir:
`AILAB-10 feat(data): pipeline medallion ANP no Databricks`
```

---

## 3. Rastreabilidade

| Campo | Valor |
| --- | --- |
| Jira | [AILAB-10](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-10) (login) |
| Épico | [AILAB-1](../epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md) |
| Prompt canônico | `docs/prompts/tasks/AILAB-10_fase2-databricks-medallion-mlflow.md` |
| Versão do prompt | `2.0.0` |
| ID legado | `AILAB-PROMPT-009-DATABRICKS` |
| Branch sugerida | `feature/AILAB-10-databricks` |
| Convenção de commit | `AILAB-10 feat(data): pipeline medallion ANP no Databricks` |
| Relatório de fechamento | `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-10.md` |
| Mapa / manifesto | [EPIC-TASK-MAP](../../map/EPIC-TASK-MAP.md) · [jira-manifest.json](../../map/jira-manifest.json) |

## 4. Histórico de Versões do Prompt

* **v1.0.0 (2026-11-08):** `prompts/vscode/AILAB-PROMPT-009-DATABRICKS.v1.md` — formato frontmatter + seções curtas (removido; consultar histórico Git).
* **v2.0.0 (2026-11-09 — Atual):** reestruturado no padrão de catálogo canônico: arquivo nomeado pela chave Jira, prompt canônico espelhando a issue, prompt executivo com ritual de início de turno, rastreabilidade e relatório de fechamento.
