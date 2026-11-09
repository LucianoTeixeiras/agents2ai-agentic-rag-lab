---
jira_key: AILAB-7
tipo: Tarefa
lab: LAB-06
fase: "1"
epico_pai: AILAB-1
executor: vscode
risco: medium
status_jira_snapshot: A fazer
prompt_version: 2.0.0
legacy_prompt_id: AILAB-PROMPT-006-EVALS-GUARDRAILS
supersedes: prompts/vscode/AILAB-PROMPT-006-EVALS-GUARDRAILS.v1.md
atualizado: "2026-11-09 14:21 America/Sao_Paulo"
---

# AILAB-7 — [LAB-06] Evals + tracing + guardrails + minimização de dados

**Tipo:** Tarefa  
**Status no Jira:** A fazer (snapshot 2026-11-09 14:21 America/Sao_Paulo)  
**Projeto:** AILAB  
**Épico Pai:** AILAB-1  
**Fase:** 1 · **Risco:** medium  
**Papéis:** Executor: agente no VS Code | Arquiteto / Revisor: **Luciano Teixeira**  
**Precedência:** bloqueada por AILAB-6 · bloqueia AILAB-8  
**Governança:** Issue-as-a-Prompt — este arquivo espelha a issue [AILAB-7](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-7) (Jira exige login)

---

## 1. Conteúdo do Prompt Canônico

## 📋 [ISSUE-AS-A-PROMPT] — AILAB-7: [LAB-06] Evals + tracing + guardrails + minimização de dados

### 1.1 Contexto & Objetivo

Suite de evals (goldens RAG + caminho de tools), `trace_id` ponta a ponta, redaction de logs, guardrails contra prompt injection e política de minimização do snapshot. Metas de qualidade propostas, não garantidas.

- Estratégia em `docs/05-TEST-EVAL-STRATEGY.md` (G01–G07).
- Política de campos: ADR-006; ameaças: `docs/04-THREAT-MODEL.md`.

### 1.2 Escopo técnico & arquivos

- `evals/goldens.yaml`
- `evals/run_evals.py`
- `src/anp_lab/guardrails.py`
- `src/anp_lab/tracing.py`
- `tests/evals/`

### 1.3 Fora de escopo

- Live ANP no CI.
- MLflow completo (fase 2, AILAB-10).

### 1.4 Passos de execução do agente

1. Goldens G01–G07 + negativos sintéticos.
2. Runner de evals com relatório.
3. `trace_id` em logs e resposta.
4. Redaction e política de campos.
5. Documentar metas propostas.

### 1.5 Testes / verificação

- G06 injection bloqueada.
- G07 nenhuma chamada HTTP ANP com live desligado.
- Smoke de evals verde.

### 1.6 Definition of Done (DoD)

- [ ] Eval smoke verde sem live
- [ ] Snapshot mínimo documentado
- [ ] Guardrails básicos cobertos por teste

### 1.7 Ações proibidas

- Afirmar licença ANP não confirmada.
- Commitar segredos (API keys, tokens, `.env`) ou dados pessoais.
- Republicar o cadastro ANP completo: snapshot mínimo, datado e sanitizado.
- Calcular métricas/contagens com o LLM — sempre em código (Python/SQL).
- Usar FakeProvider fora de testes rotulados.
- Marcar a issue como Done, aceitar ADRs ou fazer merge sem revisão do Luciano.
- Provisionar cloud ou gerar custo sem autorização explícita.

### 1.8 Escalonamento

- Necessidade de MLflow → mover para AILAB-10.

---

## 2. Prompt Executivo (colar no chat do agente no VS Code)

```markdown
Atue sob as regras de `AGENTS.md` e `docs/prompts/CORE-RULES.md`.
Tarefa: AILAB-7 — [LAB-06] Evals + tracing + guardrails + minimização de dados
Prompt canônico: `docs/prompts/tasks/AILAB-7_evals-tracing-guardrails-minimizacao.md` (v2.0.0).

### 🛡️ RITUAL OBRIGATÓRIO DE INÍCIO DE TURNO
1. Idempotência: rode `git log --oneline --grep="AILAB-7"`. Se a entrega já estiver no histórico e os testes passarem, pare e responda: `[IDEMPOTÊNCIA] AILAB-7 já executada`.
2. Branch: `git branch --show-current` deve ser `feature/AILAB-7-evals-guardrails`. Se não for, crie-a a partir de `main` atualizada.
3. Imersão: leia o prompt canônico, os docs/ADRs citados na seção 1.1 e o código existente antes de editar. Arquivos-alvo (criar ou alterar): `evals/goldens.yaml`, `evals/run_evals.py`, `src/anp_lab/guardrails.py`, `src/anp_lab/tracing.py`, `tests/evals/`.
4. Runner: use somente o Python do `.venv` (`python -m pytest`, `python -m ruff check .`).
5. Pré-requisitos: confirme que AILAB-6 está concluída. Caso contrário, pare e avise.

### 📋 ESCOPO (AILAB-7)
1. Goldens G01–G07 + negativos sintéticos.
2. Runner de evals com relatório.
3. `trace_id` em logs e resposta.
4. Redaction e política de campos.
5. Documentar metas propostas.

### ✅ SAÍDA ESPERADA
- Testes da seção 1.5 do prompt canônico executados, com saída real colada no relatório.
- Relatório de fechamento em `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-7.md` (template `docs/prompts/templates/RELATORIO-FECHAMENTO.md`).
- Não invente resultados. Se algo falhar ou estiver bloqueado, registre e pare.

Commit ao concluir:
`AILAB-7 feat(evals): goldens, tracing e guardrails`
```

---

## 3. Rastreabilidade

| Campo | Valor |
| --- | --- |
| Jira | [AILAB-7](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-7) (login) |
| Épico | [AILAB-1](../epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md) |
| Prompt canônico | `docs/prompts/tasks/AILAB-7_evals-tracing-guardrails-minimizacao.md` |
| Versão do prompt | `2.0.0` |
| ID legado | `AILAB-PROMPT-006-EVALS-GUARDRAILS` |
| Branch sugerida | `feature/AILAB-7-evals-guardrails` |
| Convenção de commit | `AILAB-7 feat(evals): goldens, tracing e guardrails` |
| Relatório de fechamento | `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-7.md` |
| Mapa / manifesto | [EPIC-TASK-MAP](../../map/EPIC-TASK-MAP.md) · [jira-manifest.json](../../map/jira-manifest.json) |

## 4. Histórico de Versões do Prompt

* **v1.0.0 (2026-11-08):** `prompts/vscode/AILAB-PROMPT-006-EVALS-GUARDRAILS.v1.md` — formato frontmatter + seções curtas (removido; consultar histórico Git).
* **v2.0.0 (2026-11-09 — Atual):** reestruturado no padrão de catálogo canônico: arquivo nomeado pela chave Jira, prompt canônico espelhando a issue, prompt executivo com ritual de início de turno, rastreabilidade e relatório de fechamento.
