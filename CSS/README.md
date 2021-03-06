# CSS

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
* Outras formas de distribuir o conteúdo interno de elementos são `justify-items`, `align-items`, `justify-self` e `align-self`, os primeiros para todos os elementos, os últimos, para elementos individuais:
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
* A diferença entre `auto-fit` e `auto-fill` é que o primeiro vai esticar os elementos mesmo em telas maiores, e o segundo vai manter o tamanho especificado em `minmax` depois que todos os elementos estiverem alinhados:
```
.wrapper {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
}
```
* É possível usar flexbox e grid simultaneamente, sempre lembrando que o primeiro trabalha de forma unidimensional, e o segundo, de forma bidimensional.
* Flexbox prioriza o conteúdo, e grid, o layout.
* Uma forma de posicionar elementos na extremidade direita (nesse caso, o terceiro elemento dentro um div):
```
.flexbox-header > div:nth-child(3) {
    margin-left: auto;
}
```
* Uma forma de fazer o rodapé grudar na base da tela é tornar o corpo um elemento flexível verticalmente. Em seguida, criamos a altura mínima com base na janela de visualização. A propriedade força o bloco de conteúdo a ocupar o espaço entre o conteúdo e o rodapé:
```
HTML:
<div class="content">
  Content goes here
</div>
<footer>
  I'm a sticky footer
</footer>

CSS:
body {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
.content {
  flex: 1 0 auto;
}
```
* Outra forma de fazer o rodapé grudar na base da tela é usar o grid, criando 2 linhas no corpo e assim o conteúdo expande o quanto precisar ou puder preencher, e como o rodapé é automático, assume o tamanho do texto determinado no html:
```
HTML:
<div class="content">
  Content goes here
</div>
<footer>
  I'm a sticky footer
</footer>

CSS:
body {
  display: grid;
  grid-template-rows: 1fr auto;
  min-height: 100vh;
}
```
* Para inverter uma imagem horizontalmente:
`transform: scaleX(-1);`
* [Pseudo-elementos](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) são usados para alterar uma parte de um elemento, sempre começarm com :: e estes são alguns deles:
```
    ::first-line
    ::first-letter
    ::before
    ::after
    ::selection
```
* [Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) são usadas para definir estados de elementos, como links, que podem ter estados como ativo, visitado ou sob o ponteiro. Por exemplo, para tirar o sublinhado dos links:
```
a:link {
  text-decoration: none;
}
```
* Ao definir o estilo para vários estados de link, esta ordem deve ser seguida: `a:link, a:visited, a:hover, a:active`
* Para centralizar elementos horizontal e verticalmente:
```
display: flex;
flex-direction: column;
justify-content: center;
align-content: center;
```
* Para afetar elementos descendentes, usar um espaço entre ascendente e descendente:
```
li a {
  color: red;
}
```
* Usar `+` para selecionar elementos adjacentes, mas não descendentes: `h2 + button` (neste caso, os primeiros botões em seguida de todos os h2)
* Para selecionar um descendente direto usar `>`, como no exemplo: `footer > a` (outros descendentes em níveis mais internos não serão selecionados)
* Para selecionar por atributo, usar `[]`, por exemplo: `input[text="pos"]` para selecionar todos os `input` do tipo texto equivalentes a `pos`
* Usando pseudo-classes, para selecionar elementos específicos por posição, somente a primeira ocorrência da terceira posição: `post:nth-of-type(3)`. E para selecionar todas as ocorrências a cada 2, ou seja, um sim, um não: `post:nth-of-type(2n)`
* Pra fazer um tabuleiro de xadrez com quadrados definidos por divs e css: 
```
square {
  background-color: black;
}
square:nth-of-type(2n) {
  background-color: white;
}
```
* A ordem de [especificidade](https://specificity.keegan.st/) é id > classes, atributos e pseudo-classes > elementos e pseudo-elementos, mas estilos em linha são mais específicos ainda, e seu uso não é recomendado: `<p style="color: blue;">azul</p>`
* A propriedade `inherit` é usada para herdar os estilos superiores da ordem de ocorrência e especificidade, mas nem todos os elementos aceitam
* Para a borda não ultrapassar o tamanho do elemento em que está, colocar na tag `html`: `box-sizing: border-box;`
* Ao usar `em` como medida, em vez de `px`, os elementos se ajustam aos elementos ascendentes. Já o `rem` (root em) se baseia na medida do documento como um todo, o que pode ser alterado com a tag `html` no css.
* Três formas de usar transparência: `color: rgba(0, 209, 112, 0.5)`, `opacity: 0.5` e `color: #657890ff`
* [Transições](https://easings.net/) usam o nome de uma propriedade, a duração, tempo e atraso.
* [Transformações](https://developer.mozilla.org/pt-BR/docs/Web/CSS/transform) podem variar entre posição, rotação e inclinação e podem ser aplicados a seções interiores ou elementos individuais.
* Para criar sites responsivos mobile-first:
```
@media only screen and (min-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```
* Para fazer cálculos no css: 
```
img { 
  width: 30%;
  margin: calc(10%/6);
}
* Lembrar que, ao usar flexbox, ele funciona por eixos (principal e perpendicular) e que quando se inverte a direção dos elementos com algum comando, os eixos tabém mudam.
```
* Uma forma de criar bordas sem usar `border` e sem usar espaço extra ou deslocar outros elementos é:
```
img {
  outline: 3px solid lime;
  outline-offset: -1.5em; /* cria borda interna*/
}
```
* É possível desativar o `outline` que o navegador usa para indicar o elemento ativo, para que não fique um retângulo destacando elementos com outros formatos, mas é uma boa ideia ativar outra forma de indicar o elemento ativo, como um `background` diferente, por ex.
* Normalmente `outline` não tem suporte em navegadores para controlar cantos da mesma forma que `border-radius`, exceto o Firefox, que tem uma propriedade não padronizada para isso: `-moz-outline-radius`
* Uma forma de tentar resolver problemas com rolagem horizontal indesejada é identificar oq ue causa a rolagem, usando:
```
* {
  outline: 3px solid red; /* contorna todos os elementos sem deslocá-los */
}
```
* Uma forma de criar um contorno visual transparente que não afeta o resto do site:
`outline: 50px solid rgba(0, 0, 0, .5);` Outra forma é usar box-shadow: `box-shadow: 0 0 0 50px rgba(0, 0, 0, .5);`
* Variáveis podem ser declaradas em qualquer parte do documento, mas a ideia de fazer isso no `:root` é que elas possam ser usadas de forma global.
* Uma boa forma de usar variáveis é redefini-las em media queries para criar responsividade.
* Para usar um fundo e uma cor:
```
body {
  background: black url(//unsplash.it/100/100) no-repeat;
}
```
* Para ter fundo com duas imagens misturadas:
```
body {
  height: 100vh;
  background-image: linear-gradient(45deg, red, blue), url(//unsplash.it/1200/600);
  background-size: cover;
  background-blend-mode: multiply;
}
```
* Para definir `align-items` e `justify-items` ao mesmo tempo, usar `place-items: <align-items> / <justify-items>`
* Abreviação para grid de imagens sem intervalo entre elas:
```
#projects {
  display: grid;
  grid: auto / repeat(auto-fit, minmax(300px, 1fr));
}
```
* Para eliminar os efeitos de animação em criações mobile-first ao fazer o media query é possível usar `all: unset` e todos os efeitos são removidos
* Para iniciar o CSS eliminando margens internas e externas:
```
 {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```
* Para alterar o estilo dos placeholders:
```
::placeholder {
  color: blue;
  font-size: 1.5em;
}
```
* A diferença de usar `width: auto` e `width 100%` é que a primeira opção distribui o espaço igualmente sem ultrapassar a largura da tela, enquanto que a segunda, se houver margens definidas, por exemplo, fará aparecer uma barra de rolagem horizontal.
* Para definir `font-size` é melhor usar `rem`, que normalmente equivale a `16px`. Um jeito de ter mais controle sobre o tamanho de fontes `rem` é definir: 
```
html {
  font-size: 62.5%;
}

body {
  font-size: 2.1rem; /* equivale a 21px */
}
```

## Dicas gerais de design
* Prestar atenção à largura das linhas, o dieal é não passar de 70-75 caracteres, dá até para usar a `ch` como unidade de medida para isso, que equivale à largura do 0 da fonte em questão.
* Deve haver espaço entre os elementos, para deixar as coisas respirarem.
* Usar contraste com cores, mesmo que sejam de uma paleta em tons de cinza, ajuda a tornar tudo mais visualmente agradável.
* Evitar usar texto justificado ajuda a não ter espaços em branco esquisitos.
* Usar contraste com propriedades de fontes como `font-weight`.
* Usar `width` e `max-width` é sempre uma boa ideia para ter mais controle sobre o efeito final em diferentes tamanhos de tela.
* De for preciso declarar uma altura, é melhor usar `min-height`ara evitar surpresas como conteúdo que ultrapassa os limites do elementos em tamanhos de tela diferentes.
* A escolha entre usar `em` ou `rem` para o `padding` e `margin` de certos elementos pode depender do elemento (para botões é melhor `em`, por ex., porque eles crecse proporcionalmente ao taamnho do texto)
* Uma boa forma de "secar" o código CSS é usar o pseudo-elemento `:is`:
```
/* em vez de
header h1,
header a,
header .btn,
header small) {
  color: green;
}, usar:*/

header :is(h1, :a, .btn, small) {
  color: green;
}

/* em vez de 
header p:hover, 
.card p:hover {
  color: red;
} usar: */

:is(header, .card) p:hover {
  color: red;
}

/* em vez de 
.card .title, 
.card p a) {
  color: red;
} usar: */

.card :is(.title, p a) {
  color: red;
}
```

## Referências
* [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
* [Color names](https://htmlcolorcodes.com/color-names/)
* [Color picker](https://htmlcolorcodes.com/color-picker/)
* [Extrator de cores de imagens](http://colormind.io/)
* [CSS fonts](https://www.cssfontstack.com/)
* [Coolors Color Palette](https://coolors.co/palettes/trending)
* [Media Queries Breakpoints For Responsive Design In 2021](https://devfacts.com/media-queries-breakpoints-2021/)
* [CSS Tools: Reset CSS](https://meyerweb.com/eric/tools/css/reset/)
* [CSS backgrounds](https://www.kevinpowell.co/article/im-always-surprised-more-people-dont-know-about-this)

[Markdown](https://guides.github.com/features/mastering-markdown/) / [ResizeImage](https://resizeimage.net/)