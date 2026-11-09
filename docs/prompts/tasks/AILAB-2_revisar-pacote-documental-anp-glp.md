---
jira_key: AILAB-2
tipo: Tarefa
lab: LAB-01
fase: "1"
epico_pai: AILAB-1
executor: humano
risco: low
status_jira_snapshot: A fazer
prompt_version: 2.0.0
legacy_prompt_id: AILAB-PROMPT-001-REVIEW-DOCS
supersedes: prompts/vscode/AILAB-PROMPT-001-REVIEW-DOCS.v1.md
atualizado: "2026-11-09 14:21 America/Sao_Paulo"
---

# AILAB-2 — [LAB-01] Revisar e aceitar pacote documental ANP GLP

**Tipo:** Tarefa  
**Status no Jira:** A fazer (snapshot 2026-11-09 14:21 America/Sao_Paulo)  
**Projeto:** AILAB  
**Épico Pai:** AILAB-1  
**Fase:** 1 · **Risco:** low  
**Papéis:** Executor: Luciano | Arquiteto / Revisor: **Luciano Teixeira**  
**Precedência:** bloqueada por — · bloqueia AILAB-3  
**Governança:** Issue-as-a-Prompt — este arquivo espelha a issue [AILAB-2](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-2) (Jira exige login)

---

## 1. Conteúdo do Prompt Canônico

## 📋 [ISSUE-AS-A-PROMPT] — AILAB-2: [LAB-01] Revisar e aceitar pacote documental ANP GLP

### 1.1 Contexto & Objetivo

Revisar o pacote documental publicado (PRD, arquitetura, design system, ADRs 001–006, threat model, testes/evals, runbook, backlog, mapa e catálogo de prompts) e registrar aceite ou lista objetiva de ajustes. Sem código.

- Documentação publicada em `docs/` no repo; catálogo de prompts em `docs/prompts/`.
- ADRs permanecem Proposto até aceite explícito do Luciano.

### 1.2 Escopo técnico & arquivos

- `README.md`
- `docs/00-PRD.md … docs/08-REPRODUCIBILITY.md`
- `docs/adrs/ADR-001..006`
- `docs/backlog/`
- `docs/map/`
- `docs/prompts/`

### 1.3 Fora de escopo

- Implementação de código.
- Criação de novas issues.
- Provisionamento de cloud.

### 1.4 Passos de execução do agente

1. Ler README e PRD; conferir jornadas J1–J3.
2. Validar ADRs (Proposto) e separação fase 1 × fase 2.
3. Confirmar minimização de dados (ADR-006) e FakeProvider só em testes (ADR-001).
4. Conferir que links do catálogo, mapa e manifesto resolvem.
5. Registrar aceite ou diffs em `docs/relatorios/` usando o template REVIEW-RECONCILE.

### 1.5 Testes / verificação

- Checklist J1–J3 coberto pelos docs.
- Nenhum dado fictício apresentado como real nos docs ativos.
- Fase 2 explicitamente condicionada a autorização.

### 1.6 Definition of Done (DoD)

- [ ] Aceite humano ou lista de ajustes registrada
- [ ] Relatório de revisão versionado
- [ ] ADRs com status decidido pelo Luciano

### 1.7 Ações proibidas

- Marcar Done sem leitura completa.
- Aceitar ADRs em nome do Luciano.
- Commitar segredos (API keys, tokens, `.env`) ou dados pessoais.
- Republicar o cadastro ANP completo: snapshot mínimo, datado e sanitizado.
- Calcular métricas/contagens com o LLM — sempre em código (Python/SQL).
- Usar FakeProvider fora de testes rotulados.
- Marcar a issue como Done, aceitar ADRs ou fazer merge sem revisão do Luciano.
- Provisionar cloud ou gerar custo sem autorização explícita.

### 1.8 Escalonamento

- Ajuste pontual de ADR → propor diff; não redesenhar o épico sem o Luciano.

---

## 2. Prompt Executivo (colar no chat do agente no VS Code)

```markdown
Atue sob as regras de `AGENTS.md` e `docs/prompts/CORE-RULES.md`.
Tarefa: AILAB-2 — [LAB-01] Revisar e aceitar pacote documental ANP GLP
Prompt canônico: `docs/prompts/tasks/AILAB-2_revisar-pacote-documental-anp-glp.md` (v2.0.0).

### 🛡️ RITUAL OBRIGATÓRIO DE INÍCIO DE TURNO
1. Idempotência: rode `git log --oneline --grep="AILAB-2"`. Se a entrega já estiver no histórico e os testes passarem, pare e responda: `[IDEMPOTÊNCIA] AILAB-2 já executada`.
2. Branch: `git branch --show-current` deve ser `docs/AILAB-2-revisao-pacote`. Se não for, crie-a a partir de `main` atualizada.
3. Imersão: leia o prompt canônico, os docs/ADRs citados na seção 1.1 e o código existente antes de editar. Arquivos-alvo (criar ou alterar): `README.md`, `docs/00-PRD.md … docs/08-REPRODUCIBILITY.md`, `docs/adrs/ADR-001..006`, `docs/backlog/`, `docs/map/`, `docs/prompts/`.
4. Runner: use somente o Python do `.venv` (`python -m pytest`, `python -m ruff check .`).
5. Pré-requisitos: confirme que — está concluída (sem bloqueios). Caso contrário, pare e avise.

### 📋 ESCOPO (AILAB-2)
1. Ler README e PRD; conferir jornadas J1–J3.
2. Validar ADRs (Proposto) e separação fase 1 × fase 2.
3. Confirmar minimização de dados (ADR-006) e FakeProvider só em testes (ADR-001).
4. Conferir que links do catálogo, mapa e manifesto resolvem.
5. Registrar aceite ou diffs em `docs/relatorios/` usando o template REVIEW-RECONCILE.

### ✅ SAÍDA ESPERADA
- Testes da seção 1.5 do prompt canônico executados, com saída real colada no relatório.
- Relatório de fechamento em `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-2.md` (template `docs/prompts/templates/RELATORIO-FECHAMENTO.md`).
- Não invente resultados. Se algo falhar ou estiver bloqueado, registre e pare.

Commit ao concluir:
`AILAB-2 docs: registra revisão do pacote documental`
```

---

## 3. Rastreabilidade

| Campo | Valor |
| --- | --- |
| Jira | [AILAB-2](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-2) (login) |
| Épico | [AILAB-1](../epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md) |
| Prompt canônico | `docs/prompts/tasks/AILAB-2_revisar-pacote-documental-anp-glp.md` |
| Versão do prompt | `2.0.0` |
| ID legado | `AILAB-PROMPT-001-REVIEW-DOCS` |
| Branch sugerida | `docs/AILAB-2-revisao-pacote` |
| Convenção de commit | `AILAB-2 docs: registra revisão do pacote documental` |
| Relatório de fechamento | `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-2.md` |
| Mapa / manifesto | [EPIC-TASK-MAP](../../map/EPIC-TASK-MAP.md) · [jira-manifest.json](../../map/jira-manifest.json) |

## 4. Histórico de Versões do Prompt

* **v1.0.0 (2026-11-08):** `prompts/vscode/AILAB-PROMPT-001-REVIEW-DOCS.v1.md` — formato frontmatter + seções curtas (removido; consultar histórico Git).
* **v2.0.0 (2026-11-09 — Atual):** reestruturado no padrão de catálogo canônico: arquivo nomeado pela chave Jira, prompt canônico espelhando a issue, prompt executivo com ritual de início de turno, rastreabilidade e relatório de fechamento.
