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
* Uma variável dentro de uma função é local, ou seja, não existe fora da função.

