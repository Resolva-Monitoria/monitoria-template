# Laço `while`

O laço `while` é uma estrutura de repetição usada quando queremos executar um bloco de código **enquanto uma condição for verdadeira**. É ideal quando **não sabemos exatamente quantas vezes** a repetição ocorrerá.

---

## Conceito Fundamental

Imagine que você está esperando um amigo:
- Você fica esperando **enquanto** ele não chegar
- Assim que ele chegar, você para de esperar

Com o laço `while`, você define uma **condição de continuidade**, não um número fixo de repetições.

> "Enquanto a condição for verdadeira, continue repetindo."

---

## Quando usar `while`?

| Situação | Exemplo |
|----------|---------|
| Não sabemos quantas vezes repetir | Ler até digitar 0 |
| Repetir até condição mudar | Subir escada até atingir o topo |
| Loop com parada indefinida | Processar até acabarem os dados |
| Validação de entrada | Pedir novamente até digitar válido |
| Esperar algo acontecer | Aguardar condição se tornar falsa |

### Quando NÃO usar while

- Quando você **sabe** o número de repetições → Use `for`
- Quando está iterando sobre uma lista → Use `for`

---

## Sintaxe básica

```python
while condição:
    # bloco de código
```

Onde:
- **`condição`** é uma expressão que resulta em `True` ou `False`
- **Bloco indentado** é o código repetido enquanto `True`

### Como funciona

```
1. Avaliar a condição
2. Se for True → executar bloco → voltar ao passo 1
3. Se for False → sair do loop → continuar programa
```

---

## Exemplo: Contador crescente

```python
contador = 1

while contador <= 5:
    print(contador)
    contador += 1
```

**Simulação passo a passo:**

| Iteração | condição (contador <= 5) | Bloco executado | contador depois |
|---------|---------------------|-------------|---------------|
| 1 | 1 <= 5 → ✅ True | print(1), contador=2 | 2 |
| 2 | 2 <= 5 → ✅ True | print(2), contador=3 | 3 |
| 3 | 3 <= 5 → ✅ True | print(3), contador=4 | 4 |
| 4 | 4 <= 5 → ✅ True | print(4), contador=5 | 5 |
| 5 | 5 <= 5 → ✅ True | print(5), contador=6 | 6 |
| 6 | 6 <= 5 → ❌ False | **(sai do loop)** | - |

**Saída:**
```
1
2
3
4
5
```

---

## Exemplo: Contador decrescente

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

## CUIDADO: Loop infinito

Se a condição nunca ficar falsa, o laço **nunca termina**!

### Exemplos de loops infinitos

```python
# ERRADO 1: Condição永远 verdadeira
while True:
    print("Olá")  # Repete para sempre!

# ERRADO 2: Esquecer de incrementar (em Python)
contador = 1
while contador <= 5:
    print(contador)
    # Esquecido: contador += 1

# ERRADO 3: Condição nunca atingida
x = 10
while x > 5:
    print(x)
    x += 1  # Aumentando, não diminuindo!
```

### Como evitar loops infinitos

✅ **Sempre** tenha uma forma de sair do loop:
- Incremente/diminua um contador
- Modifique a condição dentro do loop
- Use `break` para sair

---

## Exemplos práticos

### Exemplo 1: Somar valores até negativo

```python
soma = 0

while True:
    numero = int(input())
    
    if numero < 0:
        break  # Sai do loop
    
    soma += numero

print(soma)
```

> Use `break` para sair quando necessário.

### Exemplo 2: Ler N números ou até 0

```python
soma = 0

while True:
    numero = int(input())
    
    if numero == 0:
        break  # Para quando digitar 0
    
    soma += numero

print(soma)
```

### Exemplo 3: Menu interativo

```python
opcao = -1

while opcao != 0:
    print("1 - Jogar")
    print("2 - Configurações")
    print("0 - Sair")
    
    opcao = int(input("Escolha: "))
    
    if opcao == 1:
        print("Iniciando jogo...")
    elif opcao == 2:
        print("Abrindo configurações...")
    elif opcao == 0:
        print("Saindo...")
    else:
        print("Opção inválida!")
```

---

## Controle de loop

### `break` — Encerra imediatamente

```python
while True:
    texto = input("Digite algo (sair para terminar): ")
    
    if texto == "sair":
        break  # Sai do loop imediatamente
    
    print(f"Você digitou: {texto}")
```

**Simulação:**
```
Digite algo: ola
Você digitou: ola
Digite algo: sair
(sai do loop)
```

### `continue` — Pula para próxima iteração

```python
i = 0

while i < 5:
    i += 1
    
    if i == 3:
        continue  # Pula para próxima iteração
    
    print(i)
```

**Saída:**
```
1
2
4
5
```

> Note que o 3 não foi impresso porque pulamos com `continue`.

### `continue` vs `break`

| Comando | O que faz |
|---------|----------|
| `break` | Sai do loop completamente |
| `continue` | Pula para a próxima iteração |

---

## Validação de entrada

O `while` é muito usado para validar entrada do usuário.

### Exemplo: Número positivo

```python
numero = int(input("Digite um número positivo: "))

while numero <= 0:
    print("Erro! O número deve ser positivo.")
    numero = int(input("Digite novamente: "))

print(f"Você digitou: {numero}")
```

### Exemplo: Opção válida

```python
opcao = ""

while opcao not in ["S", "N"]:
    opcao = input("Digite S ou N: ").upper()

print("Opção escolhida:", opcao)
```

---

## Padrões comuns

### Padrão 1: Ler até condição

```python
while True:
    valor = input("Digite (0 para parar): ")
    
    if valor == "0":
        break
    
    processar(valor)
```

### Padrão 2: Contador com condição

```python
contador = 0
limite = 10

while contador < limite:
    fazer_algo()
    contador += 1
```

### Padrão 3: Esperar condição

```python
resposta = ""

while resposta != "sim":
    resposta = input("Quer continuar? ").lower()
```

### Padrão 4: Contagem regressiva com pausa

```python
tempo = 10

while tempo > 0:
    print(f"Iniciando em {tempo}...")
    tempo -= 1

print("GO!")
```

---

## Percorrendo com índice

Às vezes precisamos usar índices, não `for`.

### String

```python
texto = "Python"
i = 0

while i < len(texto):
    print(texto[i])
    i += 1
```

**Saída:**
```
P
y
t
h
o
n
```

### Lista

```python
valores = [10, 20, 30]
i = 0

while i < len(valores):
    print(valores[i])
    i += 1
```

### Também funcionam com negativo

```python
texto = "Python"

# De trás para frente
i = len(texto) - 1

while i >= 0:
    print(texto[i])
    i -= 1
```

**Saída:**
```
n
o
h
t
y
P
```

---

## while vs for

| Característica | `for` | `while` |
|---------------|-------|---------|
| Quando usar | Já sabemos o total | Não sabemos o total |
| Controle | Contador implícito | Contador explícito |
| Risco | Menor | Loop infinito |
| Legibilidade | Mais limpo | Mais flexível |

### Convertendo for para while

```python
# Com for
for i in range(5):
    print(i)

# Com while
i = 0
while i < 5:
    print(i)
    i += 1
```

> **Regra prática**: Se você sabe o número de repetições, use `for`. Se não sabe, use `while`.

---

## Erros comuns

### Erro 1: Loop infinito

```python
# ERRADO
i = 1
while i <= 5:
    print(i)
    # Esqueceu i += 1!

# CERTO
i = 1
while i <= 5:
    print(i)
    i += 1
```

### Erro 2: Condição sempre falsa

```python
# ERRADO
x = 10
while x > 20:  # Já é falso!
    print(x)
```

### Erro 3: break esquecido

```python
# ERRADO: loop infinito
while True:
    valor = input("Digite: ")
    # Esqueceu o break!
```

### Erro 4: Condição de parada errada

```python
# ERRADO: sai quando não deveria
while opcao != "sair":
    opcao = input("Digite: ")
    # Se digitar "sair", continúa porque verifica no início!

# CERTO: verifica no lugar certo
while True:
    opcao = input("Digite: ")
    if opcao == "sair":
        break
```

---

## Dicas profissionais

### Dica 1: Use booleano para контрonar

```python
jogo_ativo = True

while jogo_ativo:
    # Jogar...
    if notquer_mais:
        jogo_ativo = False
```

### Dica 2: Múltiplas condições

```python
while idade >= 18 and Nacionalidade == "brasileira":
    # Processar...
```

### Dica 3: Contador segurança

```python
tentativas = 0
max_tentativas = 3

while tentativas < max_tentativas:
    tentativas += 1
    # Tentar algo...
    if sucesso:
        break
```

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
| `continue` vs `break` | Pular vs Sair |
| `while True` + `break` | Padrão comum para loops flexíveis |