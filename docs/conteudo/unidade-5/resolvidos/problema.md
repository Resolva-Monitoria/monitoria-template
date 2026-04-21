# Anagrama — OBI 2021

Neste problema, precisamos verificar se duas palavras são anagramas (têm as mesmas letras com a mesma frequência).

> **Link do problema:** [Anagrama - OBI 2021 Fase 2](https://olimpiada.ic.unicamp.br/pratique/pj/2021/f2/anagrama/)

---

## Enunciado

Dadas duas palavras, escreva um programa para determinar se elas são anagramas.

 Uma palavra A é um anagrama de outra palavra B se podemos transformar a palavra A na palavra B apenas trocando de lugar suas letras.

---

## Exemplos

**Entrada:**
```
4
a a b b
a b a b
```

**Saída:**
```
S
```

**Entrada:**
```
3
a b c
a a b
```

**Saída:**
```
N
```

---

## Análise do problema

Para verificar se duas palavras são anagramas, precisamos:
1. Contar quantas vezes cada letra aparece em cada palavra
2. Comparar as contagens

Dicionário é perfeito para isso!

---

## Resolução

```python
N = int(input())
palavra1 = input().split()
palavra2 = input().split()

# Contar letras da palavra 1
contagem1 = {}
for letra in palavra1:
    contagem1[letra] = contagem1.get(letra, 0) + 1

# Contar letras da palavra 2
contagem2 = {}
for letra in palavra2:
    contagem2[letra] = contagem2.get(letra, 0) + 1

# Comparar os dicionários
if contagem1 == contagem2:
    print("S")
else:
    print("N")
```

---

## Explicação do código

### Passo 1: Contagem

```python
contagem1 = {}
for letra in palavra1:
    contagem1[letra] = contagem1.get(letra, 0) + 1
```

- Se a letra não existe no dicionário, `.get()` retorna 0
- Adicionamos 1 à contagem
- Exemplo: `a a b b` → `{'a': 2, 'b': 2}`

### Passo 2: Comparação

```python
if contagem1 == contagem2:
```

- Se ambos dicionários tiverem as mesmas chaves com os mesmos valores, são anagramas

---

## Versão simplificada

Podemos usar um dicionário para contar e depois comparar:

```python
N = int(input())
palavra1 = input().split()
palavra2 = input().split()

contagem = {}

# Conta da primeira palavra (positivamente)
for letra in palavra1:
    contagem[letra] = contagem.get(letra, 0) + 1

# Subtrai da segunda palavra
for letra in palavra2:
    contagem[letra] = contagem.get(letra, 0) - 1

# Se todos os valores forem 0, são anagramas
sao_anagramas = all(v == 0 for v in contagem.values())

print("S" if sao_anagramas else "N")
```

---

## Próximos Passos

Pratique com mais exercícios na seção [Praticar](../treinar/index.md).

---

## Resumo

| Conceito | Aplicação |
|----------|-----------|
| `dict.get(k, 0)` | Contagem segura |
| `dict == dict` | Comparar dicionários |
| `.values()` | Iterar sobre valores |