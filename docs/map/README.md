# Mapa épicos/tasks — sincronia entre ambientes

**Snapshot datado:** 2026-11-08 21:42 America/Sao_Paulo 
**NÃO é sync automático.** Este mapa é manifesto estático versionado no Git (quando publicado). Status/prioridade operacionais vivem no **Jira**; docs/prompts versionados vivem no **Git**. Nenhuma integração app GitHub↔Jira é alegada.

## Fontes de verdade

| Domínio | Fonte |
| --- | --- |
| Status, prioridade, assignee | Jira AILAB (operacional) |
| Spec, ADRs, prompts, mapa | Git `docs/` (após publicação) — agora só local no docs-pack |
| Código / CI | Repo https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab (docs publicados; implementação de app ainda não iniciada) |

## Arquivos

| Arquivo | Uso |
| --- | --- |
| [EPIC-TASK-MAP.md](EPIC-TASK-MAP.md) | Mapa legível humano |
| [jira-manifest.json](jira-manifest.json) | Manifesto estruturado AILAB-1..10 |
| [SYNC-CHECKLIST.md](SYNC-CHECKLIST.md) | Checklist manual de reconciliação Jira↔Git |

## Sequência (fase 1 → fase 2)

```
AILAB-2 → AILAB-3 → (AILAB-4 ∥ AILAB-5) → AILAB-6 → AILAB-7 → AILAB-8 → (AILAB-9 ∥ AILAB-10)
```

Blocks já existentes no Jira (9 links): 2→3; 3→4; 3→5; 4→6; 5→6; 6→7; 7→8; 8→9; 8→10.

> URLs do Jira no manifesto exigem **login** no site Atlassian do mantenedor.
