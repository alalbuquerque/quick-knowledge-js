# Quick knowledge 
Repositório contendo estudos de sobre javascript e suas abstrações. Estruturas de dados e algoritmos complementáres.

## Overview Javascript

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


## Objetos Globais 
Objetos globais se referem aos objetos no escopo global (somente se o modo estrito/strict mode do ECMAScript 5 não for usado; Nesse caso retorna undefined). O objeto global pode ser acessado usando o operador this no escopo global. De fato, o escopo global consiste em propriedades do objeto global, incluindo propriedades herdadas, se houver.

## Propriedades de valor
Propriedades globais retornam um valor simples; eles não tem propriedades ou métodos.

### Infinity
A propriedade `Infinity` é um valor numérico que representa infinito.
```js
var maxNumber = Math.pow(10, 1000); // max positive number

if (maxNumber === Infinity) {
  console.log("Let's call it Infinity!");
  // expected output: "Let's call it Infinity!"
}

console.log(1 / maxNumber);
// expected output: 0

```

### NaN
A propriedade `NaN` é um valor representativo de Not-A-Number.
```js 
function sanitise(x) {
  if (isNaN(x)) {
    return NaN;
  }
  return x;
}

console.log(sanitise('1'));
// expected output: "1"

console.log(sanitise('NotANumber'));
// expe
```


### undefined
A propriedade `undefined`que representa o valor primitivo undefined.
```js
function test(t) {
  if (t === undefined) {
     return 'Undefined value!';
  }
  return t;
}

var x;

console.log(test(x));
// expected output: "Undefined value!"
```

### null
A propriedade `null` representa a ausência intencional de qualquer valor de objeto.
```js
function getVowels(str) {
  var m = str.match(/[aeiou]/gi);
  if (m === null) {
    return 0;
  }
  return m.length;
}

console.log(getVowels('sky'));
// expected output: 0

```

## Propriedades de função
Estas funções globais que são chamadas globalmente ao invés de em um objeto—retornam diretamente seus resultados a quem chama.

### eval()
Se o argumento de `eval()` não é uma string, `eval()` retorna o argumento inalterado. No exemplo a seguir, o construtor `String` é especificado, e `eval()` retorna um objeto String em vez de avaliar a string.

```js
eval(new String("2 + 2")); 
// retorna um objeto String contendo "2 + 2"

eval("2 + 2");             
// retorna 4
```

### isFinite()
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

### isNaN()
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

### parseFloat()
A função `parseFloat()` analisa um argumento string e retorna um número de ponto flutuante.
```js
//Os exemplo a seguir sempre retorna 3.14
parseFloat("3.14");
parseFloat("314e-2");
parseFloat("0.0314E+2");
parseFloat("3.14more non-digit characters");
```

### parseInt()
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

### decodeURI()
A função `decodeURI()` decodifica Uniform Resource Identifier (URI) previamente criado por encodeURI ou por uma rotina similar.
```js
decodeURI(encodedURI)
```

### decodeURIComponent()
O método `decodeURIComponent()` decodifica um componente Identificador Uniforme de Recursos (URI) criado anteriormente por um encodeURIComponent ou por uma rotina semelhante.
```js
decodeURIComponent(encodedURI)
```

### encodeURI()
A função `encodeURI()` codifica um URI (Uniform Resource Identifier) substituindo cada instância de certos caracteres por uma, duas, três ou quatro seqüências de escape representando a codificação UTF-8 do caractere (serão apenas quatro seqüências de escape para caracteres compostos). de dois caracteres "substitutos").
```js
encodeURI(URI)
```

### encodeURIComponent()
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
### SyntaxError
### TypeError
### URIError

## Numbers and dates
These are the base objects representing numbers, dates, and mathematical calculations.

### Number
### Math
### Date

## Text processing
These objects represent strings and support manipulating them.

### String
### RegExp

## Indexed collections
These objects represent collections of data which are ordered by an index value. This includes (typed) arrays and array-like constructs.

### Array  
Array é uma estrutura de dados que armazena uma coleção de elementos de tal forma que cada um dos elementos contidos nele possa ser acessado por meio de um índice(index) ou uma chave(key). Essa estrutura pode ser conhecida como variável indexada, coleções indexadas, coleções de dados, vetor(para arrays unidimensionais) e matriz (para arrays bidimensionais).

Mas no Javascript o `array` é um objeto global que é usado na construção dessa estrutura de dado. 

Reference Array
* array.@@iterator
* Array.@@species
* array.@@unscopables
* array.concat
* array.copyWithin
* array.entries
* array.every
* array.fill
* array.filter
* array.find
* array.findIndex
* array.flatMap
* array.flatten
* array.forEach
* Array.from
* array.includes
* array.indexOf
* Array.isArray
* array.join
* array.keys
* array.lastIndexOf
* Array.length
* array.map
* Array.of
* array.pop
* Array.prototype
* array.push
* array.reduce
* array.reduceRight
* array.reverse
* array.shift
* array.slice
* array.some
* array.sort
* array.splice
* array.toLocaleString
* array.toString
* array.unshift
* array.values



#### Criando arrays

Existe algumas forma de criar um `array`:

```js
// Array via construtor pode ser utilizado com ou sem new. 
var array1 = new Array(elem0, elem1);
var array2 = Array(elem0, elem1);

// Array literal é definido com o número de elementos especificado
var array3 = ['elem0', 'elem1'];
```


#### Acessando items do arrays

Forma de acesar um item do `array` atraves da sua índice(index):

```js
var first = array1[0];
// elem0

var last = array1[array1.length - 1];
// array1

```

#### Interando arrays

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
#### Povoando um array
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

### Int8Array
### Uint8Array
### Uint8ClampedArray
### Int16Array
### Uint16Array
### Int32Array
### Uint32Array
### Float32Array
### Float64Array

## Keyed collections
These objects represent collections which use keys; these contain elements which are iterable in the order of insertion.

### Map
### Set
### WeakMap
### WeakSet

## Vector collections
SIMD vector data types are objects where data is arranged into lanes.

### SIMD
### SIMD.Float32x4
### SIMD.Float64x2
### SIMD.Int8x16
### SIMD.Int16x8
### SIMD.Int32x4
### SIMD.Uint8x16
### SIMD.Uint16x8
### SIMD.Uint32x4
### SIMD.Bool8x16
### SIMD.Bool16x8
### SIMD.Bool32x4
### SIMD.Bool64x2

## Structured data
These objects represent and interact with structured data buffers and data coded using JavaScript Object Notation (JSON).

### ArrayBuffer
### SharedArrayBuffer
### Atomics
### DataView
### JSON
### Control abstraction objects
### Promise
### Generator
### GeneratorFunction
### AsyncFunction
### Reflection
### Reflect
### Proxy

## Internationalization
Additions to the ECMAScript core for language-sensitive functionalities.

### Intl
### Intl.Collator
### Intl.DateTimeFormat
### Intl.NumberFormat

## WebAssembly

### WebAssembly
### WebAssembly.Module
### WebAssembly.Instance
### WebAssembly.Memory
### WebAssembly.Table
### WebAssembly.CompileError
### WebAssembly.LinkError
### WebAssembly.RuntimeError

## Statements

### Control flow
#### Block
A block statement is used to group zero or more statements. The block is delimited by a pair of curly brackets.

#### break
Terminates the current loop, switch, or label statement and transfers program control to the statement following the terminated statement.

#### continue
Terminates execution of the statements in the current iteration of the current or labeled loop, and continues execution of the loop with the next iteration.

#### Empty
An empty statement is used to provide no statement, although the JavaScript syntax would expect one.

#### if...else
Executes a statement if a specified condition is true. If the condition is false, another statement can be executed.

#### switch
Evaluates an expression, matching the expression's value to a case clause, and executes statements associated with that case.

#### throw
Throws a user-defined exception.

#### try...catch
Marks a block of statements to try, and specifies a response, should an exception be thrown.

## Declarations
### var
Declares a variable, optionally initializing it to a value.

### let
Declares a block scope local variable, optionally initializing it to a value.

### const
Declares a read-only named constant.

## Functions and classes

### function
Declares a function with the specified parameters.

### function*
Generator Functions enable writing iterators more easily.

### async function
Declares an async function with the specified parameters.

### return
Specifies the value to be returned by a function.

### class
Declares a class.

## Iterations

### do...while
Creates a loop that executes a specified statement until the test condition evaluates to false. The condition is evaluated after executing the statement, resulting in the specified statement executing at least once.

### for
Creates a loop that consists of three optional expressions, enclosed in parentheses and separated by semicolons, followed by a statement executed in the loop.

### for each...in
Iterates a specified variable over all values of object's properties. For each distinct property, a specified statement is executed.

### for...in
Iterates over the enumerable properties of an object, in arbitrary order. For each distinct property, statements can be executed.

### for...of
Iterates over iterable objects (including arrays, array-like objects, iterators and generators), invoking a custom iteration hook with statements to be executed for the value of each distinct property.

### while
Creates a loop that executes a specified statement as long as the test condition evaluates to true. The condition is evaluated before executing the statement.

## Others

### debugger
Invokes any available debugging functionality. If no debugging functionality is available, this statement has no effect.

### export
Used to export functions to make them available for imports in external modules, another scripts.

### import
Used to import functions exported from an external module, another script.

### label
Provides a statement with an identifier that you can refer to using a break or continue statement.

### with
Extends the scope chain for a statement.

## Expressions and operators

### Primary expressions
Basic keywords and general expressions in JavaScript.

#### this
The this keyword refers to the function's execution context.

#### function
The function keyword defines a function expression.

#### class
The class keyword defines a class expression.

#### function*
The function* keyword defines a generator function expression.

#### yield
Pause and resume a generator function.

#### yield*
Delegate to another generator function or iterable object.

#### async function*
The async function defines an async function expression.

#### await
Pause and resume an async function and wait for the promise's resolution/rejection.

#### []
Array initializer/literal syntax.

#### {}
Object initializer/literal syntax.

#### /ab+c/i
Regular expression literal syntax.

#### ( )
 Grouping operator.

## Left-hand-side expressions
Left values are the destination of an assignment.

### Property accessors
Member operators provide access to a property or method of an object
(object.property and object["property"]).

### new
The new operator creates an instance of a constructor.

### new.target
In constructors, new.target refers to the constructor that was invoked by new.

### super
The super keyword calls the parent constructor.

### ...obj
Spread syntax allows an expression to be expanded in places where multiple arguments (for function calls) or multiple elements (for array literals) are expected.

## Increment and decrement
Postfix/prefix increment and postfix/prefix decrement operators.

### A++
Postfix increment operator.

### A--
Postfix decrement operator.

### ++A
Prefix increment operator.

### --A
Prefix decrement operator.

## Unary operators
A unary operation is operation with only one operand.

### delete
The delete operator deletes a property from an object.

### void
The void operator discards an expression's return value.

### typeof
The typeof operator determines the type of a given object.

### +
The unary plus operator converts its operand to Number type.

### -
The unary negation operator converts its operand to Number type and then negates it.

### ~
Bitwise NOT operator.

### !
Logical NOT operator.

## Arithmetic operators
Arithmetic operators take numerical values (either literals or variables) as their operands and return a single numerical value.

### +
Addition operator.

### -
Subtraction operator.

### /
Division operator.

### *
Multiplication operator.

### %
Remainder operator.

### **
Exponentiation operator.

## Relational operators
A comparison operator compares its operands and returns a Boolean value based on whether the comparison is true.

### in
The in operator determines whether an object has a given property.

### instanceof
The instanceof operator determines whether an object is an instance of another object.

### <
Less than operator.

### >
Greater than operator.

### <=
Less than or equal operator.

### >=
Greater than or equal operator.

- Note: => is not an operator, but the notation for Arrow functions.

## Equality operators
The result of evaluating an equality operator is always of type Boolean based on whether the comparison is true.

### ==
Equality operator.

### !=
Inequality operator.

### ===
Identity operator.

### !==
Nonidentity operator.

## Bitwise shift operators
Operations to shift all bits of the operand.

### <<
Bitwise left shift operator.

### >>
Bitwise right shift operator.

### >>>
Bitwise unsigned right shift operator.

## Binary bitwise operators
Bitwise operators treat their operands as a set of 32 bits (zeros and ones) and return standard JavaScript numerical values.

### &
Bitwise AND.

### |
Bitwise OR.

### ^
Bitwise XOR.

## Binary logical operators
Logical operators are typically used with boolean (logical) values, and when they are, they return a boolean value.

### &&
Logical AND.

### ||
Logical OR.

## Conditional (ternary) operator
(condition ? ifTrue : ifFalse)
The conditional operator returns one of two values based on the logical value of the condition.

## Assignment operators
An assignment operator assigns a value to its left operand based on the value of its right operand.

### =
Assignment operator.

### *=
Multiplication assignment.

### /=
Division assignment.

### %=
Remainder assignment.

### +=
Addition assignment.

### -=
Subtraction assignment

### <<=
Left shift assignment.

### >>=
Right shift assignment.

### >>>=
Unsigned right shift assignment.

### &=
Bitwise AND assignment.

### ^=
Bitwise XOR assignment.

### |=
Bitwise OR assignment.

### [a, b] = [1, 2]
{a, b} = {a:1, b:2}
Destructuring assignment allows you to assign the properties of an array or object to variables using syntax that looks similar to array or object literals.

## Comma operator
### ,
The comma operator allows multiple expressions to be evaluated in a single statement and returns the result of the last expression.

## Non-standard features
### Legacy generator function
The function keyword can be used to define a legacy generator function inside an expression. To make the function a legacy generator, the function body should contains at least one yield expression.

### Expression closures
The expression closure syntax is a shorthand for writing simple function.

### [for (x of y) x]
Array comprehensions.

### (for (x of y) y)
Generator comprehensions.

## Functions
This chapter documents how to work with JavaScript functions to develop your applications.

### arguments
### Arrow functions
### Default parameters
### Rest parameters
### Additional reference pages
### Lexical grammar
### Data types and data structures
### Strict mode
