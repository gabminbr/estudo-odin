# JavaScript
- no html, para inserir um bloco de javascript, usamos a tag *<script>* ***texto*** *</script>*.
- podemos incluir o arquivo igual fazemos com o css também, externamente:
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <script src="javascript.js"></script>
    </head>
</html>
```
## User's Input
- *prompt(message, default)*: sendo *message* o que irá aparecer para o usuario no console, e default o valor que vai retornar por padrao caso nada seja colocado, vai retornar a string colocada no input.
## Sintaxe
### variaveis
- declaramos variaveis usando a palavra *let*:
```javascript
    let firstName = "John";
    let age = 10;
    console.log(firstName);
    console.log(age);
```
- para constantes, usamos *const*:
```javascript
    const pi = 3.14;
    pi = 10;
    console.log(pi);
```
- o exemplo acima vai dar erro, pois não podemos fazer uma mudança de valores de constantes.
#### Strings formatadas
- podemos usar algo parecido com o python:
```javascript
    let name = "John";
    console.log(`Olá, ${name}`);
```
- como vemos, para usar esse, é necessário usar o símbolo de crase.
- podemos também fazer algo assim:
```javascript
    let name = "John";
    console.log("Olá, %s!", name);
```
**- atenção: NÃO EXISTE CHAR EM JAVASCRIPT**
- podemos usar caracteres de escape para usar aspas dentro da string
```javascript
    let greeting = "Olá \"senhor\" Adam.";
```
- lembre-se: ***STRINGS SÃO IMUTÁVEIS!!!!***.
#### Boolean
- true e false
### condicionais
- diferença entre "===" e "==":
  o '==': converte o tipo dos valores e compara o valor, exemplo, 5 == '5' retorna true.
  já '===': não converte, retorna falso quando compara 5 === '5'.
- ternário: condition ? run this code : run this code instead
### Funções
- funções em javascript são padroes, usamos a palavra reservada ***function***:
```javascript
function favoriteAnimal(animal) {
    return animal + " is my favorite animal!"
}

const message = favoriteAnimal('Goat')
console.log(message)
```
- podemos dar valores "default" em parametros de funções, por padrao, se por exemplo, a funcao showMessage(from, to) usa showMessage("Anna"); o valor de to vira o data type undefined, entretanto, podemos dar um valor default pra ele caso nao receba nada:
```javascript
function showMessage(from, to = "no text given") {
    console.log(from + ": " + to);
}

showMessage("Anna", "Tomas"); // output: Anna: Tomas
showMessage("Tomas"); // output: Tomas: no text given
```
- quando a função não retorna nada ou retorna apenas com um **return**, ele retorna na verdade void / undefined.
#### Function Expressions
- existe também outro jeito de declarar funções, meio que criando variaveis:
```javascript
let sayHi = function() {
    alert("olaa);
};
```
- a função acima vai funcionar normalmente ao chamarmos com um sayHi().
- lembre-se que funções são também valores, não importa se foi criado usando a sintaxe padrao ou por function expression, entao se criarmos sayHi do jeito padrao e chamar apenas ***sayHi*** sem parenteses, vai retornar a escrita da funcao.
- diferença entre declaracao de funcao e expressao de funcao: basicamente, a expressao de funcao vai criar a funcao no exato momento que a linha executar o "let func = function....", e só é usavel se for chamada **a partir** desse momento, já a declaracao nao, pois podemos chamar ela antes da declaracao, pois o javascript primeiro busca as declaracoes de funcoes e executa todas elas e só assim comeca a execucao do codigo.
- outro ponto tambem, é que as funcoes q sao declaradas e nao expressadas como variaveis, se sao criadas dentro de blocos como um if else, so pode ser acessada dentro daquele escopo, fora dele não.
### Loops 
- loop *for(...; ....; ...)*:
```javascript
for (let i = 0; i < 10; i++) {
    console.log(i);
}
```
- loop *for..of*:
```javascript
const nomes = ['Diego', 'Julio', 'Andrew', 'Jolise'];
for(const nome of nomes) {
    console.log(nome);
}
```
- é o equivalente a:
```javascript
const nomes = ['Diego', 'Julio', 'Andrew', 'Jolise'];
for(let i = 0; i < nomes.length; i++) {
    console.log(nomes[i]);
}
```
### Arrays
#### declaração
- exemplo:
```javascript
let arr = new Array();
let arr = [];
```
- importante, arrays em javascript aceitam qualquer tipo de dados, pode ter um array com string, int, etc.
- para criar matrizes:
```javascript
let matriz = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];
```
#### map method
- é uma função que espera como argumento um callback, basicamente uma função que espera como argumento outra função:
```javascript
function addOne(num) {
  return num + 1;
}
const arr = [1, 2, 3, 4, 5];
const mappedArr = arr.map(addOne);
console.log(mappedArr); // Outputs [2, 3, 4, 5, 6]
```
- ele retorna um novo array após ter iterado sobre todos os elementos do array e aplicado a funçao que foi passada como argumento
#### filter method
- vai funcionar de forma parecida, entretanto, é uma função apenas para filtrar o array de acordo com uma funcao que retorna true ou false
```javascript
function isOdd(num) {
  return num % 2 !== 0;
}
const arr = [1, 2, 3, 4, 5];
const oddNums = arr.filter(isOdd);
console.log(oddNums); // Outputs [1, 3, 5];
console.log(arr); // Outputs [1, 2, 3, 4, 5], original array is not affected
```
#### reduce method
- usa 2 parametros, o primeiro sendo a callback function e o segundo (opcional) o valor inicial, e a callback function por sua vez recebe 2 parametros, o primeiro sendo o acumulador que é o valor que vai sendo agregado a cada iteração, e o valor atual.
- o segundo parametro é opcional, porem, se nao for colocado, por padrao pega o 1 valor do array
```javascript
const arr = [1, 2, 3, 4, 5];
const productOfAllNums = arr.reduce((total, currentItem) => {
  return total * currentItem;
}, 1);
console.log(productOfAllNums); // Outputs 120;
console.log(arr); // Outputs [1, 2, 3, 4, 5]
```
## DOM Manipulation
### query selectors
- element.querySelector(selector): retorna a referencia ao primeiro 'match' do selector
- element.querySelectorAll(selectors): returns a “NodeList” containing references to all of the matches of the selectors.
### element creation
- document.createElement(tagName, [options]): creates a new element of tag type tagName. [options] in this case means you can add some optional parameters to the function.
### append elements
- parentNode.appendChild(childNode) - appends childNode as the last child of parentNode.
- parentNode.insertBefore(newNode, referenceNode) - inserts newNode into parentNode before referenceNode.
### remove element
- parentNode.removeChild(child) - removes child from parentNode on the DOM and returns a reference to child.
### altering element
```javascript
// creates a new div referenced in the variable 'div'
const div = document.createElement("div");
```
```javascript
// adds the indicated style rule to the element in the div variable
div.style.color = "blue";

// adds several style rules
div.style.cssText = "color: blue; background: white;";

// adds several style rules
div.setAttribute("style", "color: blue; background: white;");
```
### edditing element
```javascript
// if id exists, update it to 'theDiv', else create an id with value "theDiv"
div.setAttribute("id", "theDiv");

// returns value of specified attribute, in this case "theDiv"
div.getAttribute("id");

// removes specified attribute
div.removeAttribute("id");
```
### working with classes
```javascript
// adds class "new" to your new div
div.classList.add("new");

// removes "new" class from div
div.classList.remove("new");

// if div doesn't have class "active" then add it, or if it does, then remove it
div.classList.toggle("active");
```
### OBS
- as vezes pode dar erro no js pois ele é carregado antes do html ser carregado, então para evitarmos erros se o script alterar o html, usaremos isso:
```html
<head>
  <script src="js-file.js" defer></script>
</head>
```
## Events
- existem 3 métodos para adicionar eventos no html:
- diretamente no arquivo html:
```html
<button onclick="alert('Hello World')">Click Me</button>
```
- podemos colocar no arquivo js com propriedades do tipo on<eventType>, entretanto, um elemento DOM so pode ter um on<eventType> tipo por vez.
```html
<button id="btn">Click Me</button>
```
```javascript
const btn = document.querySelector("#btn");
btn.onclick = () => alert("Hello World");
```
- o melhor método, é usando event listener:
```html
<button id="btn">Click Me Too</button>
```
```javascript
const btn = document.querySelector("#btn");
btn.addEventListener("click", () => {
    alert("Hello World");
});
```
### parameter e
```javascript
btn.addEventListener("click", function (e) {
    console.log(e);
});
```
- o que acontece nesse trecho é o seguinte: primeiro, a função *function (e)* é uma anonima, e o addEventListener sempre espera como segundo parametro uma funcao, e por padrao o argumento dessa funcao sempre será um objeto do tipo Event, e assim podemos pegar informacoes e adicionar caracteristicas.
- as informacoes por exemplo pode ser *e.target*
### colocando listeners para um grupo de nodes
```html
<div id="container">
    <button id="one">Click Me</button>
    <button id="two">Click Me</button>
    <button id="three">Click Me</button>
</div>
```
```javascript
const buttons = document.querySelectorAll("button");

buttons.forEach((button) => {
    button.addEventListener("click", () => {
        alert(button.id);
    });
});
