# Laço `for`

O laço `for` é a principal estrutura de repetição em Python quando sabemos antecipadamente quantas vezes um bloco de código deve ser executado. Ele percorre os elementos de uma sequência (como um intervalo numérico, uma string ou uma lista).

---

## Quando usar `for`?

| Situação | Exemplo |
|----------|---------|
| Repetir N vezes | Ler 10 números |
| Percorrer intervalo | Testar números de 1 a 100 |
| Processar string | Analisar cada caractere |
| Iterar lista | Somar elementos |

---

## Sintaxe básica

```python
for variável in sequência:
    # bloco que será repetido
```

A cada repetição (iteração), a `variável` recebe o próximo valor da `sequência`.

---

## Repetindo com `range()`

A função `range()` gera sequências numéricas sob demanda. É muito comum em problemas de programação competitiva.

### Formas do `range()`

| Forma | Exemplo | Sequência gerada |
|-------|---------|------------------|
| `range(stop)` | `range(5)` | 0, 1, 2, 3, 4 |
| `range(start, stop)` | `range(2, 6)` | 2, 3, 4, 5 |
| `range(start, stop, step)` | `range(1, 10, 2)` | 1, 3, 5, 7, 9 |

> **Atenção**: O valor `stop` não é incluído na sequência.

### Exemplo: Soma dos primeiros N números

```python
N = int(input())
soma = 0

for i in range(1, N + 1):
    soma += i

print(soma)
```

---

## Percorrendo strings

```python
texto = "OBI"

for caractere in texto:
    print(caractere)
```

**Saída:**
```
O
B
I
```

---

## Percorrendo listas

```python
valores = [10, 20, 30, 40]

for v in valores:
    print(v * 2)  # 20, 40, 60, 80
```

---

## Variável descartável `_`

Quando você não precisa usar o valor do contador, use `_` para indicar que é descartável:

```python
N = int(input())

for _ in range(N):
    print("Olá")  # repete N vezes
```

---

## Acumuladores

### Contando elementos

```python
pares = 0

for i in range(10):
    num = int(input())
    if num % 2 == 0:
        pares += 1

print(pares)
```

### Somando valores

```python
total = 0

for _ in range(5):
    total += int(input())

print(total)
```

---

## Próximos Passos

Agora que você aprendeu o básico de `for`, pratique com:

- [Exercício resolvido com for](../resolvidos/for.md)
- [Praticar com for](../treinar/for.md)
- [Laço while](./while.md) — para quando não sabemos o número de repetições

---

## Resumo

| Conceito | Descrição |
|----------|------------|
| `for` | Repetição com número conhecido de vezes |
| `range(n)` | Gera 0 até n-1 |
| `range(i, j)` | Gera i até j-1 |
| `range(i, j, k)` | Gera i até j-1, pulando de k em k |
| `_` | Variável descartável |
