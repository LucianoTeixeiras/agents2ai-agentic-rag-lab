---
jira_key: AILAB-8
tipo: Tarefa
lab: LAB-07
fase: "1"
epico_pai: AILAB-1
executor: vscode
risco: low
status_jira_snapshot: A fazer
prompt_version: 2.0.0
legacy_prompt_id: AILAB-PROMPT-007-CI-DEMO
supersedes: prompts/vscode/AILAB-PROMPT-007-CI-DEMO.v1.md
atualizado: "2026-11-09 14:21 America/Sao_Paulo"
---

# AILAB-8 — [LAB-07] CI snapshot + demo 5 min + README ANP

**Tipo:** Tarefa  
**Status no Jira:** A fazer (snapshot 2026-11-09 14:21 America/Sao_Paulo)  
**Projeto:** AILAB  
**Épico Pai:** AILAB-1  
**Fase:** 1 · **Risco:** low  
**Papéis:** Executor: agente no VS Code | Arquiteto / Revisor: **Luciano Teixeira**  
**Precedência:** bloqueada por AILAB-7 · bloqueia AILAB-9, AILAB-10  
**Governança:** Issue-as-a-Prompt — este arquivo espelha a issue [AILAB-8](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-8) (Jira exige login)

---

## 1. Conteúdo do Prompt Canônico

## 📋 [ISSUE-AS-A-PROMPT] — AILAB-8: [LAB-07] CI snapshot + demo 5 min + README ANP

### 1.1 Contexto & Objetivo

CI (lint + pytest + evals) sem chamadas live à ANP, roteiro de demo de 5 minutos e README final com atribuição, limites, gaps e fase 2 planejada.

- Runbook em `docs/06-RUNBOOK-DEMO.md`; maturidade em `docs/07-MATURITY-AND-GAPS.md`.

### 1.2 Escopo técnico & arquivos

- `.github/workflows/ci.yml`
- `scripts/demo.sh` (ou .ps1)
- `README.md`

### 1.3 Fora de escopo

- Provisionar cloud.
- Done do épico sem aceite humano.

### 1.4 Passos de execução do agente

1. Workflow CI com snapshot datado e live desligado.
2. Script de demo de 5 min.
3. README: fontes, atribuição, gaps honestos.
4. Atualizar checklist de maturidade.

### 1.5 Testes / verificação

- CI verde no PR.
- Demo executada uma vez e registrada no relatório.

### 1.6 Definition of Done (DoD)

- [ ] CI verde
- [ ] Demo executada uma vez
- [ ] Gaps e fase 2 explícitos

### 1.7 Ações proibidas

- Live no CI.
- Alegar integração GitHub↔Jira não verificada.
- Commitar segredos (API keys, tokens, `.env`) ou dados pessoais.
- Republicar o cadastro ANP completo: snapshot mínimo, datado e sanitizado.
- Calcular métricas/contagens com o LLM — sempre em código (Python/SQL).
- Usar FakeProvider fora de testes rotulados.
- Marcar a issue como Done, aceitar ADRs ou fazer merge sem revisão do Luciano.
- Provisionar cloud ou gerar custo sem autorização explícita.

### 1.8 Escalonamento

- CI falhando → corrigir sem inventar dados.

---

## 2. Prompt Executivo (colar no chat do agente no VS Code)

```markdown
Atue sob as regras de `AGENTS.md` e `docs/prompts/CORE-RULES.md`.
Tarefa: AILAB-8 — [LAB-07] CI snapshot + demo 5 min + README ANP
Prompt canônico: `docs/prompts/tasks/AILAB-8_ci-snapshot-demo-readme.md` (v2.0.0).

### 🛡️ RITUAL OBRIGATÓRIO DE INÍCIO DE TURNO
1. Idempotência: rode `git log --oneline --grep="AILAB-8"`. Se a entrega já estiver no histórico e os testes passarem, pare e responda: `[IDEMPOTÊNCIA] AILAB-8 já executada`.
2. Branch: `git branch --show-current` deve ser `feature/AILAB-8-ci-demo`. Se não for, crie-a a partir de `main` atualizada.
3. Imersão: leia o prompt canônico, os docs/ADRs citados na seção 1.1 e o código existente antes de editar. Arquivos-alvo (criar ou alterar): `.github/workflows/ci.yml`, `scripts/demo.sh`, `README.md`.
4. Runner: use somente o Python do `.venv` (`python -m pytest`, `python -m ruff check .`).
5. Pré-requisitos: confirme que AILAB-7 está concluída. Caso contrário, pare e avise.

### 📋 ESCOPO (AILAB-8)
1. Workflow CI com snapshot datado e live desligado.
2. Script de demo de 5 min.
3. README: fontes, atribuição, gaps honestos.
4. Atualizar checklist de maturidade.

### ✅ SAÍDA ESPERADA
- Testes da seção 1.5 do prompt canônico executados, com saída real colada no relatório.
- Relatório de fechamento em `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-8.md` (template `docs/prompts/templates/RELATORIO-FECHAMENTO.md`).
- Não invente resultados. Se algo falhar ou estiver bloqueado, registre e pare.

Commit ao concluir:
`AILAB-8 ci: pipeline snapshot e roteiro de demo`
```

---

## 3. Rastreabilidade

| Campo | Valor |
| --- | --- |
| Jira | [AILAB-8](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-8) (login) |
| Épico | [AILAB-1](../epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md) |
| Prompt canônico | `docs/prompts/tasks/AILAB-8_ci-snapshot-demo-readme.md` |
| Versão do prompt | `2.0.0` |
| ID legado | `AILAB-PROMPT-007-CI-DEMO` |
| Branch sugerida | `feature/AILAB-8-ci-demo` |
| Convenção de commit | `AILAB-8 ci: pipeline snapshot e roteiro de demo` |
| Relatório de fechamento | `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-8.md` |
| Mapa / manifesto | [EPIC-TASK-MAP](../../map/EPIC-TASK-MAP.md) · [jira-manifest.json](../../map/jira-manifest.json) |

## 4. Histórico de Versões do Prompt

* **v1.0.0 (2026-11-08):** `prompts/vscode/AILAB-PROMPT-007-CI-DEMO.v1.md` — formato frontmatter + seções curtas (removido; consultar histórico Git).
* **v2.0.0 (2026-11-09 — Atual):** reestruturado no padrão de catálogo canônico: arquivo nomeado pela chave Jira, prompt canônico espelhando a issue, prompt executivo com ritual de início de turno, rastreabilidade e relatório de fechamento.
