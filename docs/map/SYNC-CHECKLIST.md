# Checklist manual de sincronia Jira ↔ Git

**Não é sync automático.** Use após mudanças em issues ou prompts.

1. Abrir [jira-manifest.json](jira-manifest.json) e anotar `snapshot_at`.
2. Para cada key AILAB-1..10 no Jira: conferir summary, status, priority, parent, links Blocks.
3. Confirmar que `prompt_path` existe e `prompt_version` bate com frontmatter do arquivo.
4. Se divergir: atualizar **manifesto + mapa** no Git (PR) **ou** a issue no Jira — não inventar sync.
5. Registrar execução em `prompts/execution-records/` (sem segredos).
6. Nunca marcar Done / Aceitar ADR em nome do Luciano sem revisão humana.
7. Não alegar integração app GitHub–Jira.

Último snapshot embutido: 2026-11-08 21:42 America/Sao_Paulo.
