# `if/else`

As estruturas condicionais permitem que o programa tome decisões com base em condições. Diferente de repetir ações, aqui escolhemos qual caminho seguir. O `if/else`, como visto no [conteúdo introdutório](./index.md), é a principal das estruturas de decisão.

---

## Conceito Fundamental

Imagine que você está decidindo o que fazer
```
Se estiver chovendo → levar guarda-chuva  
Caso contrário → sair normalmente
```

Com as condicionais, é possível definir uma decisão entre as duas alternativas.

> Em programação, é como dizer: "Se uma condição for verdadeira, execute um bloco. Caso contrário, execute outro"

---

## Quando usar `if/else`?

| Situação         | Exemplo                        |
| ---------------- | ------------------------------ |
| Tomar decisões   | Verificar se número é positivo |
| Validar dados    | Checar idade mínima            |
| Comparar valores | Encontrar o maior número       |
| Classificar      | Nota: aprovado/reprovado       |
| Controlar fluxo  | Executar caminhos diferentes   |

---

## Sintaxe básica

```python
if condicao:
    # Executa se condicao for verdadeira

```

### Exemplo simples

```python
idade = int(input())

if idade >= 18: # Se idade for maior do que 18
    print("Maior de idade")
```

Desta forma, se o usuário entrar com uma idade **maior ou igual a 18**, o programa vai retornar a frase "Maior de idade".

---

## if + else

O else indicará o que será feito cada a condição inicial não for verdadeira.
```python
if condicao:
    # executa se condicao for verdadeira
else:
    # executa se condicao não for verdadeira
```

### Exemplo simples

```python
idade = int(input())

if idade >= 18: # Se idade for maior do que 18
    print("Maior de idade")
else: # Se idade NÃO for igual ou maior do que 18
    print("Menor de idade")
```

**Obs.**: Nem todo IF precisa ter um ELSE, mas não existe ELSE sem IF.

### if + elif + else

Quando há mais de uma possibilidade de execução, usamos o `elif`. O elif é uma junção de `else` com `if` (else + if = elif). Na prática, temos que:

```python
if condicao1:
    # Executa se a primeira condição for verdadeira
elif condicao2:
    # Executa se a segunda condição for verdadeira
else:
    # Executa se nenhuma das duas forem verdadeiras
```

> **Atenção importante**: O valor `stop` **nunca** é incluído na sequência!

### Exemplo

```python
nota = int(input())

if nota >= 6:
    print("Aprovado")
elif nota >= 3: # Se não for maior que 6 mas for maior que 3
    print("Recuperação")
else: # Se não for maior que 6 e nem maior que 3
    print("Reprovado")
```

### Operadores lógicos

Perceba que, ao longo dos exemplos, nos deparamos com comparações de variáveis. Por exemplo, ver se a nota é igual a 6 ou 3, se a idade é igual a 18 ou não. Para tanto, utilizamos os chamados `operadores lógicos`, que são os seguintes:

| Operador | Significado    |
| -------- | -------------- |
| `==`     | Igual          |
| `!=`     | Diferente      |
| `>`      | Maior          |
| `<`      | Menor          |
| `>=`     | Maior ou igual |
| `<=`     | Menor ou igual |
| `and`    | E (ambas verdadeiras) |
| `or`     | OU (uma verdadeira)   |
| `not`    | NÃO (inverte)         |


### Exemplo

```python
idade = int(input())
tem_carteira = True 

if idade >= 18 and tem_carteira:
    print("Pode dirigir")
else:
    print("Ainda não pode dirigir")
```
 > [!NOTE]
 Note que a variável `tem_carteira` está definida com o valor `True`. No Python, isso significa, de maneira prática, isso significa que a variável tem_carteira é verdadeira.

Aqui, o problema faz duas verificações em um `if` só: O programa está dizendo o seguinte:
```
"Se o usuário tiver 18 anos ou mais e tiver carteira, pode dirigir. Senão, não pode dirigir".
```

## Exemplos detalhados

### Exemplo 1: Maior de dois números

```python
a = int(input())
b = int(input())

if a > b:
    print(a)
else:
    print(b)
```

---

### Exemplo 2: Positivo, negativo ou zero

```python
numero = int(input())

if numero > 0:
    print("Positivo")
elif numero < 0:
    print("Negativo")
else:
    print("Zero")
```

---

### Exemplo 3: Maior de três números

```python
a = int(input())
b = int(input())
c = int(input())

maior = a

if b > maior:
    maior = b

if c > maior:
    maior = c

print(maior)
```

---

### Exemplo 4: Intervalo de valores

```python
idade = int(input())

if idade < 12:
    print("Criança")
elif idade < 18:
    print("Adolescente")
else:
    print("Adulto")
```

---

## Operador ternário

Ainda existe uma outra forma de lidar com estruturas condicionais utilizando `if/else`. Chamamos de **operador ternário** as operações condicionais que escrevemos em uma única linha:

```python
numero = int(input())

resultado = "Par" if numero % 2 == 0 else "Ímpar" 
print(resultado)
```

Aqui, a variável `resultado` terá o valor `"Par"` caso seja **divisível por 2**. Caso não seja, terá o valor `"Ímpar"`.

---

## Padrões comuns

### Padrão 1: Verificar → agir

```python
if condicao:
    acao()
```

---

### Padrão 2: Atualizar valor

```python
if valor > maior:
    maior = valor
```

---

### Padrão 3: Classificação

```python
if condicao1:
    classe1
elif condicao2:
    classe2
else:
    classe3
```

## Erros comuns

### Erro 1: usar `=` ao invés de `==`

```python
# ERRADO
if numero = 10:

# CERTO
if numero == 10:
```

---

### Erro 2: esquecer indentação

```python
# ERRADO
if numero > 0:
print("Positivo")

# CERTO
if numero > 0:
    print("Positivo")
```

---

### Erro 3: ordem das condições

```python
# ERRADO
if nota >= 5:
    print("Recuperação")
elif nota >= 7:
    print("Aprovado")
```

Correto:

```python
if nota >= 7:
    print("Aprovado")
elif nota >= 5:
    print("Recuperação")
```

---

## Próximos Passos

- [Exercício resolvido com if](../resolvidos/index.md)
- [Praticar condicionais](../treinar/index.md)
- [Match/Case](./matchcase.md)

---

## Resumo

| Conceito | Descrição |
|----------|------------|
| `if` | Executa se condição for verdadeira |
| `else` | Executa caso contrário |
| `elif` | Condição intermediária |
| `==` | Comparação |
| `and` / `or` | Operadores lógicos |
| `not` | Inversão |
| Ternário | Condição em uma linha |