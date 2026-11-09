# Maturidade e gaps

| Área | Fase 1 | Fase 2 (autorizada) | Produção tipica |
| --- | --- | --- | --- |
| Dados | Snapshot + live opt-in ANP | Bronze/Silver/Gold Databricks | Governança UC |
| Modelo | Test FakeProvider; compose determinístico/template | Azure OpenAI | Gateway/quotas |
| Evals | Golden offline | + MLflow | LLM-judge + humano |
| Privacidade | Snapshot mínimo | Políticas workspace | DLP |

## Gaps honestos
Sem auth; ANP pode falhar; licença ANP citada via marco dados abertos sem texto ODbL próprio confirmado no PDF; Vector Search não é requisito artificial.
