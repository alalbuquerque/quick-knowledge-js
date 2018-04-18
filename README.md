# Quick knowledge 
Repositório contendo estudos de sobre javascript e suas abstrações. Estruturas de dados e algoritmos complementáres.

Resumo

* [Objetos Globais](#objetos-globais)
* [Objetos padrão](#objetos-padrao)
* [Propriedades de valor](#propriedades-de-valor)
* [Propriedades de função](#propriedades-de-funcao)
* [Array](#array)

## Objetos Globais 
Objetos globais se referem aos objetos no escopo global (somente se o modo estrito/strict mode do ECMAScript 5 não for usado; Nesse caso retorna undefined). O objeto global pode ser acessado usando o operador this no escopo global. De fato, o escopo global consiste em propriedades do objeto global, incluindo propriedades herdadas, se houver.

### Propriedades de valor
Propriedades globais retornam um valor simples; eles não tem propriedades ou métodos.

- Infinity
- NaN
- undefined
- null

### Propriedades de função
Estas funções globais —funções que são chamadas globalmente ao invés de em um objeto—retornam diretamente seus resultados a quem chama.

#### eval()
Se o argumento de eval() não é uma string, eval() retorna o argumento inalterado. No exemplo a seguir, o construtor String é especificado, e eval() retorna um objeto String em vez de avaliar a string.

```js
eval(new String("2 + 2")); // retorna um objeto String contendo "2 + 2"
eval("2 + 2");             // retorna 4
```

#### isFinite()
A função global isFinite() determina se o valor transmitido é um número finito. Se necessário, o parâmetro é primeiro convertido a um número.

```js
isFinite(Infinity);  // false
isFinite(NaN);       // false
isFinite(-Infinity); // false

isFinite(0);         // true
isFinite(2e64);      // true
isFinite(null);      // true


isFinite("0");       // true, teria sido false com o  
                     // mais robusto Number.isFinite("0")
```

##### isNaN()
##### parseFloat()
##### parseInt()
##### decodeURI()
##### decodeURIComponent()
##### encodeURI()
##### encodeURIComponent()



## Array  
Array é uma estrutura de dados que armazena uma coleção de elementos de tal forma que cada um dos elementos contidos nele possa ser acessado por meio de um índice(index) ou uma chave(key). Essa estrutura pode ser conhecida como variável indexada, coleções indexadas, coleções de dados, vetor(para arrays unidimensionais) e matriz (para arrays bidimensionais).

Mas no Javascript o `array` é um objeto global que é usado na construção dessa estrutura de dado. 

### Criando arrays

Existe algumas forma de criar um `array`:

```js
// Array via construtor pode ser utilizado com ou sem new. 
var array1 = new Array(elem0, elem1);
var array2 = Array(elem0, elem1);

// Array literal é definido com o número de elementos especificado
var array3 = ['elem0', 'elem1'];
```


### Acessando items do arrays

Forma de acesar um item do `array` atraves da sua índice(index):

```js
var first = array1[0];
// elem0

var last = array1[array1.length - 1];
// array1

```

### Interando arrays

```js
// tratando uma interação dentro de uma função:
function ArrayElements(element, index, array) {
    console.log('a[' + index + '] = ' + element);
}
array1.forEach(ArrayElements);
// a[0] = elem0
// a[1] = elem1

// usando forEach direto no objeto array
array1.forEach(function(element, index, array) {
  console.log('a[' + index + '] = ' + element);
});
// a[0] = elem0
// a[1] = elem1

```

Exemplo de algoritmo:
```js
var fibonacci = []
fibonacci[1] = 1
fibonacci[2] = 1

for(var i = 3; i <= 20; i++) {
    fibonacci[i] = fibonacci[i-1] + fibonacci[i-2];
}

for (var i = 1; i < fibonacci.length; i++) {
    console.log(fibonacci[i])
}
```
### Povoando um array
Existe alguns métodos para inserir elementos num array. 

Um deles é atribuindo valores aos seus elementos. 
Por exemplo:

```js

var array3 = [];
array3[0] = 'elem0';
array3[1] = 'elem1';
array3[2] = 'elem2';

console.log(array3)
// ["elem0", "elem1", "elem2"]

```

Um deles é atribuindo valores aos seus elementos. 
Por exemplo:

```js

var array3 = [];
array3[0] = 'elem0';
array3[1] = 'elem1';
array3[2] = 'elem2';

console.log(array3)
// ["elem0", "elem1", "elem2"]

```

