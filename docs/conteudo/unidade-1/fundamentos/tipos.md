# `Tipos de Variáveis`

No Python, variáveis podem armazenar diferentes tipos de dados. Esses tipos definem o que pode ser feito com cada valor.

Diferente de muitas linguagens de programação, o próprio Python identifica automaticamente o tipo da variável, não sendo obrigatória a sua declaração.

---

## Principais Tipos

| Tipo | Nome | Exemplo |
|---|---|---|
| `int` | Inteiro | `67` |
| `float` | Decimal | `6.7` |
| `str` | Texto | `"Olá"` |
| `bool` | Booleano | `True` |

---

## A Função `type()`

Antes de introduzirmos o uso de tipos em uma variável, precisamos conhecer a função `type()`.

A função `type()` mostra o tipo de uma variável, usando esta como parâmetro.

```python
numero = 10
texto = "Python"

print(type(numero)) # Saída: <class 'int'>
print(type(texto)) # Saída: <class 'str'>
```

---

## Inteiros (`int`)

Os inteiros representam números sem casas decimais.

```python
idade = 18
ano = 2026

print(idade) # Saída: 18
print(type(idade)) # Saída: <class 'int'>
```

Note que o Python identificou automaticamente o tipo da variável `idade` e `ano` como inteiros. No entanto, também poderíamos identificá-lo manualmente:

```python
idade: int = 18
ano: int = 2026

print(idade) # Saída: 18
print(type(idade)) # Saída: <class 'int'>
```

A tipagem de dados no Python é importante para organização e legibilidade do código em projetos grandes; assim sendo, isto não nos interessa no momento, visto que não é necessário nos padrões de programação competitiva.

---

## Decimais (`float`)

Os números `float` possuem casas decimais.

```python
altura = 1.80
preco = 9.99

print(altura) # Saída: 1.80
print(type(altura)) # Saída: <class 'float'>
```

---

## Textos (`str`)

As strings armazenam textos.

```python
nome = "João"
cidade = 'Araquari'

print(nome) # Saída: João
print(type(nome)) # Saída: <class 'str'>
```

Strings podem utilizar aspas simples ou duplas.

---

## Booleanos (`bool`)

Booleanos representam valores de verdadeiro ou falso.

```python
aprovado = True
chovendo = False

print(aprovado) # Saída: True
print(type(aprovado)) # Saída: <class 'bool'>
```

---

## Conversão de Tipos

É possível converter um tipo para outro utilizando funções específicas.

| Função | Conversão |
|---|---|
| `int()` | Converte para inteiro |
| `float()` | Converte para decimal |
| `str()` | Converte para texto |
| `bool()` | Converte para booleano |

---

## Exemplos de Conversão

### Converter texto para inteiro

Utilizando funções de conversão no Python, é possível trazer um texto para um formato númerico.

```python
numero = "10"

numero = int(numero)

print(numero) # Saída: 10
print(type(numero)) # Saída: <class 'int'>
```

A partir disso, agora, é possível fazer operações matemáticas com o número declarado. Se não fizéssemos a conversão, as operações não se comportariam da maneira esperada:

```python
numero = "10"

print(numero) # Saída: 10
print(type(numero)) # Saída: <class 'str'>
print(numero * 2) # Saída: 1010
```

### Converter inteiro para texto

Também podemos converter números novamente para textos:

```python
idade = 17

idade = str(idade)

print(type(idade)) # <class 'str'>
```

Isso é ideal para quanto deseja-se concatenar textos em uma mesma saída.

### Converter inteiro para decimal

```python
numero = 5

numero = float(numero)

print(numero) # 5.0
```

---

## Entrada de Dados e Tipos

Por padrão, todo `input()` retorna uma string.

```python
idade = input()

print(type(idade)) # <class 'str'>
```

Para trabalhar com números, é necessário converter:

```python
idade = int(input())

print(type(idade)) # <class 'int'>
```

---

## Erros comuns

### Erro 1: Somar textos achando que são números

```python
numero1 = input()
numero2 = input()

print(numero1 + numero2)
```

**Entrada**
```python
2
3
```

**Saída**
```python
23
```

**Problema:** `input()` retorna texto.

### Correção

```python
numero1 = int(input())
numero2 = int(input())

print(numero1 + numero2)
```
**Entrada**
```python
2
3
```

**Saída**
```python
5
```

---

### Erro 2: Converter texto inválido para número

```python
numero = int("Python")
```

**Problema:** textos não numéricos não podem ser convertidos para `int`.

---

### Erro 3: Misturar tipos sem perceber

```python
idade = 17
texto = "anos"

print(idade + texto)
```

**Problema:** não é possível somar inteiro com string diretamente.

### Correção

Converta o tipo da idade para texto:

```python
print(str(idade) + texto)
```

Ou utilize f-strings:

```python
print(f"{idade} {texto}")
```

---

## Resumo

| Tipo | Utilidade |
|---|---|
| `int` | Números inteiros |
| `float` | Números decimais |
| `str` | Textos |
| `bool` | Verdadeiro ou falso |
| `type()` | Mostra o tipo |
| `int()` | Converte para inteiro |
| `float()` | Converte para decimal |
| `str()` | Converte para texto |
| `bool()` | Converte para booleano |
