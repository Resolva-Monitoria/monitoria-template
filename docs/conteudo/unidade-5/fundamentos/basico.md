# Conceitos Básicos de Dicionários

Um dicionário em Python é uma estrutura de dados mutável que armazena pares de **chave: valor**. Cada chave deve ser única e pode ser de tipos imutáveis (como strings, inteiros, tuplas).

---

## Conceito Fundamental

Imagine um dicionário de verdade (como Aurélio):
- Você procura uma **palavra** (chave)
- E encontra sua **definição** (valor)

Em Python, é exatamente isso! Um dicionário é como uma tabela de pesquisa rápida:

```
┌─────────────┬──────────────────────┐
│   Chave     │       Valor          │
├─────────────┼──────────────────────┤
│   "nome"    │     "Maria"         │
│   "idade"   │        25            │
│   "cidade"  │    "São Paulo"     │
└─────────────┴──────────────────────┘
```

### Diferença para listas

| Lista | Dicionário |
|-------|-----------|
| Acesso por **índice** numérico | Acesso por **chave** arbitrária |
| Ordem importa | Ordem (Python 3.7+) é mantida |
| `[0, 1, 2]` | `{"a": 0, "b": 1}` |

---

## Quando usar dicionários?

| Situação | Exemplo |
|----------|---------|
| Contar frequência | Contar quantas vezes cada letra aparece |
| Mapear dados | Associar nomes a notas |
| Busca rápida | Encontrar informação pela chave |
| Agrupar dados | Agrupar pessoas por idade |
| Tradução | Converter códigos em nomes |

---

## Criando dicionários

### Forma literal (mais comum)

```python
# Dicionário vazio
dicio = {}

# Com valores iniciais
pessoa = {"nome": "Maria", "idade": 20, "cidade": "SP"}

# Misturando tipos
dados = {"nome": "Ana", "notas": [8, 9, 7], "ativo": True}
```

### Usando dict()

```python
# Usando keyword arguments
notas = dict(matematica=8, historia=7, portugais=9)
# Resultado: {'matematica': 8, 'historia': 7, 'portugais': 9}

# Convertendo de lista de tuplas
pares = [("a", 1), ("b", 2)]
dicio = dict(pares)
# Resultado: {'a': 1, 'b': 2}
```

### Criando com comprehension

```python
# Quadrados de 1 a 5
quadrados = {x: x**2 for x in range(1, 6)}
# Resultado: {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

---

## Acessando valores

### Acesso direto (pode gerar erro)

```python
pessoa = {"nome": "Ana", "idade": 22}

print(pessoa["nome"])   # Ana
print(pessoa["idade"])  # 22

# ERRO se chave não existir!
print(pessoa["cpf"])    # KeyError: 'cpf'
```

### Acesso seguro com .get()

```python
pessoa = {"nome": "Ana", "idade": 22}

print(pessoa.get("nome"))           # Ana
print(pessoa.get("cpf"))             # None (não dá erro!)
print(pessoa.get("cpf", "N/A"))     # N/A (valor padrão)
print(pessoa.get("idade", 0))       # 22 (existe, retorna o valor)
```

**Comparação:**

| Método | Chave existe | Chave não existe |
|--------|-------------|------------------|
| `dicio["chave"]` | Retorna valor | Erro (KeyError) |
| `dicio.get("chave")` | Retorna valor | None |
| `dicio.get("chave", valor)` | Retorna valor | Retorna valor |

---

## Adicionando e modificando elementos

### Adicionar nova chave

```python
dicio = {}

dicio["nome"] = "Carlos"    # Adiciona: {'nome': 'Carlos'}
dicio["idade"] = 25         # Adiciona: {'nome': 'Carlos', 'idade': 25}
```

### Modificar valor existente

```python
dicio = {"nome": "Carlos", "idade": 25}

dicio["nome"] = "CARLOS"    # Modifica: {'nome': 'CARLOS', 'idade': 25}
```

### Atualizar com outro dicionário

```python
dicio = {"a": 1, "b": 2}
dicio.update({"b": 3, "c": 4})

# Resultado: {'a': 1, 'b': 3, 'c': 4}
# (b foi modificado, c foi adicionado)
```

### Adicionar múltiplas chaves

```python
dicio = {"a": 1}
dicio.update(x=10, y=20, z=30)

# Resultado: {'a': 1, 'x': 10, 'y': 20, 'z': 30}
```

---

## Removendo elementos

### pop() - Remove e retorna

```python
dicio = {"a": 1, "b": 2, "c": 3}

valor = dicio.pop("a")
print(valor)    # 1
print(dicio)     # {'b': 2, 'c': 3}
```

### popitem() - Remove último par

```python
dicio = {"a": 1, "b": 2, "c": 3}

ultimo = dicio.popitem()
print(ultimo)   # ('c', 3)
print(dicio)     # {'a': 1, 'b': 2}
```

### clear() - Remove tudo

```python
dicio = {"a": 1, "b": 2}
dicio.clear()
print(dicio)     # {}
```

### del - Remover chave

```python
dicio = {"a": 1, "b": 2, "c": 3}

del dicio["b"]
print(dicio)     # {'a': 1, 'c': 3}

# ERRO: chave não existe
del dicio["z"]   # KeyError
```

---

## Verificando chaves

### Com `in` (recomendado)

```python
pessoa = {"nome": "Carlos", "idade": 25}

if "nome" in pessoa:
    print("Nome existe!")

if "cpf" not in pessoa:
    print("CPF não cadastrado")
```

### Padrão: Verificar antes de acessar

```python
dicio = {"a": 1, "b": 2}

# Forma segura
if "c" in dicio:
    print(dicio["c"])
else:
    print("Chave não encontrada")
```

---

## Iterando sobre dicionários

### Iterar sobre chaves (padrão)

```python
dicio = {"a": 1, "b": 2, "c": 3}

for chave in dicio:
    print(chave)
```

**Saída:**
```
a
b
c
```

### Iterar sobre valores

```python
dicio = {"a": 1, "b": 2, "c": 3}

for valor in dicio.values():
    print(valor)
```

**Saída:**
```
1
2
3
```

### Iterar sobre pares (chave, valor)

```python
dicio = {"a": 1, "b": 2, "c": 3}

for chave, valor in dicio.items():
    print(f"{chave}: {valor}")
```

**Saída:**
```
a: 1
b: 2
c: 3
```

### Convertendo para lista

```python
dicio = {"a": 1, "b": 2}

print(list(dicio.keys()))   # ['a', 'b']
print(list(dicio.values())) # [1, 2]
print(list(dicio.items()))   # [('a', 1), ('b', 2)]
```

---

## Métodos úteis

### Resumo dos métodos

| Método | Descrição | Exemplo |
|--------|-----------|---------|
| `.keys()` | Retorna todas as chaves | `dicio.keys()` |
| `.values()` | Retorna todos os valores | `dicio.values()` |
| `.items()` | Retorna pares (chave, valor) | `dicio.items()` |
| `.get(k, d)` | Retorna valor de k ou d | `dicio.get('a', 0)` |
| `.pop(k)` | Remove chave e retorna valor | `dicio.pop('a')` |
| `.update(d)` | Atualiza com outro dicionário | `dicio.update({'a': 1})` |
| `.clear()` | Remove todos os elementos | `dicio.clear()` |
| `.copy()` | Copia o dicionário | `dicio.copy()` |

### copy() - Cópia independente

```python
original = {"a": 1}
copia = original.copy()

copia["a"] = 99
print(original)  # {'a': 1} - Original não muda!
print(copia)     # {'a': 99}
```

> **Importante**: Sem `.copy()`, a cópia seria por referência!

---

## Exemplo: Contagem de frequência

### Versão com verificação (if/else)

```python
texto = "banana"
contagem = {}

for letra in texto:
    if letra in contagem:
        contagem[letra] += 1
    else:
        contagem[letra] = 1

print(contagem)
```

**Simulação:**

| Iteração | letra | contagem (antes) | contagem (depois) |
|---------|-------|-----------------|-------------------|
| 1 | 'b' | {} | {'b': 1} |
| 2 | 'a' | {'b': 1} | {'b': 1, 'a': 1} |
| 3 | 'n' | {'b': 1, 'a': 1} | {'b': 1, 'a': 1, 'n': 1} |
| 4 | 'a' | {'b': 1, 'a': 1, 'n': 1} | {'b': 1, 'a': 2, 'n': 1} |
| 5 | 'n' | {'b': 1, 'a': 2, 'n': 1} | {'b': 1, 'a': 2, 'n': 2} |
| 6 | 'a' | {'b': 1, 'a': 2, 'n': 2} | {'b': 1, 'a': 3, 'n': 2} |

**Resultado:** `{'b': 1, 'a': 3, 'n': 2}`

### Versão simplificada com .get()

```python
contagem = {}

for letra in texto:
    contagem[letra] = contagem.get(letra, 0) + 1
```

> `.get(letra, 0)` retorna 0 se a chave não existir!

---

## Exemplo: Encontrar o mais frequente

```python
numeros = [1, 2, 3, 1, 2, 1, 3, 1]

# Contar
contagem = {}
for n in numeros:
    contagem[n] = contagem.get(n, 0) + 1

# Encontrar o maior
mais_frequente = max(contagem, key=contagem.get)

print(mais_frequente)  # 1
print(contagem)        # {1: 4, 2: 2, 3: 2}
```

### Como funciona o max() com key

```python
contagem = {1: 4, 2: 2, 3: 2}

# max() com key compara pelos VALORES
mais_frequente = max(contagem, key=contagem.get)
#             ↑
#             Usa contagem.get() para comparar
```

| Iteração | chave avaliada | contagem.get(chave) | Maior até agora |
|---------|---------------|---------------------|-----------------|
| 1 | 1 | 4 | 1 |
| 2 | 2 | 2 | 1 |
| 3 | 3 | 2 | 1 |

---

## Exemplo: Mapeamento (tradução)

```python
# Dicionário de tradução
traducoes = {
    "hello": "olá",
    "world": "mundo",
    "python": "python"
}

palavra = input("Digite uma palavra em inglês: ")
print(traducoes.get(palavra, "Palavra não encontrada"))
```

---

## Exemplo: Agrupamento

```python
# Agrupar pessoas por idade
pessoas = [
    {"nome": "Ana", "idade": 20},
    {"nome": "Bob", "idade": 20},
    {"nome": "Carlos", "idade": 25},
    {"nome": "Diana", "idade": 25},
    {"nome": "Eva", "idade": 30}
]

# Agrupar
agrupado = {}
for pessoa in pessoas:
    idade = pessoa["idade"]
    if idade not in agrupado:
        agrupado[idade] = []
    agrupado[idade].append(pessoa["nome"])

print(agrupado)
# Resultado: {20: ['Ana', 'Bob'], 25: ['Carlos', 'Diana'], 30: ['Eva']}
```

---

## Dicionários aninhados

### Dicionário de dicionários

```python
alunos = {
    "123": {"nome": "Ana", "nota": 8.5},
    "456": {"nome": "Bob", "nota": 7.0},
    "789": {"nome": "Carlos", "nota": 9.2}
}

# Acessar
print(alunos["123"]["nome"])  # Ana
print(alunos["456"]["nota"])   # 7.0
```

### Lista de dicionários

```python
alunos = [
    {"nome": "Ana", "nota": 8.5},
    {"nome": "Bob", "nota": 7.0},
    {"nome": "Carlos", "nota": 9.2}
]

# Buscar
for aluno in alunos:
    if aluno["nome"] == "Bob":
        print(aluno["nota"])  # 7.0
```

---

## Erros comuns

### Erro 1: Chave inexistente

```python
# ERRADO
dicio = {"a": 1}
print(dicio["b"])  # KeyError!

# CERTO
print(dicio.get("b"))  # None
print(dicio.get("b", 0))  # 0
```

### Erro 2: Usar lista como chave

```python
# ERRADO - listas são mutáveis!
dicio = {[1, 2]: "valor"}  # TypeError!

# CERTO - use tuplas (imutáveis)
dicio = {(1, 2): "valor"}  # OK!
```

### Erro 3: Esquecer .items()

```python
# ERRADO - itera só sobre chaves
for chave, valor in dicio:  # ERRO!
    print(chave, valor)

# CERTO
for chave, valor in dicio.items():
    print(chave, valor)
```

### Erro 4: Modificar durante iteração

```python
# ERRADO - pode dar problema
dicio = {"a": 1, "b": 2, "c": 3}
for chave in dicio:
    if chave == "a":
        del dicio[chave]  # RuntimeError!

# CERTO - iterate sobre lista
for chave in list(dicio.keys()):
    if chave == "a":
        del dicio[chave]
```

---

## Dicas profissionais

### Dica 1: DefaultDict

```python
from collections import defaultdict

contagem = defaultdict(int)  # Default é 0 para inteiros

for letra in "banana":
    contagem[letra] += 1

print(dict(contagem))  # {'b': 1, 'a': 3, 'n': 2}
```

### Dica 2: Counter (para contagem)

```python
from collections import Counter

texto = "banana"
contagem = Counter(texto)

print(contagem)  # Counter({'a': 3, 'n': 2, 'b': 1})
print(contagem.most_common(1))  # [('a', 3)]
```

### Dica 3: Dict comprehension

```python
# Inverter dicionário
original = {"a": 1, "b": 2, "c": 3}
invertido = {v: k for k, v in original.items()}
# Resultado: {1: 'a', 2: 'b', 3: 'c'}
```

---

## Próximos Passos

Agora que você aprendeu o básico de dicionários, pratique com:

- [Exercício resolvido com dicionários](../resolvidos/problema.md)
- [Praticar com dicionários](../treinar/index.md)

---

## Resumo

| Conceito | Descrição |
|----------|------------|
| `{ }` | Cria dicionário |
| `dict[key]` | Acessa valor pela chave (erro se não existir) |
| `dict.get(k, d)` | Acesso seguro (retorna d se não existir) |
| `k in dict` | Verifica existência |
| `.keys()` | Iterar sobre chaves |
| `.values()` | Iterar sobre valores |
| `.items()` | Iterar sobre pares (chave, valor) |
| `.pop(k)` | Remove e retorna valor |
| `.update(d)` | Atualiza com outro dicionário |
| `dict()` | Construtor de dicionário |