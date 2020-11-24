# Python

![Logo do python](https://github.com/sheilagomes/diario-de-estudos/blob/main/Python/python-logo.png)

[Documentação oficial](https://docs.python.org/3/)

## Dicas da linguagem
* Nomes de variáveis devem seguir estas regras: (1) devem começar com letra ou sublinhado, (2) o resto do nome deve ter letras, número e sublinhados, (3) diferenciam maiúsculas de minúsculas
- Convenções de nomeação no Python:
  - (1) variáveis seguem caso cobra: `snake_case`
  - (2) a maioria dos nomes de variáveis deve ser em minúsculas, exceto por constantes que devem ser maiúsculas e caso camelo maiúsculo para nomes de classes: `UpperCamelCase`
  - (3) variáveis que começam e terminam com dois sublinhados (dunder ou double underscore) são privadas: `__intocavel__`
* Python tem tipagem dinâmica (e não estática, como o Java), ou seja, aceita atribuição de valores diferentes dinamicamente
* Ao usar aspas para delcarar strings, tanto faz usar simples ou dupla , mas é preciso manter o padrão depois de escolher uma delas:
```
d = 'simples'
d = "dupla"
```
* O caracter de escape `\x` permite declarar valores hexadecimais: `hexa = "\x41" # a`
* A concatenação de strings funciona igual ao Java, usando + (ou +=)
* Para interpolar variáveis em strings existem as F-Strings: `f'mais de {x} vezes'`. Os dados interpolados são automaticamente convertidos em strings.
* Converter dados com a função `int()` extrai apenas a parte inteira: `int(12.345) # 12`, que é diferente de usar `round` pois não arredonda o número
* Para iniciar uma string vazia é possível usar `''` ou `Nome` (que é tipo de dado NoneType)
* Para ver o Zen do Python, digite `import this` no interpretador.

## Bibliotecas
* [Automação de GUI com Python](https://imasters.com.br/back-end/automacao-de-gui-com-python-exemplo-de-uso-do-pyautogui-2)
* Instalação pyautogui: pip3 install pyautogui
* [Capturar conteúdo da área de transferência no python - 1](https://www.codegrepper.com/code-examples/python/copy+paste+python+clipboard)
* [Capturar conteúdo da área de transferência no python - 2](https://pypi.org/project/pyperclip/)
* [Capturar conteúdo da área de transferência no python - 3](http://omz-software.com/pythonista/docs/ios/clipboard.html)
* [Controlar teclado com python - 1](https://automatetheboringstuff.com/chapter18/)
* [Controlar teclado com python - 2](https://nitratine.net/blog/post/how-to-make-hotkeys-in-python/)

## Cursos em vídeo
* [Python para zumbis](https://www.youtube.com/playlist?list=PLUukMN0DTKCtbzhbYe2jdF4cr8MOWClXc)
* [The Modern Python3 Bootcamp](https://www.udemy.com/course/the-modern-python3-bootcamp)

## Resumos/Notas de livros
* [Pense em Python](https://github.com/sheilagomes/diario-de-estudos/tree/main/Python/Livro%20Pense%20em%20Python)

## Referências
* [Automate the boring stuff](https://automatetheboringstuff.com)
* [Locust](locust.io/): Ferramenta de Testes de Performance escrita em python

## Outras informações
* [Membro da Python Software Foundation](https://www.python.org/psf/membership/)
* [O que é a PSF?](https://carolinedantas.com/tutorial/2020/05/21/psf_ptbr.html)
* [Newsletters](https://mail.python.org/mailman/listinfo)


[Markdown](https://guides.github.com/features/mastering-markdown/) / [ResizeImage](https://resizeimage.net/)