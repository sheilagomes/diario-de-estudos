# HTML

## Dicas gerais
* Comentários no html: `<!-- Um comentário -->`
* Font Awesome dentro do head: `<script src="https://kit.fontawesome.com/ef442ab3a4.js" crossorigin="anonymous"></script>`
* Inverter horizontalmente ícones do Font Awesome: `<i class="far fa-star-half fa-flip-horizontal"></i>`
* [Entidades HTML](https://dev.w3.org/html5/html-author/charref) começam com `&` e terminam com `;`. São usadas ​​para exibir caracteres reservados, que normalmente seriam inválidos, ou no lugar de caracteres difíceis de digitar: `&#9824; <!-- naipe de espadas -->`
* Para criar tabelas:
```
<table> 
    <thead> <!-- Cabeçalho -->
        <tr>
            <th rowspan="2">Animal</th> <!-- ocupa duas linha -->
            <th colspan="2">Average Mass</th> <!-- ocupa duas colunas para aninhar -->
        </tr>
        <tr>
            <th>kg</th> <!-- aninhado na coluna acima -->
            <th>lb</th> <!-- aninhado na coluna acima -->
        </tr>
    </thead>
    <tbody> <!-- Corpo -->
        <tr> <!-- linha de conteúdo -->
            <td>Ostrich</td>
            <td>104</td>
            <td>230</td>
        </tr>
    </tbody>
</table>
```
* Em formulários, o padrão para `button` é a ação `submit`, se quiser um botão inativo, definir como `type="button"`
* O atributo `name` serve para enviar os dados do formulário ao servidor, de acordo com a ação determinada pelo formulário. É o que aparece na barra do navegador depois de apertar no botão de envio, no final do endereço: `?username=Sheila&age=49`
* As funções de cada atributo no input são: `id` para conectar ao label, `name` para o valor a enviar ao servidor, `placeholder` para imprimir texto de ajuda, `value` para determinar o valor dentro de um conjunto de escolhas
```
<label for="first">First name</label>
<input type="text" name="first" id="first" placeholder="Type your first name">
<input type="radio" name="race" id="fun" value="fun">
<label for="fun">Fun Run 5k</label><br>
<input type="radio" name="race" id="half" value="half">
<label for="half">Half Marathon</label><br>
```
* Existem várias [validações](https://developer.mozilla.org/pt-BR/docs/Web/Guide/HTML/Forms/Form_validation) que podem ser incluídas no código em formulários, além de poder exigir o preenchimento de campos específicos em padrões determinados. Alguns padrões básicos são especificados pelo tipo, como `email` ou `url`.
* Curiosidade extra: as extensões de urls que contêm `?utm...` significam Urchin Tracking Module e são variáveis personalizados do Google Analytics para rastreamento padrão de tráfego. São cinco: fonte da campanha (utm_source), meio da campanha (utm_medium), nome da campanha (utm_campaign), termo da campanha (utm_term) e conteúdo da campanha (utm_content). Os atributos são sempre usado sem parênteses: `https://example.com/?utm_source=facebook&utm_medium=cpc&utm_campaign=spring+sale&utm_term=green+cta&utm_content=lifestyle+image`
* Um jeito de mostrar informações extras em alguma parte do html que sejam acessíveis ao usuário é usar a tag `detail`:
```
<details>
     <summary>Click Here to get the user details</summary>
         <table>
                <tr>
                    <th>#</th>
                    <th>Name</th>
                    <th>Location</th>
                    <th>Job</th>
                </tr>
                <tr>
                    <td>1</td>
                    <td>Adam</td>
                    <td>Huston</td>
                    <td>UI/UX</td>
                </tr>
          </table>
  </details>
```

## Artigos
* [10 useful HTML5 features, you may not be using](https://blog.greenroots.info/10-useful-html5-features-you-may-not-be-using-ckdua7ql300l1m3s1ez7teshc)

## Referências
* [MDN HTML elements references](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

[Markdown](https://guides.github.com/features/mastering-markdown/) / [ResizeImage](https://resizeimage.net/)
