# CSS

![Logo do CSS](https://github.com/sheilagomes/diario-de-estudos/blob/main/CSS/css-logo.png)

## Dicas gerais
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
* Para distribuir elementos ocupando o espaço dentro de um contêiner: `flex-wrap: wrap;`
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
* Pra mostrar o menu de novo no Sublime, CTRL+Shift+P > Menu > View: Toggle menu
* A opacidade varia de transparente (0) a opaca(1).
* Para transições suaves em galerias: `transition: transform 0.25s ease;`

[Markdown](https://guides.github.com/features/mastering-markdown/) / [ResizeImage](https://resizeimage.net/)
