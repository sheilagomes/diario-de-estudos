# Django

## Dicas gerais
* Django é um framework para aplicações web gratuito e de código aberto, escrito em Python.
* Para instalar o Django no computador, segundo o tutorial das [Djangogirls](https://tutorial.djangogirls.org/pt/installation/):
```
mkdir djangogirls 
cd djangogirls
python3 -m venv myvenv
python -m pip install --upgrade pip
```
* Então criar o arquivo `requirements.txt` dentro da pasta djangogirls e acrescentar o seguinte dentro: `Django~=2.2.4`
* Instalar com o seguinte comando: `pip install -r requirements.txt`
* No PythonAnywhere, pegar o token da API na seção "API Token" da conta.
* No terminal, ativar o ambiente virtual com `source myvenv/bin/activate`
* Para criar um novo projeto no diretório em que se está: `django-admin startproject mysite .`
* Para alterar o fuso horário nas configurações no novo projeto, abrir `mysite > settings.py` e alterar: `TIME_ZONE = 'America/Sao_Paulo'`
* Para alterar o idioma das notificações e texto interno do Django, alterar: `LANGUAGE_CODE = 'pt-BR'`
* Para adicionar o caminho para os arquivos estáticos, no final do arquivo, logo abaixo da linha com `STATIC_URL`, adicionar uma nova variável chamada `STATIC_ROOT`:
`STATIC_ROOT = os.path.join(BASE_DIR, 'static')`
* Quando `DEBUG` for `True` e `ALLOWED_HOSTS` estiver vazia, o domínio do site será validado como `['localhost', '127.0.0.1', '[::1]']`. Para rodar o app no PythonAnywhere, mudamos para:
`ALLOWED_HOSTS = ['127.0.0.1', '.pythonanywhere.com']`
* Para criar um banco de dados executamos o comando `python manage.py migrate` no diretório que contém o arquivo `manage.py`
* Para iniciar o servidor web executamos o comando `python manage.py runserver` no diretório que contém o arquivo `manage.py`
* Para rodar o Django no navegador: `http://127.0.0.1:8000/`, para interromper, Ctrl + C no terminal em que foi aberto
* Para criar um app, executamos o seguinte comando no diretório onde está o arquivo `manage.py`: `python manage.py startapp blog`
* Aí dizemos ao Django para usá-lo, alterando o arquivo `mysite/settings.py`. Na linha `INSTALLED_APPS` adicionamos uma linha com o nome do app, no caso, `'blog'`:
```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'blog',
]
```
* No arquivo `blog/models.py` definimos todos os objetos chamados Modelos para as postagens.
* O método `__str__()` é um método com retorno.
* Para indicar ao Django que houve alterações no modelo, digite `python manage.py makemigrations blog`
* Com isso, o Django prepara um arquivo de migração que precisamos aplicar ao banco de dados, para isso digite `python manage.py migrate blog`
* Para adicionar, editar e deletar os posts que acabamos de modelar, nós usaremos o admin do Django, abrindo e editando o arquivo `blog/admin.py`
* Reiniciamos o servidor web executando `python manage.py runserver` e digitando no navegador o endereço `http://127.0.0.1:8000/admin/`
* Precisamos criar um `superuser` digitando `python manage.py createsuperuser`
* Para subir o projeto no PythonAnywhere, criamos um repositório no GitHub, onde serão salvos todos os arquivos. Criamos também um arquivo `.gitignore` na pasta `djangogirls` com o seguinte conteúdo:
```
*.pyc
*~
__pycache__
myvenv
db.sqlite3
/static
.DS_Store
```
* Para alterar o conteúdo do banco de dados: `http://sheilagomes.pythonanywhere.com/admin`

[Markdown](https://guides.github.com/features/mastering-markdown/) / [ResizeImage](https://resizeimage.net/)
