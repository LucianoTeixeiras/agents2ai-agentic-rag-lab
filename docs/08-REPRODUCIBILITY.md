# Reprodutibilidade e sincronia de ambientes

**Atualizado:** 2026-11-08 21:42 America/Sao_Paulo

## Princípio

| O quê | Onde |
| --- | --- |
| Status / prioridade / workflow | **Jira** (fonte operacional) |
| Specs, ADRs, mapa, prompts versionados | **Git** (após publish; agora local docs-pack) |
| Execução de código | VS Code no repo https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab |

**Nenhuma integração app GitHub↔Jira é alegada.** Sync = checklist manual (`map/SYNC-CHECKLIST.md`).

## Catálogo de prompts

Ver `prompts/CATALOG.md`. Família atual = **vscode Issue-as-a-Prompt**. Runtime/agent/evals = pasta reservada.

## Não-determinismo LLM

Pin de prompt+deps+corpus melhora **reprodutibilidade de processo**, não garante texto idêntico. Sempre registrar model/config e evidências.

## Publicação

Esta preparação é **só documental local**. Publicação no GitHub = passo posterior (VS Code/humano). 
