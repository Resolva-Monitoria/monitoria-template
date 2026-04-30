# Exercício Resolvido: Idade de Dona Mônica

## Problema: Idade de Dona Mônica (OBI 2019 - Fase 1)

🔗 [Link oficial](https://olimpiada.ic.unicamp.br/pratique/pj/2019/f1/idade/)

---

## Enunciado

Dona Mônica é mãe de três filhos que têm idades diferentes. Ela notou que, neste ano, a soma das idades dos seus três filhos é igual à idade dela. Neste problema, dada a idade de dona Mônica e as idades de dois dos filhos, seu programa deve computar e imprimir a idade do filho mais velho.

Por exemplo, se sabemos que dona Mônica tem 52 anos e as idades conhecidas de dois dos filhos são 14 e 18 anos, então a idade do outro filho, que não era conhecida, tem que ser 20 anos, pois a soma das três idades tem que ser 52. Portanto, a idade do filho mais velho é 20. Em mais um exemplo, se dona Mônica tem 47 anos e as idades de dois dos filhos são 21 e 9 anos, então o outro filho tem que ter 17 anos e, portanto, a idade do filho mais velho é 21.
---

## Exemplo

**Entrada**
A primeira linha da entrada contém um inteiro M representando a idade de dona Mônica. A segunda linha da entrada contém um inteiro A representando a idade de um dos filhos. A terceira linha da entrada contém um inteiro B representando a idade de outro filho.

```
52
14
18
```

**Saída**
Seu programa deve imprimir uma linha, contendo um número inteiro, representando a idade do filho mais velho de dona Mônica.
```
20
```

---

## Resolução

```python
M = int(input())
A = int(input())
B = int(input())

C = M - (A + B)

filhos = [A, B, C]
filhos.sort(reverse=True)

print(filhos[0])
```

---

## Explicação

### 1. Ler valores

```python
M = int(input())
A = int(input())
B = int(input())
```

- `M` = A idade de dona Mônica
- `A` = A idade de um filho
- `B` = A idade de outro filho

### 2. Calcular a idade do outro filho

```python
C = M - (A + B)
``` 
- `C`= A idade do outro filho
- `M - (A + B)` = O cálculo da idade do terceiro filho com base no enunciado

### 3. Imprimir a idade do filho mais velho

```python
filhos = [A, B, C]
filhos.sort(reverse=True)

print(filhos[0])
```
- `filhos` = Vetor contendo todos os filhos
- `filhos.sort(reverse=True)` = Ordena todos os filhos em ordem decrescente
- `print(filhos[0])` = Imprime o primeiro item do vetor `filhos`. Como o vetor está ordenado do maior para o menor, então, o primeiro item é o filho mais velho.

**Alternativa**: Ao invés de estruturarmos desta forma, poderíamos usar a função `max()`, que verifica o maior item de uma lista:
```python
filhos = [A, B, C]
print(max(filhos))
```

---

## Simulação

**Entrada:** M = 52, A = 14, B = 18

```python
C = 52 - (14 + 18) = 20

filhos = [14, 18, 20]
filhos.sort(reverse=True) → [20, 18, 14]
```
**Resultado:** 20

> [!NOTE]
Este problema pode ser resolvido sem vetores, utilizando apenas condicionais. No entanto, utilizamos uma lista para reforçar o conceito de vetores em um cenário simples.

---

## Conceitos utilizados

| Conceito              | Onde foi usado                                             |
| --------------------- | ---------------------------------------------------------- |
| Lista (vetor)         | Armazenar as idades dos três filhos (`filhos = [A, B, C]`) |
| `.sort()`             | Ordenar os valores da lista em ordem decrescente           |
| Indexação             | Acessar o maior valor com `filhos[0]`                      |
| `max()` (alternativa) | Obter diretamente o maior valor da lista                   |

---

## Próximos Passos

- [Praticar vetores](../treinar/index.md)
- [Voltar para índice](../resolvidos/index.md)