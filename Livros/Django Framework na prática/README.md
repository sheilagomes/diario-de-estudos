# Anotações do Livro Djano Framework na prática

## Capítulo 1: Instalando e configurando o ambiente para iniciar o projeto
* Para preparar o ambiente é preciso instalar:
```
$ sudo apt update
$ sudo apt install software-properties-common
$ sudo add-apt-repository ppa:deadsnakes/ppa
$ sudo apt update
$ sudo apt install python3.8
$ sudo apt install virtualenv
```

## Capítulo 02: Iniciando seu primeiro projeto Django
* No diretório `home`:
```
$ cd
$ mkdir dev
$ cd dev
$ mkdir controle-visitantes
$ cd controle-visitantes
```
* Então criamos e ativamos o ambiente virtual:
```
$ virtualenv -p python3.8 env
$ source env/bin/activate
```
* Com o pip, instalamos o Django: `(env)$ pip install Django==3.0.0`
* Para iniciar um novo projeto no Django. O comando startproject pode receber, além do nome do projeto, o diretório em que o mesmo deverá ser iniciado (caso o diretório não seja informado, o Django criará um diretório de mesmo nome do projeto). Além disso, o Django permite apenas letras, números e o underline em nomes de projetos, por isso a pasta se chama controle-visitantes e o
projeto controle_visitantes (o ponto especifica o diretório atual):
`(env)$ django-admin startproject controle_visitantes .`
* O Django tem um servidor de desenvolvimento integrado para rodar a aplicação localmente, para iniciá-lo e ver se tudo está ok: `(env)$ python manage.py runserver`
* Depois de abrir a pasta controle-visitantes no VSCode vemos os seguintes arquivos:
  - manage.py (um utilitário de linha de comando que permite interagir com o projeto Django de diversas maneiras)
  - controle_visitantes/ (este segundo diretório nomeado da mesma forma que o diretório ascendente agrupa o pacote Python referente ao nosso projeto. O nome do diretório é o nome do nosso pacote e ele é importante pois nos auxilia no processo de importação de arquivos e funções. Seu nome não deve ser alterado.)
  - controle_visitantes/__init__.py (um arquivo vazio que diz ao Python que aquele diretório deve ser reconhecido e tratado como um pacote)
  - controle_visitantes/settings.py (arquivo de configurações do projeto Django, onde podemos detalhar como o projeto funciona e quais definições estão disponíveis)
  - controle_visitantes/urls.py (arquivo que declara as URLs do nosso projeto. Para que uma URL do nosso projeto seja acessível através do navegador, temos que declará-la neste arquivo)
  - controle_visitantes/wsgi.py (ponto de integração para servidores web que implementam o WSGI, um padrão Python que descreve como os servidores devem se comunicar com as aplicações web)
  - controle_visitantes/asgi.py (ponto de integração para servidores web utilizarem comunicação assíncrona)
(PAREI PAG 33)

[Markdown](https://guides.github.com/features/mastering-markdown/) / [ResizeImage](https://resizeimage.net/)
