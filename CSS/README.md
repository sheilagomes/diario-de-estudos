# CSS

![Logo do CSS](https://github.com/sheilagomes/diario-de-estudos/blob/main/CSS/css-logo.png)

## Dicas gerais
* Comentários no CSS: `/* para uma ou mais linhas */`
* No grid-template-areas não pode usar só números para definir cada área:
```
grid-template-areas:
    '1st 2nd 3rd' 
    '4th 5th 6th'
    '7th 8th 9th';
```
* Para posicionar elementos iguais de forma a ocupar o espaço inerno de um contêiner, usar flex-wrap:
```
.dice {
    width: 90px;
    height: 90px;
    border-radius: 10px;
    background-color: #EFE5DC;
    margin: 100px;
    display: flex;
    flex-wrap: wrap;
}

.dice div {
    width: 20px;
    height: 20px;
    margin: 5px;
}
```
* Para fazer imagens caberem em um espaço específico cortando o tamanho em excesso usamos `object-fit: cover;`
* Para tirar o cabeçalho em uma única página do WP:
```
.page-id-5161 .site-header {
   display: none !important;`
}
```
* Para distribuir elementos com espaço ao redor deles: `justify-content: space-around;`
* Para distribuir elementos com espaço entre deles e sem margem dos lados: `justify-content: space-between;`
* Para alinhar elementos verticalmente:
```
display: flex;
flex-direction: column;
align-items: center;
```
* Para incluir Google fonts pelo CSS:
`@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600&display=swap');`
* Para fazer o cursor virar 'mão' igual à quando está apontando um link:
`cursor: pointer;`
* A opacidade varia de transparente (0) a opaca(1).
* Para transições suaves em galerias: `transition: transform 0.25s ease;`
* Para usar grid com linhas (primeiros valores antes da barra) e colunas:
```
display: grid;
grid-template: repeat(2, 50px) / repeat(3, 1fr); /* 2 linhas, 3 colunas */
```
* Para colocar espaço entre elementos do grid: `grid-gap: 3px;`
* Como declarar e usar variáveis no CSS:
```
:root {
  --note-color-1: lightblue;
}

.color1 {
    color: var(--note-color-1);
}
```
* Para fazer vários elementos se ajustarem à tela. O `auto-fit` coloca os elementos e o `minmax` determina a menor e maior largura (o `1fr` faz com que o elemento estique até caber)):
`grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));`
* Ao usar o `auto-fit`, as linhas extras criadas em telas menores são implícitas e não seguem os tamanhos determinados para as linhas em telas maiores. Pra resolver isso:
`grid-auto-rows: 100px;`
* Para fazer elementos de tamanhos diferentes ocuparem o espaço disponível na tela sem perder a responsividade, criamos classes para determinar o espaço que cada elemento ocupará e depois usamos `grid-auto-flow: dense`, que cria independência da ordem da origem (HTML) dos elementos:
```
.container {
    display: grid;
    grid-gap: 5px;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
    grid-auto-rows: 75px;
    grid-auto-flow: dense;
}

.horizontal {
    grid-column: span 2;
}

.vertical {
    grid-row: span 2;
}

.big {
    grid-column: span 2;
    grid-row: span 2;
}
```
* Outra forma de distribuir conteúdo é usar linhas nomeadas, no caso, as linhas que limitam o retângulo que contém cada conteúdo. Mas é preciso prestar atenção nas linhas que limitam topo, base, esquerda e direita:
```
.container {
    height: 100%; 
    display: grid;
    grid-gap: 3px;
    grid-template-columns: [main-start] 1fr [content-start] 5fr [content-end main-end];
    grid-template-rows: [main-start] 40px [content-start] auto [content-end] 40px [main-end]; 
}

.header {
    grid-column: main;
}

.menu {}

.content {
    grid-area: content;
}

.footer {
    grid-column: main;
}
```
* No grid, `justify-content` alinha o conteúdo inteiro de um div em relação às linhas, e `align-content`, em relação às colunas.
* Para distribuir conteúdo de forma equidistante entre os elementos e os limites laterais, usamos `justify-content: space-evenly`. A diferença entre ele e o `justify-content: space-around` é que o segundo usa só a metade do espaço disponível nas laterais.
* Outras formas de distribuir o conteúdo interno de elementos são `justify-items`, `align-items`, `justify-self` e `align-self`, os primeiros para todos os elementos, os últimos, para elementos indiviuais:
```
.container {
    height: 100%; 
    display: grid;
    grid-gap: 3px;
    grid-template-columns: repeat(12, 1fr);
    grid-template-rows: 40px auto 40px;
    //justify-items: center;
    //align-items: center;
}

.content {
    grid-column: 3 / -1;
 //   justify-self: center;
 //   align-self: end;
}
```
* A diferença entre `auto-fit` e `auto-fill` é que o primeiro vai esticar os elementos mesmo em telas maiores, e o segundo vai manter o tamanho especificado em `minmax` depois que todos os elementos estiverem alinhados.
* É possível usar flexbox e grid simultaneamente, sempre lembrando que o primeiro trabalha de forma unidimensional, e o segundo, de forma bidimensional.
* Flexbox é content-first e grid, layout-first.
* Uma forma de posicionar elementos na extremidade direita (nesse caso, o terceiro elemento dentro um div):
```
.flexbox-header > div:nth-child(3) {
    margin-left: auto;
}
```
[Markdown](https://guides.github.com/features/mastering-markdown/) / [ResizeImage](https://resizeimage.net/)