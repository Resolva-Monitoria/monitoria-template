Neste tópico, veremos regras e padrões acerca de entradas e saídas de dados no JavaScript para resolução de problemas OBI.

### Exigências de Entrada e Saída

Declaração e uso de variável:

```javascript
var numero;
// ENTRADA
// no lugar de
const numero = Number(prompt("Digite um valor"));
// utilize o código abaixo, o "%d" indica que o valor recebido será um número inteiro
scanf("%d", "numero"); 

// SAÍDA 
//no lugar de
document.write(numero);
//utilize
printf("%d", numero); 
```

Segue também um exemplo de dois leitura de dois números informados pelo usuário e, posteriormente, a soma de ambos:

```javascript
//pedir dois numeros
scanf("%d", "numero1"); 
scanf("%d", "numero2");
//realizar operações aritméticas 
var soma = numero1+numero2;
//mostrar resultado para o usuário
printf("%d", soma); 
```

### Múltiplos inputs em uma só linha

Para leitura de múltiplas entradas em uma só linha, segue-se o seguinte padrão:

```javascript
var n, m; // Declare as variáveis previamente.
// Receba as variáveis no mesmo scanf e as separe por um espaço.
scanf("%d %d", "n", "m"); 

// Imprima apenas o que for exigido, e lembre se de escrever \n no final.
printf("%d\n", n*m);
```

É necessário separar as entradas por um espaço, pois é deste modo que a informação será inserida. Também é necessário o /n no fim de um print para que a saída fique no mesmo formato que o ambiente virtual da OBI consiga ler.

Na hora de imprimir e receber variáveis, estes são os operadores relacionais:
- %d define um valor inteiro
- %f define um valor flutuante
- %s define uma String
- %c define um caractere