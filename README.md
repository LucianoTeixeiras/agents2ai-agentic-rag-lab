# agents2ai-agentic-rag-lab

Laboratório público **Agents2AI** — assistente com **RAG** sobre documentação oficial ANP e **MCP read-only** sobre a API real de **Revendedores GLP**, com FastAPI, evals e (fase 2) Azure OpenAI + Databricks.

**Status honesto:** neste repositório há **apenas documentação, mapa Jira e catálogo de prompts**. A **implementação de aplicação ainda não foi iniciada**.

## Fases

| Fase | Escopo |
| --- | --- |
| **1** | Docs → bootstrap → RAG corpus ANP → MCP ANP → FastAPI → evals/guardrails → CI/demo (snapshot) |
| **2** | Azure OpenAI prático + Databricks Bronze/Silver/Gold (+ MLflow mínimo), **somente** com credenciais/custo autorizados — sem provisioning neste commit |

## Jira

Projeto **AILAB** (issues AILAB-1..10). Links do Jira no mapa exigem **login** no site Atlassian do mantenedor; não são conteúdo público indexável como wiki aberta.

Convenção para branch / commit / PR: prefixar com a chave Jira, ex. branch `feature/AILAB-3-bootstrap`, commit `AILAB-3 chore(bootstrap): …`.

Mapa e manifesto: [`docs/map/EPIC-TASK-MAP.md`](docs/map/EPIC-TASK-MAP.md) · [`docs/map/jira-manifest.json`](docs/map/jira-manifest.json)

Catálogo de prompts: [`docs/prompts/README.md`](docs/prompts/README.md) — um arquivo por issue (`<CHAVE>_<slug>.md`), com prompt canônico, prompt executivo para o VS Code e histórico de versões. Instruções para agentes: [`AGENTS.md`](AGENTS.md).

## Índice

| Caminho | Conteúdo |
| --- | --- |
| [`docs/00-PRD.md`](docs/00-PRD.md) | PRD |
| [`docs/01-ARCHITECTURE.md`](docs/01-ARCHITECTURE.md) | Arquitetura |
| [`docs/02-DESIGN-SYSTEM.md`](docs/02-DESIGN-SYSTEM.md) | Design system |
| [`docs/adrs/`](docs/adrs/) | ADRs (**Proposto**) |
| [`docs/04-THREAT-MODEL.md`](docs/04-THREAT-MODEL.md) | Threat model |
| [`docs/05-TEST-EVAL-STRATEGY.md`](docs/05-TEST-EVAL-STRATEGY.md) | Evals |
| [`docs/06-RUNBOOK-DEMO.md`](docs/06-RUNBOOK-DEMO.md) | Runbook demo |
| [`docs/07-MATURITY-AND-GAPS.md`](docs/07-MATURITY-AND-GAPS.md) | Maturidade |
| [`docs/08-REPRODUCIBILITY.md`](docs/08-REPRODUCIBILITY.md) | Reprodutibilidade / sync manual |
| [`docs/SOURCES.md`](docs/SOURCES.md) | Fontes oficiais |
| [`docs/backlog/`](docs/backlog/) | Epic/issues e mapping |
| [`docs/map/`](docs/map/) | Mapa + manifesto Jira |
| [`docs/prompts/`](docs/prompts/) | Catálogo canônico Issue-as-a-Prompt (épicos, tasks, core rules, templates) |
| [`docs/relatorios/`](docs/relatorios/) | Relatórios de fechamento por task |
| [`AGENTS.md`](AGENTS.md) | Instruções para agentes de código no VS Code |

## Avisos

- Dados abertos ANP ≠ republicar cadastro completo; snapshots mínimos; sem PII desnecessária.
- FakeProvider só em testes, rotulado.
- Reprodutibilidade de **processo** ≠ determinismo de saídas LLM.
- Nenhuma integração automática GitHub↔Jira é afirmada neste repo.

Atualizado: 2026-11-09 14:21 America/Sao_Paulo
