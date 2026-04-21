# Exercício Resolvido com `while`

## Problema: Dona Lesma (OBI 2020)

🔗 Link oficial: https://olimpiada.ic.unicamp.br/pratique/pj/2020/f2/lesma/

---

## Enunciado

Dona Lesma quer alcançar o topo de um muro.

- A cada **dia**, ela sobe uma distância fixa `S`
- A cada **noite**, ela escorrega uma distância fixa `D`
- Dado a altura do muro `A`, calcule quantos dias ela levará para chegar ao topo

---

## Exemplo de Entrada

```
4
2
1
```

## Exemplo de Saída

```
3
```

---

## Resolução Passo a Passo

```python
a = int(input())
s = int(input())
d = int(input())

altura = 0
dias = 0

while altura < a:
    altura += s
    dias += 1
    
    if altura >= a:
        break
    
    altura -= d

print(dias)
```

---

## Explicação Linha por Linha

### 1. Ler os valores

```python
a = int(input())
s = int(input())
d = int(input())
```

O programa lê:

- `a` = altura do muro
- `s` = distância que sobe por dia
- `d` = distância que escorrega por noite

Se entrada for:

```
4
2
1
```

Então:

- a = 4
- s = 2
- d = 1

### 2. Inicializar variáveis

```python
altura = 0
dias = 0
```

- `altura`: guarda a altura atual da lesma (começa no chão)
- `dias`: conta quantos dias se passaram (começa em 0)

### 3. Loop usando while

```python
while altura < a:
```

O loop continua **enquanto** a lesma não chegou ao topo.

### 4. Durante o dia

```python
altura += s
dias += 1
```

A lesma sobe durante o dia.
Contamos mais um dia.

### 5. Verificar se chegou

```python
if altura >= a:
    break
```

Se chegou ao topo, **para** o loop.
Não precisa descer à noite!

### 6. Durante a noite

```python
altura -= d
```

Se não chegou, escorrega à noite.

---

## Simulação Completa

### Entrada

```
4
2
1
```

| Dia | Altura (após subir) | Chegou? | Altura (após descer) |
|-----|---------------------|---------|---------------------|
| 1   | 0 + 2 = 2           | ❌      | 2 - 1 = 1           |
| 2   | 1 + 2 = 3          | ❌      | 3 - 1 = 2           |
| 3   | 2 + 2 = 4          | ✅      | -                   |

**Resultado:**

```
dias = 3
```


