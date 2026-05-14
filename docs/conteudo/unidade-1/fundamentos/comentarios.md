# `Comentários`

Comentários são anotações dentro do código. Eles servem para explicar trechos, deixar lembretes ou facilitar a leitura do programa. Sendo assim, o Python ignora comentários durante a execução do código.

---

## Comentário de Uma Linha

Para criar um comentário simples, utilizamos o símbolo `#`:

```python
# Isto é um comentário

print("Olá, Mundo!")
```

Também é possível comentar na mesma linha de um código:

```python
print("Olá, Mundo!") # Exibe uma mensagem no terminal
```

---

## Comentários de Múltiplas Linhas

Para escrever comentários maiores, de múltiplas linhas, podemos utilizar três aspas duplas `"""`:

```python
"""
Este é um comentário
de múltiplas linhas.
"""
print("Olá mundo")
```

Podemos também utilizae aspas simples `'''`:

```python
'''
Também funciona
desta forma.
'''
print("Olá mundo")
```

---

## Quando Utilizar Comentários

Comentários são úteis para:

- Explicar partes difíceis do código
- Organizar seções do programa
- Criar lembretes
- Facilitar manutenção do código

Exemplo:

```python
# Entrada de dados
nome = input()

# Saída de dados
print(nome)
```

---

## Boas Práticas

### Escreva comentários úteis

Exemplo de comentário útil:

```python
# Calcula média do aluno
media = (nota1 + nota2) / 2
```

### Evite comentários óbvios

```python
numero = 10 # Guarda 10 na variável numero
```

Neste caso, o comentário é desnecessário.

---

## Erros comuns

### Erro 1: Comentar código demais

```python
# Soma 1 + 1
resultado = 1 + 1
```

**Problema:** o comentário não acrescenta informação útil.

### Erro 2: Comentários desatualizados

```python
# Soma os números
resultado = numero1 * numero2
```

**Problema:** o comentário diz uma coisa, mas o código faz outra.

### Erro 2: Comentar antes do código

```python
# Soma os números resultado = numero1 * numero2
```

**Problema:** o bloco de código também ficou comentado.

---

## Resumo

| Conceito | Descrição |
|---|---|
| `#` | Comentário de uma linha |
| `""" """` | Comentário de múltiplas linhas |
| Comentário | Texto ignorado pelo Python |
| Boa prática | Explicar partes importantes do código |

```