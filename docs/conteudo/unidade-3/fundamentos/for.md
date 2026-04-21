# Laço `for`

O laço for é a principal estrutura de repetição em Python quando sabemos antecipadamente quantas vezes um bloco de código deve ser executado. Ele percorre os elementos de uma sequência (como um intervalo numérico, uma string ou uma lista).

---

## Sintaxe básica:

```python

for variável in sequência:
    # bloco que será repetido
```

A cada repetição (iteração), a `variável` recebe o próximo valor da `sequência`.

## Repetindo um número fixo de vezes com `range()`:

Em problemas de programação competitiva, é muito comum repetir algo `N` vezes. A função `range()` gera sequências numéricas sob demanda.

### Formas do `range()`:

| Forma                         | Exemplo             | Sequência gerada        |
|-------------------------------|---------------------|-------------------------|
| `range(stop)`                 | `range(5)`          | 0, 1, 2, 3, 4           |
| `range(start, stop)`          | `range(2, 6)`       | 2, 3, 4, 5              |
| `range(start, stop, step)`    | `range(1, 10, 2)`   | 1, 3, 5, 7, 9           |

**Atenção**: `stop` não é incluído.

### Exemplo prático – soma dos primeiros N números:

```python

N = int(input())
soma = 0
for i in range(1, N+1):
    soma += i
print(soma)
```

## Percorrendo caracteres de uma string:

```python

texto = "OBI2024"
for caractere in texto:
    print(caractere)
```
Saída:
```text

O
B
I
2
0
2
4
```
## Percorrendo listas (útil para múltiplos valores na entrada):

```python

valores = [10, 20, 30, 40]
for v in valores:
    print(v * 2)   # 20, 40, 60, 80
```

## O identificador descartável `_`:

Quando você não precisa usar o valor da variável de controle, use _ para indicar que ela é descartável. Isso é muito comum ao repetir algo N vezes sem precisar do contador.

```python

N = int(input())
for _ in range(N):
    print("OBI")   # repete a mensagem N vezes
```

## Acumuladores: somar e contar:

Contar quantos números são pares:

```python

pares = 0
for i in range(10):
    num = int(input())
    if num % 2 == 0:
        pares += 1
print(pares)
```

## Soma total:

```python

total = 0
for _ in range(5):
    total += int(input())
print(total)
```