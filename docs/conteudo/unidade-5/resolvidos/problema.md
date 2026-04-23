# Exercício Resolvido: Anagrama

## Problema: Anagrama (OBI 2021 - Fase 2)

🔗 [Link oficial](https://olimpiada.ic.unicamp.br/pratique/pj/2021/f2/anagrama/)

---

## Enunciado

Dadas duas palavras, escreva um programa para determinar se elas são anagramas.

Uma palavra A é um anagrama de outra palavra B se podemos transformar a palavra A na palavra B apenas trocando de lugar suas letras.

---

## Exemplo

**Entrada**
```
4
a a b b
a b a b
```

**Saída**
```
S
```

**Explicação:** Ambas as palavras têm duas letras 'a' e duas letras 'b'.

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

## Explicação

### 1. Ler entrada

```python
N = int(input())
palavra1 = input().split()
palavra2 = input().split()
```

- `N` = número de pares de palavras
- `palavra1` = primeira palavra (convertida em lista de caracteres)
- `palavra2` = segunda palavra

### 2. Contar frequência com dicionário

```python
contagem1 = {}
for letra in palavra1:
    contagem1[letra] = contagem1.get(letra, 0) + 1
```

- Cria um dicionário vazio
- Para cada letra, incrementa a contagem
- `.get(letra, 0)` retorna 0 se a chave não existir

**Exemplo:** `['a', 'a', 'b', 'b']` → `{'a': 2, 'b': 2}`

### 3. Comparar dicionários

```python
if contagem1 == contagem2:
    print("S")
else:
    print("N")
```

- Se os dicionários forem iguais, são anagramas
- A comparação verifica se todas as chaves e valores são iguais

---

## Simulação

**Entrada:** N=4, palavra1=['a','a','b','b'], palavra2=['a','b','a','b']

| Passo | Operação | contagem1 | contagem2 |
|-------|----------|-----------|-----------|
| 1 | Início | {} | {} |
| 2 | Letra 'a' | {'a': 1} | {} |
| 3 | Letra 'a' | {'a': 2} | {} |
| 4 | Letra 'b' | {'a': 2, 'b': 1} | {} |
| 5 | Letra 'b' | {'a': 2, 'b': 2} | {} |
| 6 | Letra 'a' (pal2) | {'a': 2, 'b': 2} | {'a': 1} |
| 7 | Letra 'b' (pal2) | {'a': 2, 'b': 2} | {'a': 1, 'b': 1} |
| 8 | Letra 'a' (pal2) | {'a': 2, 'b': 2} | {'a': 2, 'b': 1} |
| 9 | Letra 'b' (pal2) | {'a': 2, 'b': 2} | {'a': 2, 'b': 2} |

**Resultado:** São iguais → Imprime "S"

---

## Conceitos utilizados

| Conceito | Onde foi usado |
|----------|---------------|
| `dict` | Armazenar contagem de letras |
| `.get(chave, 0)` | Contagem segura |
| `for` | Iterar sobre letras |
| `dict == dict` | Comparar dicionários |
| `.split()` | Separar caracteres |

---

## Versão Alternativa

Podemos usar um único dicionário com soma e subtração:

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

## Erros Comuns

1. **Esquecer `.split()`**: Sem isso, a entrada é tratada como string única
2. **Não usar `.get()`**: Acessar chave inexistante causa erro
3. **Comparar com `in`**: Verifica apenas chaves, não valores

---

## Próximos Passos

- [Praticar com dicionários](../treinar/index.md)
- [Ver fundamentos de dicionários](../fundamentos/basico.md)
- [Voltar para índice](../resolvidos/index.md)