# Praticar com Dicionários

Dicionários são ideais para problemas de **contagem** e **mapeamento**.

---

## Quando usar dicionários?

| Situação | Exemplo |
|----------|---------|
| Contar frequência | Quantas vezes cada letra aparece |
| Mapear valores | Converter letras (criptografia) |
| Agrupar dados | Agrupar pessoas por idade |
| Busca rápida | Encontrar valor pela chave |

---

## Atividades OBI

### Nível Fácil

| # | Problema | Ano | Link |
|---|----------|-----|------|
| 1 | Dominó | OBI 2019 Fase 1 | [Resolver](https://olimpiada.ic.unicamp.br/pratique/pj/2019/f1/domino/) |
| 2 | Torneio de Tênis | OBI 2021 Fase 1 | [Resolver](https://olimpiada.ic.unicamp.br/pratique/pj/2021/f1/torneio/) |
| 3 | Camisetas da Olímpiada | OBI 2020 Fase 1 | [Resolver](https://olimpiada.ic.unicamp.br/pratique/pj/2020/f1/camisetas/) |

### Nível Difícil

| # | Problema | Ano | Link |
|---|----------|-----|------|
| 1 | Decifra | OBI 2014 Fase 2 | [Resolver](https://olimpiada.ic.unicamp.br/pratique/p1/2014/f2/decifra/) |
| 2 | Pares de Números | OBI 2019 Fase 3 | [Resolver](https://olimpiada.ic.unicamp.br/pratique/pj/2019/f3/pares/) |
| 3 | Média ou Mediana | OBI 2021 Fase 2 | [Resolver](https://olimpiada.ic.unicamp.br/pratique/pj/2021/f2/media/) |

---

## Dicas

- Use `dict.get(chave, padrão)` para inicialização segura
- Use `.items()` quando precisar de chave E valor
- Use `max(dicionario, key=dicionario.get)` para encontrar o mais frequente
- Lembre-se: dicionários são **mutáveis**, você pode modificar diretamente

---

## Padrão de Resolução

1. **Crie** o dicionário vazio: `dicio = {}`
2. **Itere** sobre os elementos
3. **Conte** usando `.get(chave, 0) + 1`
4. **Analise** os resultados

---

## Próximos Passos

- [Ver teoria sobre dicionários](../fundamentos/basico.md)
- [Ver exercício resolvido com dicionários](../resolvidos/problema.md)
- [Voltar para índice](./index.md)