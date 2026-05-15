# Resumo Rápido de Python

## Saída de Dados

```python
print("Olá, mundo!")
print(f"Valor: {x}")           # f-string
print(f"{x:.2f}")              # 2 casas decimais
print(var1, var2)              # múltiplos valores
```

## Entrada de Dados

```python
nome = input()                          # string
numero = int(input())                   # inteiro
decimal = float(input())                # decimal
x, y = map(int, input().split())        # múltiplos números
a, b = input().split()                  # múltiplos textos
```

## Condicionais

```python
if condicao:
    ...
elif outra_condicao:
    ...
else:
    ...

# Operador ternário
resultado = "Par" if x % 2 == 0 else "Ímpar"

# match/case
match valor:
    case 1:
        ...
    case 2 | 3:
        ...
    case _:
        ...
```

| Operador | Significado |
|----------|-------------|
| `==` | Igual |
| `!=` | Diferente |
| `>` / `<` | Maior / Menor |
| `>=` / `<=` | Maior ou igual / Menor ou igual |
| `and` / `or` / `not` | E / OU / NÃO |

## Vetores (Listas)

```python
lista = []                              # vazia
lista = [1, 2, 3]                       # com valores
lista.append(4)                         # adiciona ao final
lista.pop()                             # remove o último
lista.pop(0)                            # remove por posição
lista.remove(2)                         # remove por valor (1ª ocorrência)
lista.insert(1, "x")                    # insere na posição
lista.sort()                            # ordena em ordem crescente
len(lista)                              # tamanho da lista
lista[1:3]                              # slice (fatiamento)
lista[i]                                # acessa posição
```

## Loops

```python
# for com range
for i in range(n):          # 0 até n-1
for i in range(1, n+1):     # 1 até n
for i in range(1, n, 2):    # step
for _ in range(n):          # descartável

# for em sequência
for item in lista:
for indice, item in enumerate(lista):
for letra in string:

# while
while condicao:
    ...

while True:
    if parar:
        break
    ...

# Controle
break       # sai do loop
continue    # pula para próxima iteração
```

## Dicionários

```python
dicio = {}                               # vazio
dicio = {"chave": "valor"}               # com valores
dicio["chave"]                           # acesso (erro se não existir)
dicio.get("chave")                       # acesso seguro
dicio.get("chave", 0)                    # com valor padrão
"chave" in dicio                         # verificar existência

dicio.keys()                             # todas as chaves
dicio.values()                           # todos os valores
dicio.items()                            # pares (chave, valor)

dicio["nova"] = valor                    # adicionar/modificar
dicio.update({"a": 1})                   # atualizar
dicio.pop("chave")                       # remover e retornar
dicio.clear()                            # limpar
```

### Contagem de frequência

```python
contagem = {}
for letra in texto:
    contagem[letra] = contagem.get(letra, 0) + 1
```

> Tabelas-verdade, simuladores e mais exemplos detalhados estão nas páginas de cada unidade no menu "Conteúdo do Curso".
