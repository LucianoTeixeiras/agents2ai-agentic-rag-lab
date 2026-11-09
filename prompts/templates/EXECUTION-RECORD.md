# Registro de execução (template)

**Preencher após tentar a tarefa. Não inventar sucesso.**

| Campo | Valor |
| --- | --- |
| data_hora (America/Sao_Paulo) | |
| prompt_id | |
| prompt_version | |
| prompt_path | |
| jira_key | |
| executor (vscode/humano) | |
| git_commit (se houver) | |
| branch | |
| env (os/python) | |
| model (se LLM usado) | |
| model_config (temp/top_p/seed) | |
| dependency_lock (hash/arquivo) | |
| corpus_snapshot_id / retrieved_at | |
| data_mode (snapshot/live/n/a) | |
| outputs_paths | |
| evidências (CI link, logs redacted) | |
| falhas / bloqueios | |
| segredos commitados? | **não** |

## Notas
Reprodução de processo ≠ determinismo LLM.

## Checklist pós-execução
- [ ] Manifesto/prompt version anotados
- [ ] Jira status atualizado **pelo humano** se aplicável (não Done automático)
- [ ] Sem PII/cadastro completo ANP
