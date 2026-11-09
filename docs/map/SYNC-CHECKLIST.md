# Checklist manual de sincronia Jira ↔ Git

**Não é sync automático.** Use após mudanças em issues ou prompts.

1. Abrir [jira-manifest.json](jira-manifest.json) e anotar `snapshot_at`.
2. Para cada key AILAB-1..10 no Jira: conferir summary, status, priority, parent, links Blocks.
3. Confirmar que `prompt_path` existe (`docs/prompts/<epicos|tasks>/<CHAVE>_<slug>.md`), que `prompt_version` bate com o frontmatter e que a seção Rastreabilidade da issue aponta para o mesmo arquivo.
4. Se divergir: atualizar **manifesto + mapa** no Git (PR) **ou** a issue no Jira — não inventar sync.
5. Registrar execução em `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-<CHAVE>.md` (template `docs/prompts/templates/RELATORIO-FECHAMENTO.md`, sem segredos).
6. Nunca marcar Done / Aceitar ADR em nome do Luciano sem revisão humana.
7. Não alegar integração app GitHub–Jira.

Último snapshot embutido: 2026-11-09 14:21 America/Sao_Paulo.
