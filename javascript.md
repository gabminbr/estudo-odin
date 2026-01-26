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
