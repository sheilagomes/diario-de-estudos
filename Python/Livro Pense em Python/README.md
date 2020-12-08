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
* Introdução a módulos e suas funções usando o Turtle para mover um ponto ou desenhar linhas numa interface gráfica:
```
import turtle
bob = turtle.Turtle()
for i in range(4): #instrução que desenha um quadrado
    bob.fd(100)
    bob.lt(90)
turtle.mainloop()
```
* Incluir uma parte do código em uma função chama-se encapsulamento:
```
def square(t):
    for i in range(4):
        t.fd(100)
        t.lt(90)

square(bob)
```
* Acrescentar um parâmetro a uma função chama-se generalização porque ele torna a função mais geral:
```
def polygon(t, n, length):
    angle = 360 / n
    for i in range(n):
        t.fd(length)
        t.lt(angle)

polygon(bob, 7, 70)
```
* Um plano de desenvolvimento é um processo para escrever programas. O processo que usamos neste estudo de caso é “encapsulamento e generalização”. Os passos deste processo são:
 1. Comece escrevendo um pequeno programa sem definições de função.
 2. Uma vez que o programa esteja funcionando, identifique uma parte coerente dele, encapsule essa parte em uma função e dê um nome a ela.
 3. Generalize a função acrescentando os parâmetros adequados.
 4. Repita os passos 1-3 até que tenha um conjunto de funções operantes. Copie e cole o código operante para evitar a redigitação (e redepuração).
 5. Procure oportunidades de melhorar o programa pela refatoração. Por exemplo, se você tem um código semelhante em vários lugares, pode ser uma boa ideia fatorá-lo em uma função geral adequada.
* Uma docstring é uma string no início de uma função que explica a interface:
```
def polyline(t, n, length, angle):
    """Desenha n segmentos de reta com o comprimento dado e
    ângulo (em graus) entre eles. t é um turtle.
    """
    for i in range(n):
        t.fd(length)
        t.lt(angle)
```

## Capítulo 5: Condicionais e recursividade
* A divisão pelo piso é feita com // e para obter o resrtyo de uma divisão usamos o módulo com %
* Os operadores relacionais do Python são ==, !=, >, <, <= e >=
* São três os operadores lógicos: and, or e not
* Nas condicionais com if, elif e else não há limite para o números de eilfs e o else não é obrigatório no final:
```
if x < y:
    print('x is less than y')
elif x > y:
    print('x is greater than y')
else:
    print('x and y are equal')
```
* Para ter um corpo sem instruções como um espaço reservado para código que ainda não foi escrito podemos usar a instrução `pass`
* Forma concisa de escrever condicionais:
```
if 0 < x < 10:
    print('x is a positive single-digit number.')
```
* Uma função que chama a si mesma é recursiva:
```
def countdown(n):
    if n <= 0:
        print('Blastoff!')
    else:
        print(n)
        countdown(n-1)
```
* A função integrada `input` interrompe o programa e espera que o usuário digite algo:
`name = input('What...is your name?\\n')`

## Capítulo 6: Funções com resultado
* Para definir uma função com retorno:
```
def area(radius):
    return math.pi * radius**2
```
* Cada caminho possível pelo programa deve ter um return:
```
def absolute_value(x):
    if x < 0:
        return -x
    if x > 0:
        return x #se o valor de x for zero o programa derá um erro
```
* Desenvolvimento incremental: para evitar longas sessões de depuração, acrescente e teste pequenas partes do código de cada vez, usando instruções print para depuração, e depois restirando-as. Códigos desse tipo são chamados de scaffolding, porque são úteis para construir o programa, mas não são parte do produto final.
* Depois de verificar se o programa está funcionando, podemos torná-lo mais conciso compondo chamadas de função:
```
def circle_area(xc, yc, xp, yp):
    return area(distance(xc, yc, xp, yp))
```
* 