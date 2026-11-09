# Threat model (lab ANP GLP)

## Ativos
Integridade do snapshot; não republicar cadastro excessivo; ausência de secrets; honestidade provider/modo.

## Ameaças
| ID | Ameaça | Controlo | Residual |
| --- | --- | --- | --- |
| T1 | Commit de keys Azure | gitignore; CI sem secrets | Erro humano |
| T2 | Dump nacional no git | snapshot mínimo; allowlist campos | Pressão “dataset completo” |
| T3 | Prompt injection | guardrails; MCP allowlist | Injection sofisticada |
| T4 | Tool write / SSRF | MCP read-only; só host ANP | Bug |
| T5 | Live API no CI flaky | live opt-in; snapshot default | Drift dados |
| T6 | Confundir FakeProvider | labels TEST ONLY | Leitura superficial |

## Trust boundaries
Cliente→API; Grafo→MCP; MCP→ANP HTTPS; (fase2) App→Azure/Databricks.

## Assunções
Repo público; sem auth de usuário na fase 1; dados ANP são públicos mas **minimizados** no artefato.
