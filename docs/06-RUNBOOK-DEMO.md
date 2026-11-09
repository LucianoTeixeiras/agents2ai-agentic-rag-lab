# Runbook — demo 5 min (fase 1)

## Antes
Snapshot carregado; health `data_mode=snapshot`; pytest verde; **não** depender de FakeProvider na narrativa principal (se usado, dizer TEST ONLY).

## Roteiro
0:00 Problema ANP GLP + agentes 
0:40 Arquitetura RAG docs vs MCP+código 
1:30 Live: pergunta de manual → citations 
2:30 Live: consulta UF/município → tool + contagem código 
3:30 Produção leve: snapshot, guardrails, CI sem live 
4:20 Fase 2 planejada Azure/Databricks (sem alegar executado) 
5:00 Limites: paginação, minimização de dados, disponibilidade ANP

## Falhas
ANP fora → usar snapshot; nunca improvisar “já rodei Databricks”.
