# Laço `while`

O laço `while` é uma estrutura de repetição usada quando queremos executar um bloco de código **enquanto uma condição for verdadeira**.

Ele é muito útil quando **não sabemos exatamente quantas vezes** a repetição acontecerá.

---

## Sintaxe básica:

```python
while condição:
    # bloco de código
```

Enquanto a condição for verdadeira `(True)`, o código continuará repetindo.

## Exemplo simples
```
contador = 1

while contador <= 5:
    print(contador)
    contador += 1
```
Saída:
```
1
2
3
4
5
```

## O cuidado com loop infinito:

Se a condição nunca ficar falsa, o laço nunca termina.

```
while True:
    print("Olá")
```
Esse código repete para sempre.

## Contador crescente:

```
i = 0

while i < 10:
    print(i)
    i += 1
```
Saída:
```
0
1
2
3
4
5
6
7
8
9
```

## Contador decrescente:

```
i = 10

while i > 0:
    print(i)
    i -= 1
```

Saída:

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

## Somando valores:

```
i = 1
soma = 0

while i <= 5:
    soma += i
    i += 1

print(soma)
```
Saída:
```
15
```
## Lendo dados até condição parar:
```
numero = 1

while numero != 0:
    numero = int(input("Digite um número (0 para sair): "))
```
O programa só termina quando digitar `0`.

## Menu interativo:
```
opcao = -1

while opcao != 0:
    print("1 - Jogar")
    print("2 - Configurações")
    print("0 - Sair")

    opcao = int(input("Escolha: "))
```
Muito usado em sistemas e jogos.

## Usando `break`:

Encerra o laço imediatamente.
```
while True:
    texto = input("Digite sair: ")

    if texto == "sair":
        break
```

## Usando `continue`:

Pula a repetição atual.
```
i = 0

while i < 5:
    i += 1

    if i == 3:
        continue

    print(i)
```
Saída:
```
1
2
4
5
```

## Percorrendo string:

```
texto = "Python"
i = 0

while i < len(texto):
    print(texto[i])
    i += 1
```

## Percorrendo lista:
```
valores = [10, 20, 30]

i = 0

while i < len(valores):
    print(valores[i])
    i += 1
```

## Quando usar `while`?

| Situação | Recomendado |
|----------|-------------|
| Não sabemos quantas vezes repetir | `while` |
| Repetir até condição mudar | `while` |
| Contagem com parada indefinida | `while` |
| Já sabemos o número de vezes | `for` |

---