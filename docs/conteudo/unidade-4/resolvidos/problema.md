# Exercício Resolvido: Álbum da Copa

## Problema: Álbum da Copa (OBI 2018 - Fase 1)

🔗 [Link oficial](https://olimpiada.ic.unicamp.br/pratique/pj/2018/f1/album/)

---

## Enunciado

Dados o número total de espaços e figurinhas de um álbum de figurinhas, e uma lista das figurinhas já compradas (que pode conter figurinhas repetidas), sua tarefa é determinar quantas figurinhas faltam para completar o álbum.
---

## Exemplo

**Entrada**
A primeira linha contém um inteiro N indicando o número total de figurinhas e espaços no álbum. A segunda linha contém um inteiro M indicando o número de figurinhas já compradas. Cada uma das M linhas seguintes contém um número inteiro X indicando uma figurinha já comprada.

```
10
3
5
8
3
```

**Saída**
Seu programa deve produzir uma única linha contendo um inteiro, o número de figurinhas que falta para completar o álbum.
```
7
```

---

## Resolução

```python
N = int(input())
M = int(input())

compradas = []

for i in range(M):
    X = int(input())

    if X not in compradas:
        compradas.append(X)

faltam = N - len(compradas)
print(faltam)
```

---

## Explicação

### 1. Ler valores

```python
N = int(input())
M = int(input())

compradas = []
```

- `N` = Total de figurinhas e espaços no álbum
- `M` = Número de figurinhas já compradas
- `compradas` = Vetor que armazenará todas as figurinhas que já foram compradas

### 2. Percorrer números do intervalo

```python
for i in range(M):
    X = int(input())
``` 
- `for i in range(M)` = Executa um bloco de código M vezes
- `X` = O número de uma figurinha já comprada

### 3. Armazenar figurinhas compradas

```python
if X not in compradas:
    compradas.append(X)
```
- Verifica se o número já está no vetor
- Se não estiver, adiciona o número ao vetor

### 3. Imprimir o resultado
```python
faltam = N - len(compradas)
print(faltam)
```
- `faltam` = Calcula quantas figurinhas compradas seguindo a expressão: `total de figurinhas no álbum - total de figurinhas já adquiridas`
- Imprime o total de figuinhas que faltam
---

## Simulação

**Entrada:**  N= 10, M = 3, X1 = 5, X2 = 8, X3 = 3
**Resultado:** 7

---

## Conceitos utilizados

| Conceito | Onde foi usado |
|----------|----------------|
| Vetores/Listas | Armazenar as figurinhas compradas |
| `.append()` | Adicionar figurinhas ao vetor |
| `len()` | Descobrir quantas figurinhas diferentes já existem |
| `if` | Verificar se a figurinha já foi adicionada |
| `not in` | Evitar armazenar figurinhas repetidas |
| `for` | Repetir a leitura das figurinhas compradas |
| `range()` | Executar o loop exatamente `M` vezes |

---

## Próximos Passos

- [Praticar vetores](../treinar/index.md)
- [Voltar para índice](../resolvidos/index.md)