# Pacote documental — Lab ANP GLP + agentes (MVP → fase 2 cloud)

**Status:** docs ANP GLP + **mapa/manifesto** + **catálogo de prompts** (local) · **código não implementado** · **repo com docs (app não iniciada)** · AILAB-1..10 reutilizadas

## Estado atual

| Item | Estado |
| --- | --- |
| Jira AILAB | Issues **AILAB-1..10** reutilizadas e **atualizadas** (ANP GLP; não duplicadas) |
| Repo | https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab — docs publicados; implementação **não** iniciada |
| Fonte de dados MVP | API real ANP Revendedores GLP + corpus oficial (manual/metadata) |
| FakeProvider | Só testes/CI, **explicitamente rotulado** — não é o modelo da demo fase 2 |
| Azure OpenAI / Databricks | **Fase 2 prática planejada** (credenciais/custo autorizados) — **sem provisionar agora** |
| Implementação | **Não iniciada** |
| Mapa / prompts | Versionados em `docs/map/` + `prompts/` |
| Sync Jira↔Git | **Manual** (checklist); sem app integration |

## Índice

| Arquivo | Conteúdo |
| --- | --- |
| [00-PRD.md](00-PRD.md) | Produto, jornadas, acceptance |
| [01-ARCHITECTURE.md](01-ARCHITECTURE.md) | Arquitetura e contratos |
| [02-DESIGN-SYSTEM.md](02-DESIGN-SYSTEM.md) | Design system light |
| [adrs/](adrs/) | ADRs 001–006 (status **Proposto**) |
| [04-THREAT-MODEL.md](04-THREAT-MODEL.md) | Ameaças e controles (dados abertos ≠ republicar cadastro) |
| [05-TEST-EVAL-STRATEGY.md](05-TEST-EVAL-STRATEGY.md) | Snapshot datado + negativos sintéticos; live opt-in |
| [06-RUNBOOK-DEMO.md](06-RUNBOOK-DEMO.md) | Demo 5 min |
| [07-MATURITY-AND-GAPS.md](07-MATURITY-AND-GAPS.md) | Maturidade e gaps |
| [SOURCES.md](SOURCES.md) | Fontes oficiais verificadas |
| [backlog/](backlog/) | Epic/issues, mapping Jira, backlog.json |
| [map/](map/) | Mapa épicos/tasks + manifesto Jira (snapshot datado, sem auto-sync) |
| [../prompts/](../prompts/) | Catálogo Issue-as-a-Prompt + templates de execução |
| [08-REPRODUCIBILITY.md](08-REPRODUCIBILITY.md) | Fontes de verdade, não-determinismo, sync manual |

## Sequência

**Fase 1 (core):** LAB-01 → 02 → (03 ∥ 04) → 05 → 06 → 07 
**Fase 2 (prática cloud, autorizada):** LAB-08 Azure OpenAI · LAB-09 Databricks medallion + MLflow mínimo

## Papéis / labels

Arquiteto = Grok Bot · Executor = VS Code · Review = Luciano 
Labels: `spec` `exec:vscode` `review:luciano` `qa:risk-*` · fase2: `phase:2`
