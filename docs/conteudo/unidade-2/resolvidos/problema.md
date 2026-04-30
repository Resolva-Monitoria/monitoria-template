# Exercício Resolvido: Idade de Camila

## Problema: Idade de Camila (OBI 2021 - Fase 1)

🔗 [Link oficial](https://olimpiada.ic.unicamp.br/pratique/pj/2021/f1/idade/)

---

## Enunciado

Cibele, Camila e Celeste são três irmãs inseparáveis. Estão sempre juntas e adoram fazer esportes, ler, cozinhar, jogar no computador... Agora estão aprendendo a programar computadores para desenvolverem seus próprios jogos.

Mas nada disso interessa para esta tarefa: estamos interessados apenas nas suas idades. Sabemos que Cibele nasceu antes de Camila e Celeste nasceu depois de Camila.

Dados três números inteiros indicando as idades das irmãs, escreva um programa para determinar a idade de Camila.
---

## Exemplo

**Entrada**
A entrada é composta por três linhas, cada linha contendo um número inteiro N, a idade de uma das irmãs.

```
6
9
7
```

**Saída**
Seu programa deve produzir uma única linha, contendo um único número inteiro, a idade de Camila.
```
7
```

---

## Resolução

```python
N1 = int(input())
N2 = int(input())
N3 = int(input())

if N2 > N1 > N3 or N3 > N1 > N2: # Se a idade de Camila for N1
    print(N1)
elif N1 > N2 > N3 or N3 > N2 > N1: # Se a idade de Camila for N2
    print(N2)
else:
    print(N3) # Se a idade de Camila for N3
```

---

## Explicação

### 1. Ler valores

```python
N1 = int(input())
N2 = int(input())
N3 = int(input())
```

- `N1` = A idade de uma irmã
- `N2` = A idade de outra irmã
- `N3` = A idade de outra irmã

### 2. Fazer a estrutura para exibir resultados

```python
if N2 > N1 > N3 or N3 > N1 > N2: 
    print(N1)
elif N1 > N2 > N3 or N3 > N2 > N1:
    print(N2)
else:
    print(N3)
``` 

- `if N2 > N1 > N3 or N3 > N1 > N2` = Condição inicial, verifica se a idade N1 está entre as duas outras idades
- `print(N1)`: Printa a condição de a idade N1 ser a idade do meio
- O `elif N1 > N2 > N3 or N3 > N2 > N1` = Caso a idade N1 não seja a idade do meio, verifica se a idade N2 está entre as duas outras idades
- `print(N2)`: Printa a condição de a idade N2 ser a idade do meio
- `else` = Caso nenhuma das condições anteriores estejam certas
- `print(N3)`: Printa a condição de a idade N3 ser a idade do meio

---

## Simulação

**Entrada:** N1 = 6, N2 = 9, N3 = 7

**Resultado:** 7

---

## Conceitos utilizados

| Conceito | Onde foi usado |
|----------|---------------|
| `if` | Verifica uma condição inicial |
| `elif` | Verifica uma segunda condição, caso a primeira esteja incorreta |
| `else` | Executa um comando caso nenhuma das condições anteriores esteja, corretas | 

---

## Próximos Passos

- [Praticar condicionais](../treinar/index.md)
- [Voltar para índice](../resolvidos/index.md)