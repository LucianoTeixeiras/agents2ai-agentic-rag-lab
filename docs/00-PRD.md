# PRD — Assistente ANP GLP (lab público)

**Versão:** 0.2 · **Status:** Proposto · **Aprovado direcionamento:** API ANP GLP real (2026-11-08)

## 1. Problema

Precisamos de um laboratório **fim a fim** alinhado a vagas sênior de IA generativa (RAG, LangGraph, MCP, FastAPI, evals, observabilidade), com dados **públicos reais** de energia/GLP — sem inventar pedidos fictícios e sem republicar cadastro completo desnecessariamente.

## 2. Objetivo

> Dada uma pergunta sobre **regras/campos da API ANP de revendas GLP** (RAG) ou uma **consulta estruturada** (MCP read-only + código), o sistema responde com **citações oficiais** e/ou **resultados da API/snapshot**, com métricas calculadas em código e escopo temporal/geográfico explícito.

## 3. Não-objetivos (fase 1)

- UI rica; auth corporativa; provisionar Azure/Databricks/OpenAI agora
- Confiar cálculos ao LLM/vetores
- Prometer filtros não comprovados na API
- Publicar dump nacional completo de CNPJ/endereços no GitHub
- Alegar licença ODbL/específica da ANP sem texto confirmado no artefato (citar fonte ANP + Decreto 8.777 como marco de dados abertos)

## 4. Jornadas

### J1 — RAG documental (manual/metadata ANP)
Pergunta sobre paginação, parâmetros `uf`/`municipio`/`cnpj`, campos documentados. 
**Acceptance:** citations do corpus oficial; abstém se campo/regra não estiver no corpus.

### J2 — Consulta MCP read-only (API/snapshot)
Listar/obter revendas por filtros comprovados; contagens em Python sobre resultado do escopo. 
**Acceptance:** tool allowlist; resposta inclui `source`, `retrieved_at`/`snapshot_id`, escopo; sem write.

### J3 — Operador / CI
Health + ask offline via **snapshot datado**; live API **opt-in**. FakeProvider só em testes rotulados.

### J4 — Fase 2 cloud (prática, autorizada)
Azure OpenAI real + Databricks Bronze/Silver/Gold (+ MLflow mínimo se viável). Vector Search só se útil para docs e disponível — não requisito artificial.

## 5. Fontes de dados (fase 1)

| Uso | Fonte |
| --- | --- |
| Consultas | `GET https://revendedoresapi.anp.gov.br/v1/glp` (Swagger oficial) |
| RAG | Manual PDF oficial + páginas/metadata de dados abertos ANP |
| CI | Snapshot mínimo sanitizado (campos necessários) + negativos sintéticos |

Campos observados em teste (não inventar outros): `codigoSIMP`, `autorizacao`, `dataPublicacao`, `razaoSocial`, `cnpj`, `endereco`, `bairro`, `cep`, `uf`, `municipio`, `distribuidora`, `dataVinculacao`, `classe`, `statusSIGAF`, …

## 6. Métricas de sucesso (propostas)

| Métrica | Meta proposta |
| --- | --- |
| Golden RAG (manual) | ≥ 80% pass |
| Tool path (snapshot) | ≥ 90% pass |
| Secrets / dump completo no git | 0 |
| Live calls no CI default | 0 |

## 7. Riscos

Disponibilidade ANP; volume/paginação 5k; over-sharing de PII cadastral; confundir FakeProvider com demo “real”.
