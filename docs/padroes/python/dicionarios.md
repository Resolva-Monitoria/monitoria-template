Neste tópico, veremos regras e padrões acerca de dicionários no Python para resolução problemas OBI. 
No Python, dicionários são estruturas de dados que armazenam dados em pares de chave e valor, onde cada chave é atribuída juntamente ao seu valor. É semelhante aos objetos do JavaScript.

### Utilização

Aqui segue como se cria e utiliza dicionários:

```python
dicionario = {
  "nome": "Guido",
  "idade" : 33
} # Define um dicionário

print(dicionario["nome"]) # Imprime o valor da chave nome
print(dicionario["idade"]) # Imprime o valor da chave idade
```

Também é possível declarar dicionários da seguinte forma:

```python
dicionario = dict() # Define um dicionário

dicionario["nome"] = "Guido" # Define a chave nome e seu valor
dicionario["idade"] = 33 # Define a chave idade e seu valor

print(dicionario["nome"]) # Imprime o valor da chave nome
print(dicionario["idade"]) # Imprime o valor da chave idade
```

Dentre os principais métodos para dicionários, estão estes:

```python
dicionario.values() # Retorna uma lista com os valores do dicionário
dicionario.keys() # Retorna uma lista com as chaves do dicionário
dicionario.items() # Retorna uma lista com as chaves do dicionário e seus valores

dicionario.get("nome", 0) # Caso a chave selecionada exista, retorna o valor dela, caso a chave não exista retorna o outro valor descrito
dicionario.pop("nome") # Remove a chave especificada
```

Para percorrer as chaves de um dicionário, você pode utilizar os seguintes métodos:

```python
for chave in dicionario:
  print(chave)

for chave in dicionario.keys():
  print(chave)
```

Para percorrer os valores de um dicionário, você pode utilizar os seguintes métodos:

```python
for valor in dicionario.values():
  print(valor)

for chave in dicionario.keys():
  print(dicionario[chave])
```