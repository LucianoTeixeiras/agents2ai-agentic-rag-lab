# Core Rules — Engenharia Agêntica do Lab

Regras embarcadas em todos os prompts executivos de `docs/prompts/tasks/`. O agente do VS Code deve lê-las antes de qualquer edição.

## §1 Ritual de início de turno

1. **Idempotência:** `git log --oneline --grep="<CHAVE>"`. Se a entrega já existir e os testes passarem, abortar com `[IDEMPOTÊNCIA] <CHAVE> já executada`.
2. **Branch ativa:** `git branch --show-current`; trabalhar em `feature/<CHAVE>-<slug>` (ou `docs/<CHAVE>-<slug>`), criada a partir de `main` atualizada.
3. **Imersão:** ler o prompt canônico, os ADRs citados e os arquivos de contexto antes de editar.
4. **Runner:** somente o Python do `.venv` (`python -m pytest`, `python -m ruff check .`).
5. **Pré-requisitos:** se a issue bloqueadora não estiver concluída, parar e avisar.

## §2 Dados e segurança

- Fonte real: API ANP Revendedores GLP (`https://revendedoresapi.anp.gov.br/v1/glp`); documentação oficial em `docs/SOURCES.md`.
- CI e testes usam snapshot datado, mínimo e sanitizado; dados sintéticos só para casos negativos; chamadas live são opt-in.
- Não republicar o cadastro completo; não versionar dados pessoais desnecessários (ADR-006).
- Métricas e contagens sempre calculadas em código, nunca pelo LLM.
- FakeProvider somente em testes rotulados (ADR-001).
- MCP read-only com allowlist (ADR-002).
- Nenhum segredo no Git; usar `.env` local e `.env.example` só com nomes.

## §3 Git e rastreabilidade

- Chave Jira em branch, commit e PR: `<CHAVE> <tipo>(<escopo>): <mensagem>`.
- Um relatório de fechamento por task em `docs/relatorios/AAAA/AAAA-MM-DD-fechamento-<CHAVE>.md`.
- Mudou o prompt? Incrementar `prompt_version`, registrar no histórico e no manifesto.

## §4 Governança

- Status operacional vive no Jira; o agente não marca Done, não aceita ADRs e não faz merge sem o Luciano.
- Fase 2 (Azure OpenAI/Databricks) só com credenciais e custo autorizados; sem autorização, registrar bloqueio.
- Não inventar resultados: falhas e bloqueios vão para o relatório.
