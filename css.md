# CSS
## classes
- exemplo, no nosso arquivo css:
```css
.class-example {
  background-color: red;
}
```
- no arquivo .html usaremos dessa forma:
```html
<div class="class-example">olá a todos</div>
```
- além disso, podemos usar duas ou mais classes numa mesma div, por exemplo:
```html
<div class="class-example example-class"...
```
## ID
- também temos os seletores por ID, a grande diferença entre eles e a classe, é que o por ID só pode usar um por vez na classe.
```css
#title {
  color: blue;
}
```
- no html:
```html
<div id="title">olá</div>
```
## outros
- também podemos "reaproveitar" elementos que têm o conteúdo parecido, exemplo:
```css
.read {
  color: white;
  background-color: black;
  /* several unique declarations */
}

.unread {
  color: white;
  background-color: black;
  /* several unique declarations */
}
```
- fica assim:
```css
.read,
.unread {
  color: white;
  background-color: black;
}

.read {
  // as declaracoes unicas que tem nesse seletor
}

.unread {
  // ...
}
```
- outra coisa que podemos fazer também é, se tivermos uma regra específica de css quando um elemento tem duas classes especificas:
```html
  <div class = "subsection header">blabla</div>
```
```css
  .subsection.header {
    color:purple;
  }
```
- ps: a ordem **não** importa.
- e também pode ser misturado com ID:
```css
  .subsection#private {
    //blabla
  }
```
## adicionar css no html
### externamente
- podemos adicionar apenas linkando no topo do arquivo html o arquivo de estilizacao, como no exemplo:
```html
  <head>
    <link rel="stylesheet" href="styles.css">
  </head>
```
### internamente
- podemos criar o arquivo css dentro do arquivo html também, usando do elemento *style*
```html
<head>
  <style>
    div {
      color: white;
      background-color: black;
    }

    p {
      color: red;
    }
  </style>
</head>
<body>
  ...
</body>
```
### inline
- adicionamos o css diretamente no elemento que queremos:
```html
  <body>
    <div style="color: white; background-color: black;">...</div>
  </body>
```

