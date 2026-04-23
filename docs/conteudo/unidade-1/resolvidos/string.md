# Exercício Resolvido: Nome Completo

## Problema: Nome Completo (Repositório de Programação I)

🔗 [Link oficial](https://github.com/ldmfabio/Programacao/blob/master/02_variaveis_e_operadores/02_05_tipos_de_dados/02_05_01_listaExercicios/02_somaInteiros.html)

---

## Enunciado

 Peça para o usuário informar o seu nome, o nome do meio e o seu último nome. Após, o programa deverá apresentar a seguinte mensagem: "O seu nome completo é NOME NOME_DO_MEIO ULTIMO_NOME".

---

## Exemplo

**Entrada**
```
Kennedy
Araújo
dos Santos
```

**Saída**
```
O seu nome completo é Kennedy Araújo dos Santos
```

---

## Resolução

```python
N = input()
M = input()
U = input()

C = f'{N} {M} {U}'

print('O seu nome completo é {C}')
```

---

## Explicação

### 1. Ler valores

```python
N = input()
M = input()
U = input()
```

Obs.: Estamos nomeando variáveis com uma única letra maiúscula, segundo o padrão predefinido nas questões da OBI.
- `N` = nome
- `M` = nome do meio
- `U` = último nome

### 2. Concatenar nomes

```python
C = f'{N} {M} {U}'
```

O `range(a, b + 1)` gera: a, a+1, ..., b

### 3. Mostrar resultado

```python
print('O seu nome completo é {C}')
```

---

## Conceitos utilizados

| Conceito | Onde foi usado |
|----------|---------------|
| `input()` | Recebe entradas de dados do usuário |
| `print()` | Apresenta dados ao usuário |
| `variáveis` | Armazenam dados |
| `fstring` | Concatena variáveis |

---

## Próximos Passos

- [Praticar com entradas e saídas](../treinar/for.md)
- [Ver exercício com números](./number.md)
- [Voltar para índice](../resolvidos/index.md)