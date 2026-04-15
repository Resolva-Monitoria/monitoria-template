Neste tópico, veremos regras e padrões acerca de vetores no Python para resolução problemas OBI. 
No Python, vetores funcionam semelhantemente aos arrays no JavaScript.

### Definição e utilização

```python
vetor = [] # Define um vetor
vetor.append(1) # Adiciona um valor no vetor
print(vetor[0]) # Imprime o valor do índice 0
```

### Laço for

Para trabalhar com vetores, no Python, muitas vezes utilizamos o for.
Segue abaixo um modo de integrar o for com um vetor:

```python
vetor = []
for i in range(10):
 vetor.append(i)
 # Inserindo um valor em cada casa do vetor
```
```python
for i in range(len(vetor)):
 print(vetor[i])
 # Acessando os valores das casas de um vetor

for i in vetor:
 print(i)
 # Outro método de acessar um vetor
```

Outra forma de se trabalhar com vetores é através de funções e métodos nativos do próprio Python. Abaixo estão estas funções e métodos:

### .append()

Para adicionar novos elementos a um vetor você pode utilizar o método push, cada elemento novo deve estar separado por uma vírgula.

```python
vetor = []
vetor.append(1)
print(vetor) # Imprime “[1]”
```

### .pop()

Para remover um elemento de uma lista podemos utilizar o método pop, ele remove o último elemento da lista ou o elemento do índice passado.

```python
vetor = []
vetor.append(1)
vetor.append(2)
vetor.pop(0)
print(vetor) # Imprime “[2]”
```

### .sort()

Para ordenar uma lista em ordem crescente utilizamos o método sort.

```python
vetor = [2, 1, 3]
vetor.sort()
print(vetor) # Imprime “[1, 2, 3]”
```

### Reverter uma lista

Caso seja necessário inverter uma lista, utilizaremos a seguinte sintaxe:

```python
vetor = [2, 1, 3]
vetor = vetor[::-1]
print(vetor) # Imprime “[3, 1, 2]”
```

Também é possível utilizar o método .sort() da seguinte forma:

```python
vetor = [2, 1, 3]
vetor.sort(reverse=True)
print(vetor) # Imprime “[3, 1, 2]”
```

Há também a função sorted():

```python
vetor = [2, 1, 3]
novoVetor = sorted(vetor, reverse=True)
print(novoVetor) # Imprime “[3, 1, 2]”
```

### O tamanho de uma lista

Para retornar o tamanho de uma lista utilizamos a função len.

```python
vetor = [2, 1, 3]
print(len(vetor)) # Imprime “3”
```

### Copiar uma lista

```python
vetor = [2, 1, 3]
vetor2 = vetor.copy()
print(vetor2) # Imprime “2, 1, 3”
```

### Slices

Para pegar apenas frações de cada lista:

```python
vetor = [2, 1, 3]
vetor = vetor[0:2] # Pega os elementos do índice 0 até o 1
print(vetor) # Imprime “[2, 1]”
```