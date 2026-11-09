---
jira_key: AILAB-4
tipo: Tarefa
lab: LAB-03
fase: "1"
epico_pai: AILAB-1
executor: vscode
risco: medium
status_jira_snapshot: A fazer
prompt_version: 2.0.0
legacy_prompt_id: AILAB-PROMPT-003-RAG-DOCS
supersedes: prompts/vscode/AILAB-PROMPT-003-RAG-DOCS.v1.md
atualizado: "2026-11-09 14:21 America/Sao_Paulo"
---

# AILAB-4 — [LAB-03] RAG: corpus oficial ANP (manual/metadata) + citações

**Tipo:** Tarefa  
**Status no Jira:** A fazer (snapshot 2026-11-09 14:21 America/Sao_Paulo)  
**Projeto:** AILAB  
**Épico Pai:** AILAB-1  
**Fase:** 1 · **Risco:** medium  
**Papéis:** Executor: agente no VS Code | Arquiteto / Revisor: **Luciano Teixeira**  
**Precedência:** bloqueada por AILAB-3 · bloqueia AILAB-6  
**Governança:** Issue-as-a-Prompt — este arquivo espelha a issue [AILAB-4](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-4) (Jira exige login)

---

## 1. Conteúdo do Prompt Canônico

## 📋 [ISSUE-AS-A-PROMPT] — AILAB-4: [LAB-03] RAG: corpus oficial ANP (manual/metadata) + citações

### 1.1 Contexto & Objetivo

RAG lexical (ADR-003) sobre o corpus oficial da ANP — manual da API Revendedores, Swagger e páginas de dados abertos — com chunk ids estáveis, citações obrigatórias e abstenção quando a resposta não está no corpus.

- Fontes listadas em `docs/SOURCES.md`.
- Texto derivado versionado com nota de origem e data de coleta.

### 1.2 Escopo técnico & arquivos

- `data/corpus/anp/`
- `src/anp_lab/rag/`
- `tests/rag/`

### 1.3 Fora de escopo

- Embeddings pagos sem autorização.
- Corpus, políticas ou campos inventados.

### 1.4 Passos de execução do agente

1. Extrair trechos oficiais com atribuição e `retrieved_at`.
2. Gerar chunks com ids estáveis.
3. Implementar retrieve top-k lexical com citações (fonte + chunk).
4. Implementar abstenção fora do corpus.
5. Criar testes golden G01–G03.

### 1.5 Testes / verificação

- G01 paginação 5k → citação do manual.
- G02 filtros uf/municipio/cnpj → citação.
- G03 campo inexistente → abstém.

### 1.6 Definition of Done (DoD)

- [ ] Citações oficiais em toda resposta documental
- [ ] Abstenção testada
- [ ] G01–G03 verdes
- [ ] Atribuição ANP no corpus

### 1.7 Ações proibidas

- Afirmar licença não confirmada como fato.
- Commitar segredos (API keys, tokens, `.env`) ou dados pessoais.
- Republicar o cadastro ANP completo: snapshot mínimo, datado e sanitizado.
- Calcular métricas/contagens com o LLM — sempre em código (Python/SQL).
- Usar FakeProvider fora de testes rotulados.
- Marcar a issue como Done, aceitar ADRs ou fazer merge sem revisão do Luciano.
- Provisionar cloud ou gerar custo sem autorização explícita.

### 1.8 Escalonamento

- Parsing de PDF pesado → texto pré-extraído no repo com nota de origem.

---

## 2. Prompt Executivo (colar no chat do agente no VS Code)

```markdown
Atue sob as regras de `AGENTS.md` e `docs/prompts/CORE-RULES.md`.
Tarefa: AILAB-4 — [LAB-03] RAG: corpus oficial ANP (manual/metadata) + citações
Prompt canônico: `docs/prompts/tasks/AILAB-4_rag-corpus-oficial-anp-citacoes.md` (v2.0.0).

### 🛡️ RITUAL OBRIGATÓRIO DE INÍCIO DE TURNO
1. Idempotência: rode `git log --oneline --grep="AILAB-4"`. Se a entrega já estiver no histórico e os testes passarem, pare e responda: `[IDEMPOTÊNCIA] AILAB-4 já executada`.
2. Branch: `git branch --show-current` deve ser `feature/AILAB-4-rag-docs`. Se não for, crie-a a partir de `main` atualizada.
3. Imersão: leia o prompt canônico, os docs/ADRs citados na seção 1.1 e o código existente antes de editar. Arquivos-alvo (criar ou alterar): `data/corpus/anp/`, `src/anp_lab/rag/`, `tests/rag/`.
4. Runner: use somente o Python do `.venv` (`python -m pytest`, `python -m ruff check .`).
5. Pré-requisitos: confirme que AILAB-3 está concluída. Caso contrário, pare e avise.

### 📋 ESCOPO (AILAB-4)
1. Extrair trechos oficiais com atribuição e `retrieved_at`.
2. Gerar chunks com ids estáveis.
3. Implementar retrieve top-k lexical com citações (fonte + chunk).
4. Implementar abstenção fora do corpus.
5. Criar testes golden G01–G03.

### ✅ SAÍDA ESPERADA
- Testes da seção 1.5 do prompt canônico executados, com saída real colada no relatório.
- Relatório de fechamento em `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-4.md` (template `docs/prompts/templates/RELATORIO-FECHAMENTO.md`).
- Não invente resultados. Se algo falhar ou estiver bloqueado, registre e pare.

Commit ao concluir:
`AILAB-4 feat(rag): corpus oficial ANP com citações`
```

---

## 3. Rastreabilidade

| Campo | Valor |
| --- | --- |
| Jira | [AILAB-4](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-4) (login) |
| Épico | [AILAB-1](../epicos/AILAB-1_epic-lab-anp-glp-rag-mcp-fastapi.md) |
| Prompt canônico | `docs/prompts/tasks/AILAB-4_rag-corpus-oficial-anp-citacoes.md` |
| Versão do prompt | `2.0.0` |
| ID legado | `AILAB-PROMPT-003-RAG-DOCS` |
| Branch sugerida | `feature/AILAB-4-rag-docs` |
| Convenção de commit | `AILAB-4 feat(rag): corpus oficial ANP com citações` |
| Relatório de fechamento | `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-AILAB-4.md` |
| Mapa / manifesto | [EPIC-TASK-MAP](../../map/EPIC-TASK-MAP.md) · [jira-manifest.json](../../map/jira-manifest.json) |

## 4. Histórico de Versões do Prompt

* **v1.0.0 (2026-11-08):** `prompts/vscode/AILAB-PROMPT-003-RAG-DOCS.v1.md` — formato frontmatter + seções curtas (removido; consultar histórico Git).
* **v2.0.0 (2026-11-09 — Atual):** reestruturado no padrão de catálogo canônico: arquivo nomeado pela chave Jira, prompt canônico espelhando a issue, prompt executivo com ritual de início de turno, rastreabilidade e relatório de fechamento.
