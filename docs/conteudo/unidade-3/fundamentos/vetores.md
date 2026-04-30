# `Vetores`

Como vimos no [conteúdo introdutório](index.md), `vetores` são estruturas que nos permitem armazenar uma série de dados temporariamente. Funciona como uma variável que armazena mais de um valor; agora, ao invés de armazenarmos apenas um valor em uma única variável, agora, armazenaremos vários valores de uma lista.

---

## Conceito Fundamental

Imagine que você tem um programa que trabalha com uma lista de compras, e quer fazer o seguinte com elas:
```
- Exibir toda a lista
- Exibir somente o primeiro elemento da lista
```

Com os vetores, isto é possível. Para exibir um item de uma lista, basta indicá-la numericamente, conforme sua posição na tabela:
| Posição         | Produto                        |
| ---------------- | ------------------------------ |
| 0  | Café  |
| 1  | Bolacha  |
| 2  | Arroz  |
| 3  | Trigo  |
> [!NOTE]
Nunca se esqueça de que, em programação, toda lista começa na **na posição 0**.

### Exemplo simples

```python
lista_de_compras = ['Café', 'Bolacha', 'Arroz', 'Trigo']

print(lista_de_compras) # Saída: ['Café', 'Bolacha', 'Arroz', 'Trigo']
print(lista_de_compras[0]) # Saída: 'Café'
```

Assim, se quisermos chamar o primeiro item da lista, usamos

```python
print(lista_de_compras[0])
```

Se quisermos o segundo:
```python
print(lista_de_compras[1])
```

E assim por diante.
---

## Funções para manipulação de vetores:

Para a manipulação de vetores, existem diversas funções. É aqui que a "mágica" começa a acontecer:

| Função | Utilidade |
| -------- | -------------- |
| `.append()` | Adiciona um item a uma lista |
| `.pop()` | Remove o último item de uma lista |
| `.remove()` | Remove a primeira ocorrência de um item de uma lista |
| `.insert()` | Adiciona item em uma posição específica de uma lista |
| `.sort()` | Ordena os itens de uma lista em ordem crescente |
| `.slice()` | Tem por função fatiar um vetor |
| `len()` | Retorna a quantidade de itens de uma lista |

## Exemplos

Para mostrar o funcionamento da manipulação de vetores, vamos continuar utilizando a mesma lista:
```python
lista = ['Café', 'Bolacha', 'Arroz', 'Trigo']
```

### .append()

`.append()` é uma função cuja utilidade é adicionar um item a uma lista; funciona da seguinte forma:
```python
lista.append('Feijão')
print(lista) # ['Café', 'Bolacha', 'Arroz', 'Trigo', 'Feijão']
```

Assim, nossa lista agora é:
```python
lista = ['Café', 'Bolacha', 'Arroz', 'Trigo', 'Feijão']
```

### .pop()

Por padrão, `.pop()` é uma função utilizada para remover o último item de uma lista:
```python
lista.pop() # remove último
print(lista) # ['Café', 'Bolacha', 'Arroz', 'Trigo']
```

No entando, a função .pop() também é utilizada para remover um item de uma posição específica de uma lista. 
Suponhamos que queiramos remover o item `'Café'` da nossa lista; com .pop(), removeremos com base na posição de 'Café' na nossa lista:
```python
lista.pop(0) # Café é o primeiro item; logo, é o item da posição 0
print(lista) # ['Bolacha', 'Arroz', 'Trigo']
```

### .remove()

Ainda pensando em remover itens da nossa lista, também há a função `.remove()`.
Antes de usarmos a função .remove(), vamos adicionar mais um item de bolacha na nossa lista:
```python
lista.append('Bolacha')
print(lista) # ['Bolacha', 'Arroz', 'Trigo', 'Bolacha']
```

A principal diferença da função `.pop()` para a `.remove()` é que, nesta última, você indica o item, e a primeira ocorrência deste item será retirada:
```python
lista.remove('Bolacha') # Remove a primeira ocorrência de 'Bolacha'
print(lista) # ['Arroz', 'Trigo', 'Bolacha']
```
Agora, nossa lista está assim:

```python
lista = ['Arroz', 'Trigo', 'Bolacha']
```

### .insert()

A função `.insert()` serve para inserirmos um item em uma posição específica de uma lista.
Por exemplo, é normal que, para muitos, o feijão venha depois do arroz em um prato; caso você queira inserir o feijão após o arroz na lista, basta indicar a nova posição do feijão na função .insert(). Como 'Arroz' está na posição 0, inserir na posição 1 fará com que 'Feijão' venha logo depois:
```python
lista.insert(1, 'Feijão') # Insere feijão como o segundo item da lista, a posição 1
print(lista) # ['Arroz', 'Feijão', 'Trigo', 'Bolacha']
```

Assim, a função .insert() insere um novo item na posição que você quiser.

### .sort()

A função `.sort()` serve para ordenar uma lista em ordem crescente, seja ela uma ordem numérica ou alfabética:
```python
lista.sort()
print(lista) # ['Arroz', 'Bolacha', 'Feijão', 'Trigo']
```

### slice

`Slice` é o nome dado ao fatiamento de um vetor. Na prática, isso significa que odemos acessar partes da lista:

```python
print(lista[1:3]) # ['Bolacha', 'Feijão']
print(lista[:3])  # ['Arroz', 'Bolacha', 'Feijão']
print(lista[::2]) # ['Arroz', 'Feijão']
```

### len()

Podemos ter acesso ao tamanho de uma lista; para isso, usamos a função `len()`.
Diferente das demais funções, a função `len()` não pertence à lista. Ela recebe a lista como parâmetro:
```python
print(len(lista)) # Saída: 4
```

As funções de manipulação de vetores também podem ser armazenadas em uma variável:
```python
tamanho_lista = len(lista)
print(tamanho_lista) # Saída: 4
```

---

## Erros comuns

### Erro 1: Acessar posição inexistente

```python
lista = [10, 20, 30]
print(lista[3])  # Erro!
```
**Problema**: índices vão de 0 até `len(lista) - 1`

### Erro 2: Confundir .pop() com .remove()
```python
lista = [10, 20, 30]

lista.pop(20)  # ERRO
```
**Problema**: `.pop()` usa posição, não valor

### Erro 3: Esquecer que sort() altera a lista
```python
lista = [3, 1, 2]
lista.sort()

print(lista)  # [1, 2, 3]
```
**Problema**: `.sort()` modifica a lista original (não cria outra)

### Erro 4: Esperar que slice altere a lista
```python
lista = [1, 2, 3, 4]

nova = lista[1:3]

print(lista)  # [1, 2, 3, 4]
print(nova)   # [2, 3]
```
**Problema**: slice cria uma nova lista, não altera a original

### Erro 5: Misturar tipos sem perceber
```python
lista = [1, 2, 3]
lista.append("4")

print(lista)  # [1, 2, 3, '4']
```
**Problema**: Isso pode gerar erros em operações matemáticas depois.

---

## Próximos Passos

- [Exercício resolvido com vetores](../resolvidos/index.md)
- [Praticar vetores](../treinar/index.md)

---

## Resumo
| Conceito   | Descrição                             |
| ---------- | ------------------------------------- |
| Lista      | Estrutura que armazena vários valores |
| Índice     | Posição do elemento (começa em 0)     |
| `append()` | Adiciona ao final                     |
| `pop()`    | Remove por posição                    |
| `remove()` | Remove por valor                      |
| `insert()` | Insere em posição específica          |
| `sort()`   | Ordena a lista                        |
| Slice      | Acessa partes da lista                |
| `len()`    | Retorna o tamanho                     |