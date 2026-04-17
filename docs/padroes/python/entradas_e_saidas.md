Neste tópico, veremos regras e padrões acerca de entradas e saídas de dados no Python para resolução de problemas OBI.

### Exigências de Entrada e Saída

```python
x = int(input()) # Captura um inteiro e salva na variável x
print(x) # Retorna a variável x ao usuário
```

### Múltiplos inputs em uma só linha

```python
x, y = map(int, input().split())
[x, y] = [int(x) for x in input().split()] # A captura funciona de ambas as formas
```
Imprimindo ambos na mesma linha:

```python
print(f”{x} {y}”)
```

### Imprimir lista em uma só linha

```python
lista = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

print(*lista)
```