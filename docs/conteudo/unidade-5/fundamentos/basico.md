# Conceitos Básicos de Dicionários

Um dicionário em Python é uma estrutura de dados mutável que armazena pares de **chave: valor**. Cada chave deve ser única e pode ser de tipos imutáveis (como strings, inteiros, tuplas).

---

## Quando usar dicionários?

| Situação | Exemplo |
|----------|---------|
| Contar frequência | Contar quantas vezes cada letra aparece |
| Mapear dados | Dicionarização de nomes para notas |
| Busca rápida | Encontrar informação pela chave |
| Agrupar dados | Agrupar pessoas por idade |

---

## Sintaxe básica

```python
# Dicionário vazio
dicio = {}

# Com valores iniciais
pessoa = {"nome": "Maria", "idade": 20, "cidade": "SP"}

# Usando dict()
notas = dict(matematica=8, historia=7, portugais=9)
```

---

## Acessando valores

```python
pessoa = {"nome": "Ana", "idade": 22}

# Acesso direto (erro se chave não existir)
print(pessoa["nome"])  # Ana

# Acesso seguro (retorna None ou valor padrão)
print(pessoa.get("nome"))           # Ana
print(pessoa.get("cpf"))            # None
print(pessoa.get("cpf", "N/A"))     # N/A
```

---

## Adicionando e modificando

```python
dicio = {}

# Adicionar nova chave
dicio["chave"] = "valor"

# Modificar valor existente
dicio["chave"] = "novo valor"

# Atualizar com outro dicionário
dicio.update({"a": 1, "b": 2})
```

---

## Removendo elementos

```python
dicio = {"a": 1, "b": 2, "c": 3}

# remove e retorna o valor
valor = dicio.pop("a")

# remove última chave-valor
ultimo = dicio.popitem()

# remove todas as chaves
dicio.clear()
```

---

## Verificando chaves

```python
dicio = {"nome": "Carlos", "idade": 25}

# Verificar se chave existe
if "nome" in dicio:
    print("Nome existe!")

if "cpf" not in dicio:
    print("CPF não cadastrado")
```

---

## Iterando sobre dicionários

```python
dicio = {"a": 1, "b": 2, "c": 3}

# Iterar sobre chaves
for chave in dicio:
    print(chave)  # a, b, c

# Iterar sobre valores
for valor in dicio.values():
    print(valor)  # 1, 2, 3

# Iterar sobre itens (chave, valor)
for chave, valor in dicio.items():
    print(f"{chave}: {valor}")
```

---

## Métodos úteis

| Método | Descrição |
|--------|-----------|
| `.keys()` | Retorna todas as chaves |
| `.values()` | Retorna todos os valores |
| `.items()` | Retorna pares (chave, valor) |
| `.get(k, d)` | Retorna valor de k ou d |
| `.pop(k)` | Remove chave e retorna valor |
| `.update(d)` | Atualiza com outro dicionário |
| `.clear()` | Remove todos os elementos |

---

## Exemplo: Contagem de frequência

```python
texto = "banana"
contagem = {}

for letra in texto:
    if letra in contagem:
        contagem[letra] += 1
    else:
        contagem[letra] = 1

print(contagem)  # {'b': 1, 'a': 3, 'n': 2}
```

### Versão simplificada com `.get()`

```python
contagem = {}

for letra in texto:
    contagem[letra] = contagem.get(letra, 0) + 1
```

---

## Exemplo: Encontrar o mais frequente

```python
numeros = [1, 2, 3, 1, 2, 1, 3, 1]

contagem = {}
for n in numeros:
    contagem[n] = contagem.get(n, 0) + 1

mais_frequente = max(contagem, key=contagem.get)
print(mais_frequente)  # 1
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
| `dict[key]` | Acessa valor pela chave |
| `dict.get(k, d)` | Acesso seguro |
| `k in dict` | Verifica existência |
| `.keys()` | Iterar sobre chaves |
| `.values()` | Iterar sobre valores |
| `.items()` | Iterar sobre pares |
