# Reprodutibilidade e sincronia de ambientes

**Atualizado:** 2026-11-09 14:21 America/Sao_Paulo

## Princípio

| O quê | Onde |
| --- | --- |
| Status / prioridade / workflow | **Jira** (fonte operacional) |
| Specs, ADRs, mapa, prompts versionados | **Git** (`docs/`) |
| Execução de código | VS Code no repo https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab |

**Nenhuma integração app GitHub↔Jira é alegada.** Sync = checklist manual (`map/SYNC-CHECKLIST.md`).

## Catálogo de prompts

Ver [`prompts/README.md`](prompts/README.md). Um arquivo por issue Jira (`prompts/epicos/` e `prompts/tasks/`, nome `<CHAVE>_<slug>.md`), com prompt canônico, prompt executivo (ritual de início de turno) e histórico de versões. Regras comuns em [`prompts/CORE-RULES.md`](prompts/CORE-RULES.md). Evidências de execução vão para [`relatorios/`](relatorios/). Runtime/agent/evals = pasta reservada `prompts/runtime/`.

## Não-determinismo LLM

Pin de prompt+deps+corpus melhora **reprodutibilidade de processo**, não garante texto idêntico. Sempre registrar model/config e evidências.

## Publicação

Documentação, mapa e catálogo publicados em `main`. Implementação de aplicação ainda não iniciada.
