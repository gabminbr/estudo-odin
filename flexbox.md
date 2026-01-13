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

## Flexbox properties
- flex: esse atributo na verdade é um atalho (obs: esse atributo é posto dentro do **flex item**) para 3 atributos flex, que são:
- flex-grow: basicamente como o nome diz, ele vai dizer o quanto aquele flex item vai crescer em relação aos outros, se por exemplo, um flex container tem 3 itens, e cada item tem o *flex-grow: 1*, vai sair o container todo dividido igualmente, entretanto, se um tiver 2, ele vai ser o dobro em relacao aos outros 
- flex-shrink: como o nome diz, encolhimento, funciona parecido com o grow, ele só acaba sendo utilizado se o tamanho dos flex itens somado é maior do que o tamanho do flex container, se não quer que o item encolha, coloque o *flex-shrink: 0*
- flex-basis: ele seta o tamanho inicial de um flex item, pode ser confundido com o width, entretanto, ele vai ser o width ou height dependendo da direcao que está o flex container, se estiver coluna por exemplo, o flex basis vai definir a altura do item, nao a largura, por padrao, ele vem como auto, pois diz para o navegador "Olhe para o meu conteúdo ou para o meu width para saber meu tamanho inicial". Ao usar o 0 como parametro, o que acontece é que ele ignora o tamanho dado pelo width e comeca do 0 e distribui o valor igualmente
- por padrão, se fizermos *flex: 1*, o atalho na verdade é para *flex: 1 1 0%*, 1 para grow 1 para shrink e 0 para basis

