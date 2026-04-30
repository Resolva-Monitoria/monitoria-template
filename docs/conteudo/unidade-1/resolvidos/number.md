# Exercício Resolvido: Divisão do Tesouro

## Problema: Divisão do Tesouro (OBI 2020 - Fase 1)

🔗 [Link oficial](https://olimpiada.ic.unicamp.br/pratique/pj/2020/f1/tesouro/)

---

## Enunciado

O Capitão Olho Roxo e seus marinheiros encontraram uma arca com uma grande quantidade de moedas de ouro idênticas. Para a divisão das moedas, todos concordaram com a seguinte sugestão do Capitão:

cada marinheiro exceto o Capitão deveria receber exatamente o mesmo número de moedas; e
o Capitão deveria receber o dobro de moedas que um marinheiro recebe.
Pode ser que o fato de o Capitão ser o único com uma pistola a bordo tenha contribuído para a concordância de todos, mas também contribuiu o fato de que na forma proposta a divisão era perfeita, não sobrando ou faltando moedas.

Dados o número de moedas na arca e o número de marinheiros, escreva um programa para determinar quantas moedas o Capitão Olho Roxo recebeu.

---

## Exemplo

**Entrada**
```

221
11
```

**Saída**
```
34
```

---

## Resolução

```python
A = int(input())
N = int(input())

I = 2 * (A // (N+2))

print(I)
```

---

## Explicação

### 1. Ler valores

```python
A = int(input())
N = int(input())
```

- `A` = Número de moedas na arca
- `N` = Número de marinheiros

### 2. Fazer a operação matemática

```python
I = 2 * (A // (N+2))
```

- `I` = Número inteiro de moedas que o Capitão deve receber
- O `A // (N+2)` dá o número que cada marinheiro vai receber, pois é o número de moedas para cada marinheiro mais dois, equivalente ao que o capitão vai receber
- `*` = sinal de multiplicação no Python
- `//` = sinal de divisão que retorna um número inteiro, não decimal

### 3. Mostrar resultado

```python
print(I)
```

---

## Simulação

**Entrada:** A=221, N=11

I = 2 * (221 // (11 + 2))
I = 2 * (221 // 13)
I = 2 * 17
I = 34

**Resultado:** 34

---

## Conceitos utilizados

| Conceito | Onde foi usado |
|----------|---------------|
| `int()` | Transforma uma entrada em um inteiro |
| `input()` | Recebe uma entrada do usuário |
| `print()` | Devolve um dado ao usuário |

---

## Próximos Passos

- [Praticar entradas e saídas](../treinar/index.md)
- [Voltar para índice](../resolvidos/index.md)