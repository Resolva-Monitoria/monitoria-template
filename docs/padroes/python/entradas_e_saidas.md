## Entradas e Saídas

Neste tópico, veremos regras e padrões acerca de entradas e saídas de dados no Python para resolução de problemas OBI.

### Exigências de Entrada e Saída

```python
x = int(input()) # Captura um inteiro e salva na variável x
print(x) # Retorna a variável x ao usuário
```

### Múltiplos Inputs em uma só linha

```python
x, y = map(int, input().split())
```