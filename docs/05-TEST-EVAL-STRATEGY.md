# Testes e evals

**Números = metas propostas**, não resultados medidos.

## Pirâmide
1. Unit — parse ANP page JSON; count; redaction; guardrail 
2. Integration snapshot — `/ask` docs→citations; query→tool; metrics 
3. Golden evals — 8–12 casos 
4. CI — lint+pytest+eval smoke **sem** live ANP 
5. Live opt-in — job/flag manual

## Casos (exemplos)
| ID | Tipo | Esperado |
| --- | --- | --- |
| G01 | Paginação 5k | citation manual |
| G02 | Filtros uf/municipio/cnpj | citation |
| G03 | Campo não no corpus | abstém |
| G04 | count UF snapshot | métrica código = N snapshot |
| G05 | CNPJ no snapshot | tool get |
| G06 | Injection | bloqueio |
| G07 | Live desligado no CI | sem HTTP ANP |

## FakeProvider
Somente testes; campo `provider=fake` + banner. Demo fase 2 usa modelo real autorizado.
