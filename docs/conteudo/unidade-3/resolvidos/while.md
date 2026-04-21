# Exercício Resolvido: Dona Lesma

## Problema: Dona Lesma (OBI 2020 - Fase 2)

🔗 [Link oficial](https://olimpiada.ic.unicamp.br/pratique/pj/2020/f2/lesma/)

---

## Enunciado

Dona Lesma quer alcançar o topo de um muro.

- A cada **dia**, ela sobe uma distância fixa `S`
- A cada **noite**, ela escorrega uma distância fixa `D`
- Dada a altura do muro `A`, calcule quantos dias ela levará para chegar ao topo

---

## Exemplo

**Entrada**
```
4
2
1
```

**Saída**
```
3
```

---

## Resolução

```python
a = int(input())  # altura do muro
s = int(input())  # distância que sobe por dia
d = int(input())  # distância que escorrega por noite

altura = 0
dias = 0

while altura < a:
    altura += s    # sobe durante o dia
    dias += 1
    
    if altura >= a:
        break      # chegou ao topo!
    
    altura -= d    # escorrega à noite

print(dias)
```

---

## Explicação

### 1. Ler valores

```python
a = int(input())  # altura do muro
s = int(input())  # quanto sobe por dia
d = int(input())  # quanto escorrega por noite
```

### 2. Inicializar variáveis

```python
altura = 0   # posição atual
dias = 0     # dias transcurridos
```

### 3. Loop até atingir o topo

```python
while altura < a:
```

Repete enquanto não chegou ao topo.

### 4. Durante o dia

```python
altura += s   # sobe
dias += 1     # conta mais um dia
```

### 5. Verificar se chegou

```python
if altura >= a:
    break   # para imediatamente
```

Se chegou ao topo, não precisa escorregar à noite!

### 6. Durante a noite (se não chegou)

```python
altura -= d   # escorrega
```

---

## Simulação

**Entrada:** A=4, S=2, D=1

| Dia | Altura (após subir) | Chegou? | Altura (após descer) |
|-----|---------------------|---------|----------------------|
| 1   | 0 + 2 = 2           | ❌      | 2 - 1 = 1           |
| 2   | 1 + 2 = 3           | ❌      | 3 - 1 = 2           |
| 3   | 2 + 2 = 4           | ✅      | -                   |

**Resultado:** 3 dias

---

## Mais Exemplos

### Exemplo 2

**Entrada:** A=12, S=5, D=2

| Dia | Altura (após subir) | Chegou? | Altura (após descer) |
|-----|---------------------|---------|----------------------|
| 1   | 5                   | ❌      | 3                   |
| 2   | 8                   | ❌      | 6                   |
| 3   | 11                  | ❌      | 9                   |
| 4   | 14                  | ✅      | -                   |

**Saída:** 4

### Exemplo 3

**Entrada:** A=10000, S=100, D=50

- A cada dia efetivo: sobe 100 - 50 = 50m
- Para 10000m: 10000 / 50 = 200 dias
- Mas no último dia ela chega antes de descer!

**Saída:** 199

---

## Conceitos utilizados

| Conceito | Onde foi usado |
|----------|---------------|
| `while` | Repete até atingir o topo |
| `break` | Sai do loop quando chega |
| Variáveis de controle | `altura` e `dias` |
| Condição de parada | `altura < a` |

---

## Quando usar `while`?

| Situação | Recomendado |
|----------|-------------|
| Não sabemos quantas vezes repetir | `while` ✅ |
| Repetir até condição mudar | `while` ✅ |
| Já sabemos o número de vezes | `for` |

---

## Próximos Passos

- [Praticar com while](../treinar/while.md)
- [Ver exercício com for](./for.md)
- [Voltar para índice](../resolvidos/index.md)