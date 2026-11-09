---
jira_key: AILAB-3
tipo: Tarefa
lab: LAB-02
fase: "1"
epico_pai: AILAB-1
executor: vscode
risco: low
status_jira_snapshot: A fazer
prompt_version: 2.0.0
legacy_prompt_id: AILAB-PROMPT-002-BOOTSTRAP
supersedes: prompts/vscode/AILAB-PROMPT-002-BOOTSTRAP.v1.md
atualizado: "2026-11-09 14:21 America/Sao_Paulo"
---

# AILAB-3 — [LAB-02] Bootstrap VS Code no repo existente (docs ANP)

**Tipo:** Tarefa  
**Status no Jira:** A fazer (snapshot 2026-11-09 14:21 America/Sao_Paulo)  
**Projeto:** AILAB  
**Épico Pai:** AILAB-1  
**Fase:** 1 · **Risco:** low  
**Papéis:** Executor: agente no VS Code | Arquiteto / Revisor: **Luciano Teixeira**  
**Precedência:** bloqueada por AILAB-2 · bloqueia AILAB-4, AILAB-5  
**Governança:** Issue-as-a-Prompt — este arquivo espelha a issue [AILAB-3](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-3) (Jira exige login)

---

## 1. Conteúdo do Prompt Canônico

## 📋 [ISSUE-AS-A-PROMPT] — AILAB-3: [LAB-02] Bootstrap VS Code no repo existente (docs ANP)

### 1.1 Contexto & Objetivo

Preparar o esqueleto Python no repo já existente (sem criar outro repo): ambiente virtual do VS Code, `pyproject.toml` com dependências pinadas, estrutura `src/` e `tests/`, `.gitignore`, `.env.example` sem valores, LICENSE e README com atribuição ANP.

- A documentação já está em `docs/`; não copiar nem duplicar.
- Runner oficial: Python do `.venv` (`python -m pytest`, `python -m ruff`).

### 1.2 Escopo técnico & arquivos

- `pyproject.toml`
- `.gitignore`
- `.env.example`
- `LICENSE`
- `README.md`
- `src/anp_lab/__init__.py`
- `tests/test_smoke.py`

### 1.3 Fora de escopo

- Implementar RAG, MCP ou API.
- Integração Azure/Databricks.
- Baixar dump ANP.

### 1.4 Passos de execução do agente

1. Clonar o repo, abrir no VS Code e criar o `.venv` (Python: Create Environment).
2. Criar `pyproject.toml` com dependências mínimas pinadas (fastapi, pydantic, httpx, pytest, ruff).
3. Criar `src/anp_lab/` e `tests/test_smoke.py`.
4. Atualizar `.gitignore` (venv, `.env`, caches, `data/raw/`) e criar `.env.example` só com nomes de variáveis.
5. Atualizar README: como rodar, fonte ANP, atribuição, snapshot vs live, fase 2 planejada.
6. Rodar scan de segredos antes do commit.

### 1.5 Testes / verificação

- `python -m pytest` verde em clone fresco.
- `python -m ruff check .` sem erros.
- Scan de segredos sem achados.

### 1.6 Definition of Done (DoD)

- [ ] Clone fresco roda smoke test
- [ ] Zero segredos
- [ ] README revisado pelo Luciano

### 1.7 Ações proibidas

- Criar novo repositório.
- Alegar MCP/Azure implementados.
- Commitar segredos (API keys, tokens, `.env`) ou dados pessoais.
- Republicar o cadastro ANP completo: snapshot mínimo, datado e sanitizado.
- Calcular métricas/contagens com o LLM — sempre em código (Python/SQL).
- Usar FakeProvider fora de testes rotulados.
- Marcar a issue como Done, aceitar ADRs ou fazer merge sem revisão do Luciano.
- Provisionar cloud ou gerar custo sem autorização explícita.

### 1.8 Escalonamento

- Problema de autenticação GitHub → Luciano.

---

## 2. Prompt Executivo (colar no chat do agente no VS Code)

```markdown
Atue sob as regras de `AGENTS.md` e `docs/prompts/CORE-RULES.md`.
Tarefa: AILAB-3 — [LAB-02] Bootstrap VS Code no repo existente (docs ANP)
Prompt canônico: `docs/prompts/tasks/AILAB-3_bootstrap-vscode-repo-existente.md` (v2.0.0).

### 🛡️ RITUAL OBRIGATÓRIO DE INÍCIO DE TURNO
1. Idempotência: rode `git log --oneline --grep="AILAB-3"`. Se a entrega já estiver no histórico e os testes passarem, pare e responda: `[IDEMPOTÊNCIA] AILAB-3 já executada`.
2. Branch: `git branch --show-current` deve ser `feature/AILAB-3-bootstrap`. Se não for, crie-a a partir de `main` atualizada.
3. Imersão: leia o prompt canônico, os docs/ADRs citados na seção 1.1 e o código existente antes de editar. Arquivos-alvo (criar ou alterar): `pyproject.toml`, `.gitignore`, `.env.example`, `LICENSE`, `README.md`, `src/anp_lab/__init__.py`, `tests/test_smoke.py`.
4. Runner: use somente o Python do `.venv` (`python -m pytest`, `python -m ruff check .`).
5. Pré-requisitos: confirme que AILAB-2 está concluída. Caso contrário, pare e avise.

### 📋 ESCOPO (AILAB-3)
1. Clonar o repo, abrir no VS Code e criar o `.venv` (Python: Create Environment).
2. Criar `pyproject.toml` com dependências mínimas pinadas (fastapi, pydantic, httpx, pytest, ruff).
3. Criar `src/anp_lab/` e `tests/test_smoke.py`.
4. Atualizar `.gitignore` (venv, `.env`, caches, `data/raw/`) e criar `.env.example` só com nomes de variáveis.
5. Atualizar README: como rodar, fonte ANP, atribuição, snapshot vs live, fase 2 planejada.
6. Rodar scan de segredos antes do commit.

### ✅ SAÍDA ESPERADA
- Testes da seção 1.5 do prompt canônico executados, com saída real colada no relatório.
- Relatório de fechamento em `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-3.md` (template `docs/prompts/templates/RELATORIO-FECHAMENTO.md`).
- Não invente resultados. Se algo falhar ou estiver bloqueado, registre e pare.

Commit ao concluir:
`AILAB-3 chore(bootstrap): estrutura Python, venv e README`
```

---

## 3. Rastreabilidade

| Campo | Valor |
| --- | --- |
| Jira | [AILAB-3](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-3) (login) |
| Épico | [AILAB-1](../epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md) |
| Prompt canônico | `docs/prompts/tasks/AILAB-3_bootstrap-vscode-repo-existente.md` |
| Versão do prompt | `2.0.0` |
| ID legado | `AILAB-PROMPT-002-BOOTSTRAP` |
| Branch sugerida | `feature/AILAB-3-bootstrap` |
| Convenção de commit | `AILAB-3 chore(bootstrap): estrutura Python, venv e README` |
| Relatório de fechamento | `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-3.md` |
| Mapa / manifesto | [EPIC-TASK-MAP](../../map/EPIC-TASK-MAP.md) · [jira-manifest.json](../../map/jira-manifest.json) |

## 4. Histórico de Versões do Prompt

* **v1.0.0 (2026-11-08):** `prompts/vscode/AILAB-PROMPT-002-BOOTSTRAP.v1.md` — formato frontmatter + seções curtas (removido; consultar histórico Git).
* **v2.0.0 (2026-11-09 — Atual):** reestruturado no padrão de catálogo canônico: arquivo nomeado pela chave Jira, prompt canônico espelhando a issue, prompt executivo com ritual de início de turno, rastreabilidade e relatório de fechamento.
