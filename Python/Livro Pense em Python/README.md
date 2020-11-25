# Anotações do Livro Pense em Python

[Link do livro](https://penseallen.github.io/PensePython2e/)

## Capítulo 1: A jornada do programa
* Se for omitido um dos parênteses em uma instrução print: no início dá erro de sintaxe, se for do final ele interpreta que a instrução foi dividida em mais de uma linha e fica esperando incluir o parênteses de fechamento.
* Se usar um sinal de menos para fazer um número negativo o interpretador imprime o número (Ex.: `-2`). Se puser um sinal de mais antes de um número, ele só imprime o número sem o sinal. Se escrever `2++2` (ou até mais símbolos de +) ele interpreta como se só houvesse um sinal de mais e dá o resultado `4`.
* A notação de números do interpretador é americana, ou seja, vírgulas e pontos invertidos em relação à notação brasileira.

## Capítulo 2: Variáveis, expressões e instruções
* O Python segue a convenção matemática de ordem de precedência na execução, exemplificada pelo  acrônimo PEMDAS (Parênteses, Exponenciação, Multiplicação, Divisão, Adição e Subtração).
* O operador + faz concatenação de strings e o * cria repetiçoes: `'Spam'*3 # 'SpamSpamSpam’`.
* São três os tipos de erros que podem ocorrer em um programa: erros de sintaxe, erros de tempo de execução e erros semânticos.
* No Python é possível fazer atribuições múltiplas: `x = y = 1`
* Para usar o π no Python é preciso importar a biblioteca math:
```
import math
round((4/3)*math.pi*(5**3),2)
```
* O `_` (sublinhado) usa o valor da última operação no interpretador do Python.

## Capítulo 3: Funções
* As regras para nomes de função são as mesmas que as das variáveis.
* A definição de uma função cria um objeto de função, que tem o tipo function.
* A ordem da declaração das funções no corpo do programa não importa, desde que as chamadas estejam depois delas.
* Funções podem usar argumentos, que na declaração da função são chamados de parâmetros.
```
def print_twice(bruce): #parâmetro = bruce
    print(bruce)
    print(bruce)

print_twice(42) #argumento = 42
print_twice('Spam '*4) #argumento = 'Spam '*4
print_twice(math.cos(math.pi)) #argumento = math.cos(math.pi)
michael = 'Eric, the half a bee.'
print_twice(michael) #argumento = variável michael
```
* Variáveis e parâmetros dentro de uma função são locais, ou seja, não existem fora da função.
* As funções podem ter retorno ou serem nulas. Se uma função nula for atribuída a uma variável, ela recebe um valor especial chamado `None` (do tipo `NoneType`):
* Funções sáo úteis para manter o código limpo e curto, para serem reutilizadas em outros programas e para facilitar a depuração.
* Uma função é dividida em cabeçalho (primeira linha) e corpo.
* A notação de ponto é a forma em que se chama uma função de outro módulo,  especificando o nome do módulo seguido de um ponto e o nome da função.
* Exemplo de função para justificar palavras à direita:
```
def right_justify(word):
    print(f'{' '*(70-len(word)'}{word})
```
* Exemplo de função para repetir o uso de outras funções:
```
def do_twice(f, x):
    f(x)
    f(x)

def do_four(f,x):
    do_twice(f,x)
    do_twice(f,x)

def print_x(x):
    print(x)

do_four(print_x, 'aria')
```
* Exercício de construção de grade:
```
def linha_mais():
    print('+ - - - -', end=' ')

def linha_barra():
    print('|        ', end=' ')

def final_mais():
    print('+')

def final_barra():
    print('|')

def dobra(f):
    f()
    f()

def quadruplica(g):
    dobra(g)
    dobra(g)

def linhas_horizontais():
    quadruplica(linha_mais)
    final_mais()

def linhas_verticais():
    quadruplica(linha_barra)
    final_barra()

def grade():
    linhas_horizontais()
    quadruplica(linhas_verticais)
    linhas_horizontais()
    quadruplica(linhas_verticais)
    linhas_horizontais()
    quadruplica(linhas_verticais)
    linhas_horizontais()
    quadruplica(linhas_verticais)
    linhas_horizontais()

grade()
```

## Capítulo 4: Estudo de caso: projeto de interface

