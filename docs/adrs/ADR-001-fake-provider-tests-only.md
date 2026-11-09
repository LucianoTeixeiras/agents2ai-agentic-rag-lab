# ADR-001 — FakeProvider apenas em testes

- **Status:** Proposto
- **Data:** 2026-11-08

## Contexto
Precisamos de determinismo no CI sem custo. Confundir FakeProvider com “modelo da demo” é risco.

## Decisão
FakeProvider **somente** em testes/CI, rotulado (`provider=fake`, TEST ONLY). Compose fase 1 pode ser template/determinístico sobre tool+RAG. Modelo real = **fase 2 Azure OpenAI** quando autorizado.

## Consequências
(+) CI barato e honesto (−) prosa menos “LLM” na fase 1
