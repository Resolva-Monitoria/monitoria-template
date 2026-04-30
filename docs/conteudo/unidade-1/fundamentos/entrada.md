# input(): Entrada de Dados

Vamos utilizar um padrão de apresentação de mensagens para o usuário. Será a função **input()**.

## input()

Semelhantemente ao prompt() que aprendemos no JavaScript, o comando input() receberá um dado de entrada a ser ditado pelo usuário que executará o código. Vejamos um exemplo simples:

```python
texto = input()
```

Com isso, ao rodar o código, haverá a possibilidade de o usuário interagir com o seu sistema gravando algo na variável texto, que poderá ser usada de outras formas ao decorrer do código.

Suponhamos que o usuário digite "Hello World" na variável texto:

```python
texto = input() # Entrada: Hello World
print(texto) # Saída: Hello World
```

### Entrada de Números

Assim como no JavaScript, também é possível especificar quando a variável de entrada deve ser um número; para tanto, usaremos a função **int()**, que converterá aquela entrada como um número inteiro:

```python
numero_inteiro = int(input())
```
 > [!NOTE]
 Note que o nome da variável está sendo declarado apenas com letras minúsculas e palavras separadas por underline (_); esta convenção de nomenclatura chama-se `snake_case`. As demais formas de declarar uma variável também são aceitas pelo Python, contanto que não haja espaços entre caracteres; porém, a maneira considerada mais adequada na comunidade de programadores da linguagem é utilizando snake_case.

Sabendo disso, podemos utilizar as variáveis para fazer operações numéricas:

```python
numero1 = int(input())
numero2 = int(input())
operacao = numero1 * numero2
print(operacao) # A saída será o primeiro número enviado pelo usuário com o segundo
```

Ainda é possível especificar um número que não será inteiro, semelhante ao  `parseFloat()` do JavaScript. Usamos a função **float()**:
```python
numero_decimal = float(input())
```

### Múltiplas Entradas

Um dos recursos mais poderosos do Python é a possibilidade de captação de duas variáveis em uma única linha, algo que é **frequentemente cobrado em problemas da OBI**. A captura é bem simples, e podemos separar em formato de **texto** ou de **números**:

- Formato de texto:
```python
x, y = input().split()
```
Com isso, você pode enviar duas palavras em uma só entrada, bastando separá-las por um espaço.

- Formato númerico:
```python
x, y = map(int, input().split())
```
Assim como no formato de texto, é possível a entrada de dois números em uma só linha, separando-os por um espaço.

### Textos em Entradas

O uso de textos em entradas, geralmente, não são permitidos em questões da OBI. Porém, a título de curiosidade, é possível seu uso de uma maneira simples:
```python
nome = input("Insira seu nome") # Output: Insira seu nome
idade = int(input("Insira sua idade")) # Output: Insira sua idade
```
Assim, o sistema mostrará o texto e, juntamente, a opção de entrada de dado.

Tendo completado o conteúdo de saída de dados, concluímos a Unidade 1, e podemos prosseguir para o conhecimento de estruturas de decisão.