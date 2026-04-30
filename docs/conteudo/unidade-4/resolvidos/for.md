# Exercício Resolvido: Cálculo Rápido

## Problema: Cálculo Rápido (OBI 2021 - Fase 2)

🔗 [Link oficial](https://olimpiada.ic.unicamp.br/pratique/p1/2021/f2/calculo/)

---

## Enunciado

Dados três números inteiros:

- `S` = soma desejada dos dígitos
- `A` = início do intervalo
- `B` = fim do intervalo

Conte quantos números entre `A` e `B` possuem soma dos dígitos igual a `S`.

---

## Exemplo

**Entrada**
```
3
10
30
```

**Saída**
```
3
```

Os números são: 12, 21, 30

---

## Resolução

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

## Explicação

### 1. Ler valores

```python
s = int(input())
a = int(input())
b = int(input())
```

- `s` = soma desejada
- `a` = início do intervalo
- `b` = fim do intervalo

### 2. Percorrer números do intervalo

```python
for numero in range(a, b + 1):
```

O `range(a, b + 1)` gera: a, a+1, ..., b

### 3. Para cada número, calcular soma dos dígitos

```python
soma = 0
for digito in str(numero):
    soma += int(digito)
```

- Transforma o número em string
- Percorre cada caractere (dígito)
- Converte de volta para int e soma

Exemplo para número 12:
- Primeira iteração: soma = 0 + 1 = 1
- Segunda iteração: soma = 1 + 2 = 3

### 4. Verificar se soma bate com S

```python
if soma == s:
    contador += 1
```

### 5. Mostrar resultado

```python
print(contador)
```

---

## Simulação

**Entrada:** s=3, a=10, b=15

| Número | Soma dos Dígitos | Conta? |
|--------|------------------|--------|
| 10     | 1                | ❌     |
| 11     | 2                | ❌     |
| 12     | 3                | ✅     |
| 13     | 4                | ❌     |
| 14     | 5                | ❌     |
| 15     | 6                | ❌     |

**Resultado:** 1

---

## Conceitos utilizados

| Conceito | Onde foi usado |
|----------|---------------|
| `for` externo | Percorre números do intervalo |
| `for` interno | Percorre dígitos do número |
| `range()` | Gera sequência de números |
| `str()` | Converte número para string |
| `int()` | Converte caractere para número |
| Condição | Verifica se soma == S |

---

## Próximos Passos

- [Praticar com for](../treinar/for.md)
- [Ver exercício com while](./while.md)
- [Voltar para índice](../resolvidos/index.md)