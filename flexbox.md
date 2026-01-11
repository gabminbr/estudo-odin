# Flexbox
## Definição
- é uma forma em que você organiza os itens em colunas ou linhas e esses itens vão aumentar conforme você define, exemplo básico:
```html
<div class="flex-container">
  <div class="one"></div>
  <div class="two"></div>
  <div class="three"></div>
</div>
```
```css
.flex-container {
  display: flex;
}

/* this selector selects all divs inside of .flex-container */
.flex-container div {
  background: peachpuff;
  border: 4px solid brown;
  height: 100px;
  flex: 1;
}
```
- por padrão como se observa, os flex itens vão se arranjar horizontalmente, a medida q for adicionando mais divs dentro do flex container, vai aumentando o numero de flex itens e ele vai se rearrajar automaticamente
- formalmente, flex-container é tudo que tem como atributo o *display:flex* enquanto um flex item é toda div dentro de um flex container, mas um flex item também pode ser um flex container, podendo dividir infinitamente
