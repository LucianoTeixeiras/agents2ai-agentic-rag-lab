# Arquitetura — ANP GLP lab (prosa)

**Status:** Proposto · Fase 1 offline-first (snapshot) + live opt-in · Fase 2 cloud prática planejada

## Visão

```
Cliente (curl/Swagger)
 → FastAPI (/health, /ask)
 → LangGraph
 ├─ intent: docs → retrieve (RAG lexical) → citations
 ├─ intent: query → MCP ANP tools (allowlist) → code metrics
 └─ compose (fase1: template/FakeProvider rotulado em testes;
 fase2: Azure OpenAI se autorizado)
```

## Ingestão ANP (cliente HTTP)

- Paginação (`numeropagina`; até 5.000/página conforme manual)
- Timeout, retry com backoff, cache local com `retrieved_at` e `source_url`
- Escopo explícito (ex.: `uf=RS`) — métricas só sobre o conjunto recuperado nesse escopo
- Não prometer filtros além dos comprovados: `uf`, `municipio`(+`uf`), `cnpj`, ou sem filtro (cuidado com volume)

## MCP (read-only)

Allowlist proposta:
1. `get_revenda_glp_by_cnpj(cnpj)`
2. `list_revendas_glp(uf, municipio?=None, page?=1)`
3. `count_revendas_glp(uf, municipio?=None)` — **contagem no código**, não no LLM

Proibido: write, scrapers genéricos, SQL livre, download de dump nacional no path default.

## RAG

Corpus: manual da API Revendedores + trechos/metadata oficiais ANP. 
Abstém se a pergunta pedir definição de campo ausente do corpus.

## Snapshots e privacidade

Dados abertos ≠ obrigação de republicar o cadastro inteiro. 
Snapshot de CI/demo: **mínimo** de registros e campos necessários (preferir agregados/`uf`/`municipio`/`classe`/`statusSIGAF`; evitar endereço/CEP/CNPJ completos quando não essenciais à prova). Revisar atribuição à ANP.

## Contratos HTTP (prosa)

**GET /health** — status, `data_mode: snapshot|live`, `provider_test_only: fake|n/a`

**POST /ask** — `question`, opcional `session_id` 
Saída: `answer`, `citations[]`, `tool_calls[]?`, `metrics?`, `data_mode`, `snapshot_id?`, `retrieved_at?`, `provider`, `trace_id`

## Fase 2 (planejada, não provisionada)

- **Azure OpenAI:** adapter real com env local; default fase1 permanece sem cobrança.
- **Databricks:** Bronze=JSON/páginas ANP; Silver=normalizado; Gold=agregados; MLflow mínimo para eval/tracing se viável; Vector Search **opcional** só para docs se disponível/útil.

## ADRs

Ver `adrs/` (todos **Proposto**).
