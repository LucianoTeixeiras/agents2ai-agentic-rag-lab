---
id: AILAB-PROMPT-002-BOOTSTRAP
version: 1.0.0
jira_key: AILAB-3
temp: LAB-02
phase: "1"
kind: vscode-issue-as-prompt
executor: vscode
locale: pt-BR
status: draft
created: "2026-11-08 21:42 America/Sao_Paulo"
supersedes: null
---

# AILAB-PROMPT-002-BOOTSTRAP — [LAB-02] Bootstrap VS Code no repo existente (docs ANP)

**Tipo:** Issue-as-a-Prompt (**vscode**). Não confundir com prompts futuros de runtime/agent/evals em `prompts/runtime/`. 
**Jira:** [AILAB-3](https://lucianoteixeiras-1773934569563.atlassian.net/browse/AILAB-3) · Parent: AILAB-1 · Fase: 1

## Objetivo
Bootstrap no **repo existente**: estrutura mínima, copiar docs-pack→`docs/`, README ANP, gitignore, venv; **sem novo repo**.

## Contexto
- Repo: https://github.com/LucianoTeixeiras/agents2ai-agentic-rag-lab (docs/prompts publicados neste repositório; implementação de app ainda não iniciada).
- Dados: API ANP GLP + corpus oficial; FakeProvider só testes rotulados.
- ADRs: **Proposto**. Issues: **A fazer**.
- Mapa: `docs/map/EPIC-TASK-MAP.md` · Manifesto: `docs/map/jira-manifest.json`.

## Inputs
- Clone do repo com docs (app não iniciada); docs-pack/tar; este prompt v1.

## Precondições
- AILAB-2 aceita (ou Luciano autoriza bootstrap paralelo consciente).

## Output esperado
- Tree com `docs/` (incl. map/prompts); README; zero secrets; PR/commit pelo Luciano/VS Code (esta preparação **não** publica).

> Não inventar implementação nem resultados: este arquivo é o **contrato do trabalho**. Evidências → `templates/EXECUTION-RECORD.md`.

## Testes / verificação
- Clone fresco; README legível; scan secrets; paths do manifesto existem.

## Definition of Done
- [ ] Docs no working tree prontos a publicar
- [ ] Zero secrets
- [ ] Aceite README

## Proibições
- Novo repo; dump ANP; alegar MCP/Azure feitos; 
- Sem dados pessoais/clientes/legacy indevido; snapshot ANP mínimo.
- Sem provisioning Azure/Databricks / gastos não autorizados.
- Sem Done automático; sem issues duplicadas; sem comentários externos como mensagens.

## Escalonamento
- Auth GitHub com Luciano.

## Rastreabilidade
| Campo | Valor |
| --- | --- |
| prompt_id | `AILAB-PROMPT-002-BOOTSTRAP` |
| version | `1.0.0` |
| path | `prompts/vscode/AILAB-PROMPT-002-BOOTSTRAP.v1.md` |
| jira | AILAB-3 |
| blocked_by | AILAB-2 |
| blocks | AILAB-4, AILAB-5 |
