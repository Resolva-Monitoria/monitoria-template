# print(): Saída de Dados

Vamos utilizar um padrão de apresentação de mensagens para o usuário. Será a função **print()**.

Para escrevermos os códigos em Python, podemos utilizar o Python no VSCode (unidade de Instalação) ou podemos abrir um bloco de código no Google Colab. De ambas as formas, a escrita de código será a mesma.

## print()

Semelhantemente ao console.log() que aprendemos no JavaScript, o comando print() exibirá seu conteúdo quando for rodado no Python. Vamos usar um exemplo com a famosa frase "Hello World!":

```python
print('Hello World') # Saída: Hello World
```

No Python, não é usado ponto e vírgula, e a utilização das aspas na entrada de mensagens de texto (strings), entre simples e duplas, é independente, ou seja, fica a critério do programador:

```python
print("Hello World") # Saída: Hello World
```

### Expressões Matemáticas

Além disso, é possível efetuar expressões matemáticas dentro do método print(), no caso de exibir um resultado para o usuário:

```python
print(6 + 7) # Saída: 13
print(6 * 7) # Saída: 42
```

### Variáveis

Outra forma de exibir uma mensagem para o usuário é capturando seu valor em uma variável e exibindo a própria variável no método print().

Note que a declaração de variáveis no Python não depende de palavras-chave, como `const` e `let` no JavaScript.

```python
nome = 'João da Silva'
idade = 67
print(nome, idade) # Saída: João da Silva 67
```

### Concatenação

A concatenação de variáveis e textos no Python pode ser feita de várias formas. A principal é utilizando um conceito chamado **fstring**, da seguinte forma:

```python
nome = 'João da Silva'
idade = 67
print(f'{nome} tem {idade} anos.') # João da Silva tem 67 anos.
```

Igualmente, podemos exibir expressões matemáticas com fstrings:
```python
numero1 = 6
numero2 = 7
print(f'O número {numero1} multiplicado por {numero2} é igual a {numero1 * numero2}.') # Saída: O número 6 multiplicado por 7 é igual a 42.
```

Também é possível regularmos as quantidades de casas decimais a serem exibidas, semelhante ao uso de `.toFixed()` no JavaScript:

```python
numero1 = 6
numero2 = 7
operacao = numero1 / numero2
print(f'O número {numero1} dividido por {numero2} é igual a {operacao:.3f}') # Saída: O número 6 dividido por 7 é igual a 0.857
```
Note que, agora, estamos armazenando o resultado da operação matemática dentro de uma variável chamada operacao. o método :.3f é a forma que utilizamos, dentro das fstrings, para apresentar somente três digitos nas casas decimais.

Visto isso, podemos seguir ao próximo passo para saber como pedir uma entrada ao usuário.