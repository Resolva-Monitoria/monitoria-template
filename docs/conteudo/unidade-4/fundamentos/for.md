# Laço `for`

O laço `for` é a principal estrutura de repetição em Python quando sabemos antecipadamente **quantas vezes** um bloco de código deve ser executado. Ele percorre os elementos de uma sequência (como um intervalo numérico, uma string ou uma lista).

---

## Conceito Fundamental

Imagine que você tem uma lista de compras:
```
1. Arroz
2. Feijão
3. Macarrão
```

Com o laço `for`, você pode olhar **cada item da lista**, um por um, em ordem. É como se você dissesse:

> "Para cada item da minha lista, faça algo"

---

## Quando usar `for`?

| Situação | Exemplo |
|----------|---------|
| Repetir N vezes | Ler 10 números |
| Percorrer intervalo | Testar números de 1 a 100 |
| Processar string | Analisar cada caractere |
| Iterar lista | Somar elementos |
| Quando sabemos o total | Processar todos os dados de uma vez |

---

## Sintaxe básica

```python
for variável in sequência:
    # bloco que será repetido
```

Onde:
- **`variável`** é o nome que você escolhe para representar cada elemento
- **`sequência`** é o conjunto de valores que será percorrido
- **Bloco indentado** é o código que será executado a cada iteração

### Exemplo simples

```python
for fruta in ["maçã", "banana", "uva"]:
    print(fruta)
```

**Passo a passo:**

```
Iteração 1: fruta = "maçã"  → print("maçã")
Iteração 2: fruta = "banana" → print("banana")
Iteração 3: fruta = "uva"   → print("uva")
```

**Saída:**
```
maçã
banana
uva
```

---

## A função `range()`

A função `range()` gera sequências numéricas sob demanda. É muito comum em problemas de programação competitiva.

### Por que "sob demanda"?

O `range()` não cria uma lista completa na memória. Ele gera os números **um por um** conforme necessário. Isso é eficiente para números grandes.

### Formas do `range()`

| Forma | Exemplo | Sequência gerada | Explicação |
|-------|---------|-----------------|----------|
| `range(stop)` | `range(5)` | 0, 1, 2, 3, 4 | De 0 até 4 (não inclui 5) |
| `range(start, stop)` | `range(2, 6)` | 2, 3, 4, 5 | De 2 até 5 (não inclui 6) |
| `range(start, stop, step)` | `range(1, 10, 2)` | 1, 3, 5, 7, 9 | De 1 até 8, pulando de 2 em 2 |

> **Atenção importante**: O valor `stop` **nunca** é incluído na sequência!

### Visualizando o `range()`

```
range(5)        → [0, 1, 2, 3, 4]     (5 números)
range(2, 6)    → [2, 3, 4, 5]       (4 números)
range(0, 10, 2)→ [0, 2, 4, 6, 8]   (5 números)
```

### Exemplos práticos

#### De 1 até N (incluindo N)

```python
N = 5
for i in range(1, N + 1):
    print(i)
```

**Saída:**
```
1
2
3
4
5
```

> Perceba: usamos `N + 1` porque o `stop` não é incluído!

#### Números pares de 2 até 100

```python
for i in range(2, 101, 2):
    print(i)
```

#### Contagem regressiva

```python
for i in range(10, 0, -1):
    print(i)
```

**Saída:**
```
10
9
8
7
6
5
4
3
2
1
```

---

## Exemplos detalhados

### Exemplo 1: Soma dos primeiros N números

**Problema:** Some todos os números de 1 até N.

```python
N = int(input())
soma = 0

for i in range(1, N + 1):
    soma += i

print(soma)
```

**Simulação (N = 4):**

| Iteração | i | soma (antes) | soma (depois) |
|---------|---|------------|---------------|
| 1 | 1 | 0 | 1 |
| 2 | 2 | 1 | 3 |
| 3 | 3 | 3 | 6 |
| 4 | 4 | 6 | 10 |

**Resultado:** 10

---

### Exemplo 2: Tabuada

```python
numero = int(input())
for i in range(1, 11):
    print(f"{numero} x {i} = {numero * i}")
```

**Simulação (numero = 3):**

```
3 x 1 = 3
3 x 2 = 6
3 x 3 = 9
3 x 4 = 12
3 x 5 = 15
3 x 6 = 18
3 x 7 = 21
3 x 8 = 24
3 x 9 = 27
3 x 10 = 30
```

---

### Exemplo 3: Contar números positivos

```python
positivos = 0

for _ in range(5):
    numero = int(input())
    if numero > 0:
        positivos += 1

print(positivos)
```

> Usamos `_` porque não precisamos do valor do contador.

---

### Exemplo 4: Encontrar maior número

```python
maior = int(input())  # Primeiro número define o inicial

for _ in range(4):  # Ainda faltam 4 números
    numero = int(input())
    if numero > maior:
        maior = numero

print(maior)
```

---

## Percorrendo strings

Strings são sequências de caracteres. Podemos iterar sobre elas!

### Exemplo: Contar vogais

```python
texto = input()
vogais = "aeiouAEIOU"
contagem = 0

for letra in texto:
    if letra in vogais:
        contagem += 1

print(contagem)
```

### Exemplo: Inverter string

```python
texto = input()
invertido = ""

for letra in texto:
    invertido = letra + invertido

print(invertido)
```

**Simulação (texto = "casa"):**

| Iteração | letra | invertido (antes) | invertido (depois) |
|---------|-------|-----------------|---------------------|
| 1 | 'c' | "" | "c" |
| 2 | 'a' | "c" | "ac" |
| 3 | 's' | "ac" | "sac" |
| 4 | 'a' | "sac" | "asac" |

---

## Percorrendo listas

Listas são sequências ordenadas de valores.

### Exemplo: Somar elementos

```python
valores = [10, 20, 30, 40]
soma = 0

for v in valores:
    soma += v

print(soma)  # 100
```

### Exemplo: Maior e menor

```python
numeros = [5, 2, 8, 1, 9]

maior = numeros[0]
menor = numeros[0]

for n in numeros:
    if n > maior:
        maior = n
    if n < menor:
        menor = n

print(f"Maior: {maior}, Menor: {menor}")
```

---

## A variável descartável `_`

Quando você não precisa usar o valor do contador, use `_` para indicar que é descartável:

```python
# Repete 10 vezes, não precisa do contador
for _ in range(10):
    print("Olá")
```

### Por que usar `_`?

1. **Legibilidade**: `_` indica que o valor não será usado
2. **Performance**: Python otimiza para variáveis descartáveis
3. **Convenção**: É um padrão widely aceito

---

## Acumuladores e Contadores

### Contador

```python
contador = 0

for _ in range(10):
    if condicao:
        contador += 1  # Incrementa
```

### Acumulador (soma)

```python
soma = 0

for _ in range(5):
    soma += int(input())
```

### Multiplicador

```python
produto = 1

for _ in range(4):
    produto *= int(input())
```

---

## Acumulação dupla

### Contar pares e ímpares

```python
pares = 0
impares = 0

for _ in range(10):
    numero = int(input())
    if numero % 2 == 0:
        pares += 1
    else:
        impares += 1
```

### Soma e conta

```python
soma = 0
quantidade = 0

for _ in range(5):
    numero = int(input())
    soma += numero
    quantidade += 1

media = soma / quantidade
```

---

## Padrões comuns

### Padrão 1: Inicializar → Processar → Usar

```python
# Inicializar
acumulador = 0

# Processar (N vezes)
for _ in range(N):
    valor = int(input())
    acumulador += valor

# Usar
print(acumulador)
```

### Padrão 2: Percorrer → Verificar → Contar

```python
contador = 0

for elemento in sequencia:
    if condicao(elemento):
        contador += 1

print(contador)
```

### Padrão 3: Buscar máximo/mínimo

```python
maior = sequencia[0]  # Primeiro elemento

for elemento in sequencia:
    if elemento > maior:
        maior = elemento
```

---

## Erros comuns

### Erro 1: range() errado

```python
# ERRADO: não inclui o 10
for i in range(10):
    print(i)  # 0 a 9, não 1 a 10!

# CERTO: usar N + 1
for i in range(1, 11):
    print(i)  # 1 a 10
```

### Erro 2: Esquecer de inicializar

```python
# ERRADO: acumulador não existe
for i in range(5):
    acumulador += i  # NameError!

# CERTO: inicializar antes
acumulador = 0
for i in range(5):
    acumulador += i
```

### Erro 3: modificar lista durante iteração

```python
# ERRADO: pode causar comportamento inesperado
numeros = [1, 2, 3, 4, 5]
for n in numeros:
    numeros.remove(n)

# CERTO: usar cópia
for n in numeros.copy():
    numeros.remove(n)
```

---

## Dica: enumerate()

Quando você precisa do índice E do valor:

```python
frutas = ["maçã", "banana", "uva"]

for indice, fruta in enumerate(frutas):
    print(f"{indice}: {fruta}")
```

**Saída:**
```
0: maçã
1: banana
2: uva
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
| `enumerate()` | Iterar com índice |
| break | Encerra o loop |
| continue | Pula para próxima iteração |