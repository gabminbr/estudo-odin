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

