# Laço `while`

O laço `while` é uma estrutura de repetição usada quando queremos executar um bloco de código **enquanto uma condição for verdadeira**. É ideal quando **não sabemos exatamente quantas vezes** a repetição ocorrerá.

---

## Quando usar `while`?

| Situação | Exemplo |
|----------|---------|
| Não sabemos quantas vezes repetir | Ler até digitar 0 |
| Repetir até condição mudar | Subir até atingir o topo |
| Loop com parada indefinida | Processar até acabarem os dados |
| Validação de entrada | Pedir novamente até digitar válido |

---

## Sintaxe básica

```python
while condição:
    # bloco de código
```

Enquanto a condição for verdadeira (`True`), o código continuará repetindo.

---

## Exemplo: Contador crescente

```python
contador = 1

while contador <= 5:
    print(contador)
    contador += 1
```

**Saída:**
```
1
2
3
4
5
```

---

## Cuidado: Loop infinito

Se a condição nunca ficar falsa, o laço nunca termina:

```python
while True:
    print("Olá")  # repete para sempre!
```

> **Sempre** tenha uma forma de sair do loop.

---

## Contador decrescente

```python
i = 10

while i > 0:
    print(i)
    i -= 1
```

**Saída:**
```
10
9
8
7
6
5
4
3
2
1
```

---

## Somando valores

```python
i = 1
soma = 0

while i <= 5:
    soma += i
    i += 1

print(soma)  # 15
```

---

## Ler até condição

```python
numero = 1

while numero != 0:
    numero = int(input("Digite um número (0 para sair): "))
```

O programa só termina quando o usuário digitar `0`.

---

## Menu interativo

```python
opcao = -1

while opcao != 0:
    print("1 - Jogar")
    print("2 - Configurações")
    print("0 - Sair")

    opcao = int(input("Escolha: "))
```

---

## Controle de loop

### `break` — Encerra imediatamente

```python
while True:
    texto = input("Digite 'sair' para terminar: ")

    if texto == "sair":
        break
```

### `continue` — Pula para próxima iteração

```python
i = 0

while i < 5:
    i += 1

    if i == 3:
        continue  # pula o 3

    print(i)
```

**Saída:**
```
1
2
4
5
```

---

## Percorrendo com índice

### String

```python
texto = "Python"
i = 0

while i < len(texto):
    print(texto[i])
    i += 1
```

### Lista

```python
valores = [10, 20, 30]
i = 0

while i < len(valores):
    print(valores[i])
    i += 1
```

---

## Quando usar `for` ou `while`?

| Situação | Recomendado |
|----------|-------------|
| Já sabemos o número de vezes | `for` |
| Não sabemos quantas vezes | `while` |
| Repetir até condição mudar | `while` |
| Processar sequência Known size | `for` |

---

## Próximos Passos

Pratique com:

- [Exercício resolvido com while](../resolvidos/while.md)
- [Praticar com while](../treinar/while.md)
- [Laço for](./for.md) — para repetições controladas

---

## Resumo

| Conceito | Descrição |
|----------|------------|
| `while` | Repetição enquanto condição é verdadeira |
| `break` | Encerra o loop imediatamente |
| `continue` | Pula para próxima iteração |
| Loop infinito | Cuidado! Sempre tenha condição de parada |