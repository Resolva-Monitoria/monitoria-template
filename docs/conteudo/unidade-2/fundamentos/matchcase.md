# `match/case`

O `match/case` é uma estrutura de decisão introduzida no Python 3.10. Ele permite comparar um valor com vários casos possíveis, funcionando de forma semelhante a um "switch" em outras linguagens.

Apesar de útil, seu uso é **menos comum em programação competitiva**, onde `if/elif` costuma ser suficiente.

---

## Conceito Fundamental

Imagine que você quer executar uma ação com base em um valor específico:

```
Se for 1 → fazer algo  
Se for 2 → fazer outra coisa  
Se for 3 → fazer outra coisa  
```

O `match` permite organizar isso de forma mais estruturada.

> Em programação: "Compare um valor com vários casos possíveis e execute o correspondente."

---

## Quando usar `match/case`?

| Situação | Exemplo |
|----------|---------|
| Múltiplas comparações simples | Menu de opções |
| Valores fixos conhecidos | Dias da semana |
| Substituir muitos `elif` | Código mais organizado |

---

## Sintaxe básica

```python
match variavel:
    case valor1:
        # executa se for valor1
    case valor2:
        # executa se for valor2
    case _:
        # caso padrão (default)
```

---

## Exemplo simples

```python
numero = int(input())

match numero:
    case 1:
        print("Um")
    case 2:
        print("Dois")
    case 67:
        print("Sessenta e sete")
    case _:
        print("Outro número")
```

---

## O `case _`

O `_` funciona como um **caso padrão**, equivalente ao `else`.

```python
case _:
    print("Valor não esperado")
```

---

## Comparação com `if/elif`

### Usando `if`

```python
numero = int(input())

if numero == 1:
    print("Um")
elif numero == 2:
    print("Dois")
else:
    print("Outro")
```

### Usando `match`

```python
numero = int(input())

match numero:
    case 1:
        print("Um")
    case 2:
        print("Dois")
    case _:
        print("Outro")
```

---

## Exemplo prático: Menu

```python
opcao = int(input())

match opcao:
    case 1:
        print("Iniciar jogo")
    case 2:
        print("Configurações")
    case 3:
        print("Sair")
    case _:
        print("Opção inválida")
```

---

## Agrupando casos

É possível tratar vários valores da mesma forma:

```python
dia = int(input())

match dia:
    case 1 | 2 | 3 | 4 | 5:
        print("Dia útil")
    case 6 | 7:
        print("Fim de semana")
```

Aqui, em programação, é como se fosse falado: "caso o dia seja 1 **ou** 2 **ou** 3 **ou** 4 **ou** 5, é dia útil. Caso seja 6 **ou** 7, é fim de semana".

---

## Erros comuns

### Erro 1: esquecer o `case _`

```python
# Pode deixar casos sem tratamento
match valor:
    case 1:
        print("Um")
```
Diferente do `if + else`, não existe `match` sem `case` ou vice-versa.
Melhor:

```python
match valor:
    case 1:
        print("Um")
    case _:
        print("Outro")
```

---

### Erro 2: usar para condições complexas

```python
# NÃO recomendado
match numero:
    case numero > 10:
        print("Maior que 10")
```

👉 `match` não substitui comparações gerais. Use `if` nesses casos.

---

## Quando NÃO usar

- Comparações com intervalos (`>`, `<`)
- Condições complexas
- Problemas de OBI (em geral)

👉 Nesses casos, prefira `if/elif`.

---

## Próximos Passos

- [Voltar para condicionais](./ifelse.md)
- [Praticar condicionais](../treinar/ifelse.md)

---

## Resumo

| Conceito | Descrição |
|----------|------------|
| `match` | Estrutura de múltiplos casos |
| `case` | Define um valor específico |
| `case _` | Caso padrão (como else) |
| `|` | Permite múltiplos valores no mesmo caso |