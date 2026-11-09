# ADR-002 — MCP real read-only sobre ANP GLP

- **Status:** Proposto

## Decisão
MCP Python SDK (stdio) com allowlist de tools de consulta à API/snapshot ANP. Sem write. Host permitido: `revendedoresapi.anp.gov.br` (live) ou filesystem de snapshot.

## Consequências
(+) Evidência MCP + domínio energia (−) Dependência/limites da API ANP
