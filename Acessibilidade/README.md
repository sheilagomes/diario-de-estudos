# Acessibilidade

## Dicas gerais
* Acessibilidade é o processo de criação de aplicativos que podem ser usados ​​por pessoas com várias habilidades e em situações diversas.
* “A11y” é o numerônimo de “acessibilidade” em inglês.
* Acessibilidade anda de mãos dadas com usabilidade
* Sempre use um texto `alt` significativo para não confundir os leitores de tela.
* O site [Web Content Accessibility Guidelines](https://www.w3.org/WAI/WCAG21/quickref/) é uma ótima fonte de referência rápida.
* Otimize o contraste da cor, para encontrar mais informações acesse [Getstark](https://www.getstark.co/), uma das plataformas de otimização de cores para acessibilidade.
* Simplifique a linguagem, mantenha seu conteúdo sempre simples e compreensível e mantenha seu layout claro.
* Conduza os usuários, por exemplo, usando etiquetas de formulário para descrever campos de entrada e espaços reservados. Exemplos de campos de entrada aceitáveis ​​são muito úteis.
* Sempre forneça legendas para conteúdo de vídeo. Sem legendas, não faz sentido para uma pessoa com um problema visual permanente ou temporário. Nunca, jamais, faça seu vídeo começar a ser reproduzido automaticamente.
* Não se esqueça de testar a navegação do teclado. O usuário deve ter o direito de usar o teclado para navegar no site. Não podemos tirar essa vantagem deles.
* Crie botões grandes! Desta forma, fica mais claro que este é um botão clicável e que chama à uma ação.
* Crie links compreensíveis para deixar o usuário saber onde clicar e onde ir.
Use elementos HTML semânticos como `<main>`, `<nav>`, `<header>`, `<section>`, `<article>`, `<form>`
* Use funções de referência [ARIA](https://www.w3.org/TR/wai-aria-practices/examples/landmarks/main.html) para adicionar contexto aos elementos HTML. Mas apenas se você já não está usando HTML semântico, que fornece a leitores de tela o mesmo tipo de informação que as funções ARIA.
* [A11Y Project](https://www.a11yproject.com/) é um checklist de acessibilidade para iniciantes.
* WAI-ARIA: Web Accessibility Initiative - Accessible Rich Internet Applications
* Uma forma de usar etiquetas aria para resolver um efeito de escrita de máquina de escrever feito em JS:
```
<h1 id="typewriter-effect" aria-label="Developer, designer and coffee addict">
  <span id="text" aria-hidden="true"></span>
</h1>
```
* Se estiver usando um ícone de hambúrguer do FontAwesome, Bootstrap ou uma imagem, use os atributos aria-label e aria-hidden para fornecer alternativas aos leitores de tela:
```
<a href="#" aria-label="Collapse or expand the menu">
  <i class="fas fa-bars" aria-hidden="true"></i>
</a>
```

## Podcasts
* [Web accessibility](https://github.com/ladybug-podcast/ladybug-website/blob/master/transcripts/53-accessibility.md)

## Artigos
* [11 Golden Rules for A11Y](https://dev.to/ezgihendrickx/11-golden-rules-for-a11y-146c)
* [The best web accessibility tools for developers in 2021](https://dev.to/jaketracey/the-best-web-accessibility-tools-for-developers-in-2021-8c8)
* [The problem with the "typewriter” effect and how to fix it](
https://dev.to/savvasstephnds/the-problem-with-the-typewriter-effect-and-how-to-fix-it-2731)
* [The problem with the hamburger menu and how to fix it](
https://dev.to/savvasstephnds/your-hamburger-menu-button-is-inaccessible-here-s-how-to-fix-it-7n)
* [The problem with autocomplete and how to fix it](https://dev.to/savvasstephnds/the-problem-with-autocomplete-and-how-to-fix-it-2ill)

## Twitter
* [Wendy Fox](https://twitter.com/drwendyfox)

## Referências
* [Web Content Accessibility Guidelines](https://www.w3.org/WAI/standards-guidelines/wcag/)
* [Introduction to Web Accessibility](https://www.edx.org/course/web-accessibility-introduction)
* [Web Accessibility](https://www.webaccessibility.com/)
* [Accessibility - Mozilla](https://developer.mozilla.org/en-US/docs/Web/Accessibility)
* [Smashing magazine](https://www.smashingmagazine.com/category/accessibility)
* [CSS tricks](https://css-tricks.com/tag/accessibility/)

[Markdown](https://guides.github.com/features/mastering-markdown/) / [ResizeImage](https://resizeimage.net/)
