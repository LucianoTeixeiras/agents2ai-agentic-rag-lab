---
id: AILAB-PROMPT-008-AZURE-OPENAI
version: 1.0.0
jira_key: AILAB-9
temp: LAB-08
phase: "2"
kind: vscode-issue-as-prompt
executor: vscode
locale: pt-BR
status: draft
created: "2026-11-08 21:42 America/Sao_Paulo"
supersedes: null
---

# AILAB-PROMPT-008-AZURE-OPENAI — [LAB-08][Fase 2] Azure OpenAI prático (credenciais/custo autorizados)

**Tipo:** Issue-as-a-Prompt (**vscode**). Não confundir com prompts futuros de runtime/agent/evals em `prompts/runtime/`. 
**Jira:** [AILAB-9](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-9) · Parent: AILAB-1 · Fase: 2

## Objetivo
Integrar Azure OpenAI **de fato** só com credenciais/custo **autorizados**. Sem authorization = bloqueio explícito, não stub cosmétique.

## Contexto
- Repo: https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab (docs/prompts publicados neste repositório; implementação de app ainda não iniciada).
- Dados: API ANP GLP + corpus oficial; FakeProvider só testes rotulados.
- ADRs: **Proposto**. Issues: **A fazer**.
- Mapa: `docs/map/EPIC-TASK-MAP.md` · Manifesto: `docs/map/jira-manifest.json`.

## Inputs
- Autorização Luciano; env local; ADR-005.

## Precondições
- AILAB-8; budget/credenciais ok.

## Output esperado
- Adapter real **ou** registro de bloqueio; rollback fase1.

> Não inventar implementação nem resultados: este arquivo é o **contrato do trabalho**. Evidências → `templates/EXECUTION-RECORD.md`.

## Testes / verificação
- Mock + smoke autorizado; zero secrets no git.

## Definition of Done
- [ ] Execução autorizada OU bloqueio documentado

## Proibições
- Provisionar sem ok; keys no git; CI pago default.
- Sem dados pessoais/clientes/legacy indevido; snapshot ANP mínimo.
- Sem provisioning Azure/Databricks / gastos não autorizados.
- Sem Done automático; sem issues duplicadas; sem comentários externos como mensagens.

## Escalonamento
- Sem acesso → parar e registrar. créditos.

## Rastreabilidade
| Campo | Valor |
| --- | --- |
| prompt_id | `AILAB-PROMPT-008-AZURE-OPENAI` |
| version | `1.0.0` |
| path | `prompts/vscode/AILAB-PROMPT-008-AZURE-OPENAI.v1.md` |
| jira | AILAB-9 |
| blocked_by | AILAB-8 |
| blocks | — |
