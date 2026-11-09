# Catálogo de prompts — reprodutibilidade

**Snapshot:** 2026-11-08 21:42 America/Sao_Paulo · **Locale:** pt-BR · **Schema catálogo:** 1.0.0

## Distinção importante

| Família | Pasta | Quando usar |
| --- | --- | --- |
| **VS Code / Issue-as-a-Prompt** | `prompts/vscode/` | Execução humana+IDE das tarefas AILAB (agora) |
| **Runtime / agent / evals** | `prompts/runtime/` | **Reservado** — prompts de sistema/ferramenta/eval em runtime futuro; **vazios de implementação** nesta versão |

Não misturar: um Issue-as-a-Prompt **não** é o system prompt do agente em produção.

## Index

| ID | Versão | Jira | Executor | Path | Status |
| --- | --- | --- | --- | --- | --- |
| `AILAB-PROMPT-000-EPIC` | 1.0.0 | AILAB-1 | mixed | `prompts/vscode/AILAB-PROMPT-000-EPIC.v1.md` | draft |
| `AILAB-PROMPT-001-REVIEW-DOCS` | 1.0.0 | AILAB-2 | humano | `prompts/vscode/AILAB-PROMPT-001-REVIEW-DOCS.v1.md` | draft |
| `AILAB-PROMPT-002-BOOTSTRAP` | 1.0.0 | AILAB-3 | vscode | `prompts/vscode/AILAB-PROMPT-002-BOOTSTRAP.v1.md` | draft |
| `AILAB-PROMPT-003-RAG-DOCS` | 1.0.0 | AILAB-4 | vscode | `prompts/vscode/AILAB-PROMPT-003-RAG-DOCS.v1.md` | draft |
| `AILAB-PROMPT-004-MCP-ANP` | 1.0.0 | AILAB-5 | vscode | `prompts/vscode/AILAB-PROMPT-004-MCP-ANP.v1.md` | draft |
| `AILAB-PROMPT-005-FASTAPI-E2E` | 1.0.0 | AILAB-6 | vscode | `prompts/vscode/AILAB-PROMPT-005-FASTAPI-E2E.v1.md` | draft |
| `AILAB-PROMPT-006-EVALS-GUARDRAILS` | 1.0.0 | AILAB-7 | vscode | `prompts/vscode/AILAB-PROMPT-006-EVALS-GUARDRAILS.v1.md` | draft |
| `AILAB-PROMPT-007-CI-DEMO` | 1.0.0 | AILAB-8 | vscode | `prompts/vscode/AILAB-PROMPT-007-CI-DEMO.v1.md` | draft |
| `AILAB-PROMPT-008-AZURE-OPENAI` | 1.0.0 | AILAB-9 | vscode | `prompts/vscode/AILAB-PROMPT-008-AZURE-OPENAI.v1.md` | draft |
| `AILAB-PROMPT-009-DATABRICKS` | 1.0.0 | AILAB-10 | vscode | `prompts/vscode/AILAB-PROMPT-009-DATABRICKS.v1.md` | draft |

## Versionamento

- ID estável (`AILAB-PROMPT-00N-...`); versão semver no frontmatter e no nome `*.v1.md`.
- Breaking change → novo arquivo `*.v2.md` + atualizar manifesto `prompt_version`/`prompt_path`.
- `supersedes` no frontmatter aponta versão anterior.

## Aviso de não-determinismo

Mesmo com prompt+deps+corpus pinados, **saídas de LLM podem variar**. Reprodutibilidade aqui = **processo** (mesmos inputs, versões, checks), não bit-identical text. Sempre gravar model/config/seed se houver e evidências no execution record.
