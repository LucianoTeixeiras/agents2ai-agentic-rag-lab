---
jira_key: AILAB-9
tipo: Tarefa
lab: LAB-08
fase: "2"
epico_pai: AILAB-1
executor: vscode
risco: high
status_jira_snapshot: A fazer
prompt_version: 2.0.0
legacy_prompt_id: AILAB-PROMPT-008-AZURE-OPENAI
supersedes: prompts/vscode/AILAB-PROMPT-008-AZURE-OPENAI.v1.md
atualizado: "2026-11-09 14:21 America/Sao_Paulo"
---

# AILAB-9 — [LAB-08][Fase 2] Azure OpenAI prático (credenciais/custo autorizados)

**Tipo:** Tarefa  
**Status no Jira:** A fazer (snapshot 2026-11-09 14:21 America/Sao_Paulo)  
**Projeto:** AILAB  
**Épico Pai:** AILAB-1  
**Fase:** 2 · **Risco:** high  
**Papéis:** Executor: agente no VS Code | Arquiteto / Revisor: **Luciano Teixeira**  
**Precedência:** bloqueada por AILAB-8 · bloqueia —  
**Governança:** Issue-as-a-Prompt — este arquivo espelha a issue [AILAB-9](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-9) (Jira exige login)

---

## 1. Conteúdo do Prompt Canônico

## 📋 [ISSUE-AS-A-PROMPT] — AILAB-9: [LAB-08][Fase 2] Azure OpenAI prático (credenciais/custo autorizados)

### 1.1 Contexto & Objetivo

Integrar Azure OpenAI de fato (adapter real), somente com credenciais e orçamento autorizados pelo Luciano. Sem autorização: registrar bloqueio explícito, sem stub cosmético. A fase 1 continua funcionando sem custo.

- ADR-005 (fase 2 Azure/Databricks).
- Credenciais apenas em `.env` local, nunca no Git.

### 1.2 Escopo técnico & arquivos

- `src/anp_lab/llm/azure_openai.py`
- `.env.example` (apenas nomes)
- `tests/llm/`

### 1.3 Fora de escopo

- Provisionamento sem aprovação.
- CI pago por padrão.

### 1.4 Passos de execução do agente

1. Confirmar autorização de credenciais e orçamento.
2. Implementar adapter com seleção por variável de ambiente.
3. Testes com mock + smoke autorizado.
4. Documentar rollback para fase 1.

### 1.5 Testes / verificação

- Testes com mock verdes.
- Smoke autorizado registrado no relatório.
- Default fase 1 inalterado.

### 1.6 Definition of Done (DoD)

- [ ] Execução real autorizada ou bloqueio documentado
- [ ] Zero segredos
- [ ] Default fase 1 intacto

### 1.7 Ações proibidas

- Keys no Git.
- Commitar segredos (API keys, tokens, `.env`) ou dados pessoais.
- Republicar o cadastro ANP completo: snapshot mínimo, datado e sanitizado.
- Calcular métricas/contagens com o LLM — sempre em código (Python/SQL).
- Usar FakeProvider fora de testes rotulados.
- Marcar a issue como Done, aceitar ADRs ou fazer merge sem revisão do Luciano.
- Provisionar cloud ou gerar custo sem autorização explícita.

### 1.8 Escalonamento

- Sem acesso/créditos → parar e registrar bloqueio.

---

## 2. Prompt Executivo (colar no chat do agente no VS Code)

```markdown
Atue sob as regras de `AGENTS.md` e `docs/prompts/CORE-RULES.md`.
Tarefa: AILAB-9 — [LAB-08][Fase 2] Azure OpenAI prático (credenciais/custo autorizados)
Prompt canônico: `docs/prompts/tasks/AILAB-9_fase2-azure-openai-pratico.md` (v2.0.0).

### 🛡️ RITUAL OBRIGATÓRIO DE INÍCIO DE TURNO
1. Idempotência: rode `git log --oneline --grep="AILAB-9"`. Se a entrega já estiver no histórico e os testes passarem, pare e responda: `[IDEMPOTÊNCIA] AILAB-9 já executada`.
2. Branch: `git branch --show-current` deve ser `feature/AILAB-9-azure-openai`. Se não for, crie-a a partir de `main` atualizada.
3. Imersão: leia o prompt canônico, os docs/ADRs citados na seção 1.1 e o código existente antes de editar. Arquivos-alvo (criar ou alterar): `src/anp_lab/llm/azure_openai.py`, `.env.example`, `tests/llm/`.
4. Runner: use somente o Python do `.venv` (`python -m pytest`, `python -m ruff check .`).
5. Pré-requisitos: confirme que AILAB-8 está concluída. Caso contrário, pare e avise.

### 📋 ESCOPO (AILAB-9)
1. Confirmar autorização de credenciais e orçamento.
2. Implementar adapter com seleção por variável de ambiente.
3. Testes com mock + smoke autorizado.
4. Documentar rollback para fase 1.

### ✅ SAÍDA ESPERADA
- Testes da seção 1.5 do prompt canônico executados, com saída real colada no relatório.
- Relatório de fechamento em `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-9.md` (template `docs/prompts/templates/RELATORIO-FECHAMENTO.md`).
- Não invente resultados. Se algo falhar ou estiver bloqueado, registre e pare.

Commit ao concluir:
`AILAB-9 feat(llm): adapter Azure OpenAI`
```

---

## 3. Rastreabilidade

| Campo | Valor |
| --- | --- |
| Jira | [AILAB-9](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-9) (login) |
| Épico | [AILAB-1](../epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md) |
| Prompt canônico | `docs/prompts/tasks/AILAB-9_fase2-azure-openai-pratico.md` |
| Versão do prompt | `2.0.0` |
| ID legado | `AILAB-PROMPT-008-AZURE-OPENAI` |
| Branch sugerida | `feature/AILAB-9-azure-openai` |
| Convenção de commit | `AILAB-9 feat(llm): adapter Azure OpenAI` |
| Relatório de fechamento | `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-9.md` |
| Mapa / manifesto | [EPIC-TASK-MAP](../../map/EPIC-TASK-MAP.md) · [jira-manifest.json](../../map/jira-manifest.json) |

## 4. Histórico de Versões do Prompt

* **v1.0.0 (2026-11-08):** `prompts/vscode/AILAB-PROMPT-008-AZURE-OPENAI.v1.md` — formato frontmatter + seções curtas (removido; consultar histórico Git).
* **v2.0.0 (2026-11-09 — Atual):** reestruturado no padrão de catálogo canônico: arquivo nomeado pela chave Jira, prompt canônico espelhando a issue, prompt executivo com ritual de início de turno, rastreabilidade e relatório de fechamento.
