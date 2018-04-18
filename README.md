# Quick knowledge 
Repositório contendo estudos de sobre javascript e suas abstrações. Estruturas de dados e algoritmos complementáres.

* [Objetos Globais](#objetos-globais)
* [Objetos padrão](#objetos-padrao)
* [Propriedades de valor](#propriedades-de-valor)
* [Propriedades de função](#propriedades-de-função)
* [eval()](#eval)
* [isfinite()](#isfinite)
* [isNaN()](#isnan)
* [parseFloat()](#parsefloat)
* [parseInt()](#parseint)
* [Objetos fundamentais](#objetos-fundamentais)
* [Object](#object)
* [Function](#function)
* [Boolean](#boolean)
* [Error](#error)
* [EvalError](#evalerror)
* [InternalError](#internalerror)
* [RangeError](#rangeerror)
* [ReferenceError](#referenceerror)
* [StopIteration](#stopinteration)
* [SyntaxError](#syntaxerror)
* [TypeError](#typeerror)
* [URIError](#urierror)
* [Array](#array)

# Overview Javascript

## Objetos Globais 
Objetos globais se referem aos objetos no escopo global (somente se o modo estrito/strict mode do ECMAScript 5 não for usado; Nesse caso retorna undefined). O objeto global pode ser acessado usando o operador this no escopo global. De fato, o escopo global consiste em propriedades do objeto global, incluindo propriedades herdadas, se houver.

### Propriedades de valor
Propriedades globais retornam um valor simples; eles não tem propriedades ou métodos.

- `Infinity`
- `NaN`
- `undefined`
- `null`

### Propriedades de função
Estas funções globais que são chamadas globalmente ao invés de em um objeto—retornam diretamente seus resultados a quem chama.

#### eval()
Se o argumento de `eval()` não é uma string, `eval()` retorna o argumento inalterado. No exemplo a seguir, o construtor `String` é especificado, e `eval()` retorna um objeto String em vez de avaliar a string.

```js
eval(new String("2 + 2")); 
// retorna um objeto String contendo "2 + 2"

eval("2 + 2");             
// retorna 4
```

#### isFinite()
A função global `isFinite()` determina se o valor transmitido é um número finito. Se necessário, o parâmetro é primeiro convertido a um número.
```js
isFinite(Infinity);  
// false

isFinite(NaN);       
// false

isFinite(-Infinity); 
// false

isFinite(0);         
// true

isFinite(2e64);      
// true

isFinite(null);      
// true

isFinite("0");       
// true, teria sido false com o  
// mais robusto Number.isFinite("0")
```

#### isNaN()
A função `isNAN()` determina se o valor é `NaN` ou não. 
```js
isNaN(NaN);       
// true

isNaN(undefined); 
// true

isNaN({});        
// true

isNaN(true);      
// false

isNaN(null);      
// false

isNaN(37);        
// false

// strings
isNaN("37");      
// false: "37" is converted to the number 37 which is not NaN

isNaN("37.37");   
// false: "37.37" is converted to the number 37.37 which is not NaN

isNaN("");        
// false: the empty string is converted to 0 which is not NaN

isNaN(" ");       
// false: a string with spaces is converted to 0 which is not NaN

// dates
isNaN(new Date());                
// false

isNaN(new Date().toString());     
// true

// Esse é um falso positivo e é a razão para isNaN não seja totalmente confiável.
isNaN("blabla")   
// true: "blabla" é convertido para número. 
// A análise desse número falha e retorna NaN como resultado.
```

#### parseFloat()
A função `parseFloat()` analisa um argumento string e retorna um número de ponto flutuante.
```js
//Os exemplo a seguir sempre retorna 3.14
parseFloat("3.14");
parseFloat("314e-2");
parseFloat("0.0314E+2");
parseFloat("3.14more non-digit characters");
```

#### parseInt()
A função `parseInt()` analisa um argumento string e retorna um inteiro na base especificada.
```js
//Os exemplo a seguir sempre retorna 15
parseInt(" 0xF", 16);
parseInt(" F", 16);
parseInt("17", 8);
parseInt(021, 8);
parseInt("015", 10);
parseInt(15.99, 10);
parseInt("FXX123", 16);
parseInt("1111", 2);
parseInt("15*3", 10);
parseInt("15e2", 10);
parseInt("15px", 10);
parseInt("12", 13);
```

#### decodeURI()
A função `decodeURI()` decodifica Uniform Resource Identifier (URI) previamente criado por encodeURI ou por uma rotina similar.
```js
decodeURI(encodedURI)
```

#### decodeURIComponent()
O método `decodeURIComponent()` decodifica um componente Identificador Uniforme de Recursos (URI) criado anteriormente por um encodeURIComponent ou por uma rotina semelhante.
```js
decodeURIComponent(encodedURI)
```

#### encodeURI()
A função `encodeURI()` codifica um URI (Uniform Resource Identifier) substituindo cada instância de certos caracteres por uma, duas, três ou quatro seqüências de escape representando a codificação UTF-8 do caractere (serão apenas quatro seqüências de escape para caracteres compostos). de dois caracteres "substitutos").
```js
encodeURI(URI)
```

#### encodeURIComponent()
O método `encodeURIComponent()` codifica  uma URI (Identificador recurso uniforme) substituindo cada ocorrência de determinados caracteres por um, dois, três, ou quatro seqüências de escape que representam a codificação UTF-8 do caractere (só será quatro seqüências de escape para caracteres compostos por dois caracteres "substituto").
```js
encodeURIComponent(str);
```

## Objetos fundamentais
Estes são objetos básicos e fundamentais nos quais todos os outros objetos são baseados. Isso inclui objetos que representam objetos genéricos, funções e erros.

### Object
Cria um novo objeto.
```js
new Object( [ valor ] )
// qualquer valor
```

### Function
O construtor Function cria um novo objeto Function. Em JavaScript cada função é, na verdade, um objeto Function.
```js
new Function ([arg1[, arg2[, ...argN]],] functionBody)
```
`arg1, arg2, ... argN`
Nomes para serem usandos pela função como nomes formais de argumentos. Cada um deve ser uma string que corresponde para uma válida identidade JavaScript ou uma lista de certas strings separadas com uma vírgula; por exemplo "x", "theValue". our "a,b".

`functionBody`
Uma string que contém as instruções JavaScript que compõem a definição da função.

### Boolean 
O objeto Boolean é um objeto wrapper para um valor booleano.
```js
new Boolean([value])
// value Opcional. O valor inicial do objeto Boolean.
```

### Error
O construtor de Error cria um objeto de erro. Instâncias de objetos Error são lançadas quando erros de tempo de execução ocorrem. O objeto Error também pode ser usado como objeto base para exceções definidas pelo usuário. Veja abaixo tipos de erro padrões embutidos.
```js
new Error([message[, fileName[, lineNumber]]])
```
`message`
Descrição do erro legível.

`fileName` 
O valor da propriedade fileName  no objeto de erro criado. O padrão é o nome do arquivo contendo o código que chamou o construtor de Error().

`lineNumber` 
O valor da propriedade lineNumber no objeto de Error criado. O padrão é o número da linha contendo a invocação do construtor Error().


### EvalError
O Objeto EvalError indica um erro em relação a função global eval(). Esta exceção não é mais lançada pelo JavaScript, no entanto, o objeto EvalError ainda permanece compatível.
```js
new EvalError([message[, fileName[, lineNumber]]])
```
`message`
Descrição do erro legível.

`fileName` 
O nome do arquivo que contém o código que causa a exceção

`lineNumber` 
O número da linha do código que causa a exceção


### InternalError
### RangeError
### ReferenceError
### StopIteration
### SyntaxError
### TypeError
### URIError







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

