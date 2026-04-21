# Exercício Resolvido com `for`

## Problema: Cálculo Rápido (OBI 2021)

🔗 Link oficial: https://olimpiada.ic.unicamp.br/pratique/p1/2021/f2/calculo/

---

## Enunciado

Dados três números inteiros:

- `S` = soma desejada dos dígitos
- `A` = início do intervalo
- `B` = fim do intervalo

Conte quantos números entre `A` e `B` possuem soma dos dígitos igual a `S`.

---

## Exemplo de Entrada

```text
3
10
30
```

## Exemplo de Saída

```text
3
```

Porque os números são: 12, 21, 30

---

## Resolução Passo a Passo

```python
s = int(input())
a = int(input())
b = int(input())

contador = 0

for numero in range(a, b + 1):
    soma = 0

    for digito in str(numero):
        soma += int(digito)

    if soma == s:
        contador += 1

print(contador)
```

---

## Explicação Linha por Linha

### 1. Ler os valores

```python
s = int(input())
a = int(input())
b = int(input())
```

O programa lê:

- valor desejado da soma dos dígitos (s)
- começo do intervalo (a)
- final do intervalo (b)

Se entrada for:

```
3
10
30
```

Então:

- s = 3
- a = 10
- b = 30

### 2. Criar contador

```python
contador = 0
```

Essa variável guarda quantos números corretos encontramos.
Começa em 0.

### 3. Percorrer os números

```python
for numero in range(a, b + 1):
```

Vai testar todos os números de a até b.

Se:

- a = 10
- b = 15

O laço percorre: 10, 11, 12, 13, 14, 15

### 4. Resetar soma dos dígitos

```python
soma = 0
```

Cada número precisa começar com soma zerada.

Exemplo: Para testar 12, começa: soma = 0

### 5. Percorrer cada dígito

```python
for digito in str(numero):
```

Transformamos o número em texto.

Exemplo:

- numero = 12
- str(numero) = "12"

Agora o laço percorre: "1", "2"

### 6. Somar os dígitos

```python
soma += int(digito)
```

Transforma cada caractere em número e soma.

Para 12:

- Primeira volta: digito = "1", soma = 0 + 1 = 1
- Segunda volta: digito = "2", soma = 1 + 2 = 3

Resultado final: soma = 3

### 7. Verificar se bate com S

```python
if soma == s:
```

Se:

- soma = 3
- s = 3

Então: contador += 1

---

## Simulação Completa

**Entrada:**

```
3
10
15
```

| Número | Soma dos Dígitos | Conta? |
|--------|-----------------|--------|
| 10     | 1               | ❌     |
| 11     | 2               | ❌     |
| 12     | 3               | ✅     |
| 13     | 4               | ❌     |
| 14     | 5               | ❌     |
| 15     | 6               | ❌     |

**Resultado:** contador = 1

### 8. Mostrar resposta

```python
print(contador)
```

Saída:

```
1
```

---
