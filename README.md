# Quick knowledge 


Repositório contendo estudos de sobre javascript e suas abstrações. Estruturas de dados e algoritmos complementáres.

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
