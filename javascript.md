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
#### Boolean
- true e false
### condicionais
- diferença entre "===" e "==":
  o '==': converte o tipo dos valores e compara o valor, exemplo, 5 == '5' retorna true.
  já '===': não converte, retorna falso quando compara 5 === '5'.
- ternário: condition ? run this code : run this code instead
