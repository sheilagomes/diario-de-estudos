# Java

![Logo do Java](https://github.com/sheilagomes/diario-de-estudos/blob/main/Java/java-logo.png)

[Documentação oficial](https://docs.oracle.com/en/java/)

## Dicas de IDEs
### Eclipse/STS
* Dois cliques no nome de uma janela faz a janela maximizar e minimizar
* Para criar a expressão de impressão pulando linha digitar `sysout` e dar enter

### Intellij
* Para criar a expressão de impressão pulando linha digitar `sout` e dar enter
* Para criar a expressão do main() digitar `psvm` e dar enter 
* Para abrir ações usadas com frequência: Ctrl + Shift + A
* Debug: F7 - entra no método, F8 - próximo passo, F9 - próximo breakpoint, Drop frame - volta início execução método atual
* Entrar no método - Ctrl + Alt + B

## Dicas da linguagem
* Boa prática ao nomear métodos é começar com verbo: `exibirAutonomia()`
* Os números no Java são como uma roleta: se somar 1 ao limite, volta como negativos (fecha o círculo)
* Se usar static antes da declaração de variável dentro de uma classe, a variável é global e funcionará independente das instâncias.
* O super indica uma variável que vem de uma classe superior (quando é usado o extends, por ex.)
* O nome do arquivo java deve corresponder ao nome da classe:
```
MyClass.java
public class MyClass {
	public static void main(String[] args) {
		System.out.println("Hello World");
	}
}
```
* O Java diferencia maiúsculas de minúsculas. O padrão é usar primeira maiúscula para classes e primeira minúscula para atributos, variáveis ​​e métodos. Usar todas as letras minúsculas indica um nome de pacote e todas as letras maiúsculas, um nome de constante.
* Exemplo de nomeação de pacote: domínio da empresa ao contrário + noe do projeto + pastas/subpastas: `br.trd.multitude.cursoOmegaT.aula1`
* Todo programa Java tem um nome de classe que deve corresponder ao nome do arquivo e todo programa deve conter o método main().
* Comentários de linha única começam com duas barras (//).
* Comentários de várias linhas começam com `/*` e terminam com `*/`.
* Para criar uma variável, você deve especificar o tipo e atribuir um valor a ela:
```
int myNum = 15;
myFloatNum = 5.99f;
char myLetter = 'D';
boolean myBool = true;
String myText = "Hello";
```
* Você também pode declarar uma variável sem atribuir o valor e atribuir o valor depois:
```
int myNum;
myNum = 15;
```
* Adicione a palavra-chave `final` para declarar a variável como "final" ou "constante", para que ela seja imutável e somente para leitura: `final int myNum = 15;`
* O método `println()` é muitas vezes usado para exibir variáveis. Para combinar texto e variável, use o caractere +:
```
String name = "John";
System.out.println("Hello " + name);
```
* Para declarar mais de uma variável do mesmo tipo, use uma lista separada por vírgulas:
```
int x = 5, y = 6, z = 50;
System.out.println(x + y + z);
```
* Todas as variáveis ​​Java devem ser identificadas com nomes exclusivos chamados identificadores. É recomendável usar nomes descritivos para criar código compreensível e sustentável. As regras gerais para a construção de nomes para variáveis ​​(identificadores únicos) são: nomes podem conter letras, dígitos, sublinhados e cifrões, devem começar com uma letra, devem começar com uma letra minúscula e não podem conter espaços em branco, também podem começar com cifrão e sublinhado, os nomes diferenciam maiúsculas de minúsculas, as palavras reservadas não podem ser usadas como nomes.
* Os tipos de dados são divididos em dois grupos: Primitivos (inclui byte, short, int, long, float, double, boolean e char) e não primitivos (String, Arrays e Classes)
* O tipo de dados byte pode armazenar números inteiros de -128 a 127.
* O tipo de dados short pode armazenar números inteiros de -32768 a 32767.
* O tipo de dados int pode armazenar números inteiros de -2147483648 a 2147483647.
* O tipo de dados long pode armazenar números inteiros de -9223372036854775808 a 9223372036854775807.
* O tipo de dados float pode armazenar números fracionais de 3.4e−038 a 3.4e+038. Observe que é preciso terminar o número com um "f".
* The double data type can store fractional numbers from 1.7e−308 to 1.7e+308. Note that you should end the value with a "d".
* The char data type is used to store a single character. The character must be surrounded by single quotes, like 'A' or 'c'. Alternatively, you can use ASCII values to display certain characters:
	char a = 65, b = 66, c = 67;
* String values must be surrounded by double quotes. It is so much used and integrated in Java, that some call it "the special ninth type". A String in Java is actually a non-primitive data type, because it refers to an object. The String object has methods that is used to perform certain operations on strings.
* Use float or double? The precision of float is only six or seven decimal digits, while double variables have a precision of about 15 digits. Therefore it is safer to use double for most calculations.
* The main difference between primitive and non-primitive data types are: primitive types are predefined (already defined) in Java. Non-primitive types are created by the programmer and is not defined by Java (except for String). Non-primitive types can be used to call methods to perform certain operations, while primitive types cannot. A primitive type has always a value, while non-primitive types can be null. A primitive type starts with a lowercase letter, while non-primitive types starts with an uppercase letter. The size of a primitive type depends on the data type, while non-primitive types have all the same size. Examples of non-primitive types are Strings, Arrays, Classes, Interface, etc.
* Type casting is when you assign a value of one primitive data type to another type. In Java, there are two types of casting: Widening Casting (automatically) - converting a smaller type to a larger type size (byte -> short -> char -> int -> long -> float -> double) and Narrowing Casting (manually) - converting a larger type to a smaller size type (double -> float -> long -> int -> char -> short -> byte)
* Java divides the operators into the following groups: Arithmetic (+, -, *, /, %, ++, --), Assignment (=, +=, -=, *=, /=, %=, &=, |=, ^=, >>=, <<=), Comparison (==, !=, >, <, >=, <=), Logical (&&, ||, !), Bitwise ()
- [String methods](https://www.w3schools.com/JAVA/java_ref_string.asp): length(), toUpperCase(), toLowerCase(), indexOf(), concat()
* Java counts positions from zero. 0 is the first position in a string, 1 is the second, 2 is the third.
* Escape characters: \', \", \\, \n, \r, \t, \b, \f
* [Math methods](https://www.w3schools.com/JAVA/java_ref_math.asp):  Math.max(x,y), Math.min(x,y), Math.sqrt(x), Math.abs(x), Math.random()
* The if Statement:
```
if (condition1) {
  // block of code to be executed if condition1 is true
} else if (condition2) {
  // block of code to be executed if the condition1 is false and condition2 is true
} else {
  // block of code to be executed if the condition1 is false and condition2 is false
}
```
* Short Hand If...Else (Ternary Operator): `variable = (condition) ? expressionTrue :  expressionFalse;`
* Switch statements:
```
switch(expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
}
```
* While loop:
```
while (condition) {
  // code block to be executed
}
```
* Do/While loop:
```
do {
  // code block to be executed
}
while (condition);
```
* For loop:
```
for (statement 1; statement 2; statement 3) {
  // code block to be executed
 }
```
* For-each loop:
```
for (type variableName : arrayName) {
  // code block to be executed
}
```
* The break statement can be used to jump out of a loop. The continue statement breaks one iteration (in the loop), if a specified condition occurs, and continues with the next iteration in the loop. You can also use break and continue in while loops.
* Arrays are used to store multiple values in a single variable, instead of declaring separate variables for each value. To declare an array, define the variable type with square brackets:
```
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
    System.out.println(cars[0]);
```
* You can loop through the array elements with the for loop, and use the length property to specify how many times the loop should run.
```
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
for (int i = 0; i < cars.length; i++) {
  System.out.println(cars[i]);
```
* The following example outputs all elements in the cars array, using a "for-each" loop:
```
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
for (String i : cars) {
  System.out.println(i);
```
* A multidimensional array is an array containing one or more arrays. To access the elements of the myNumbers array, specify two indexes: one for the array, and one for the element inside that array. 
```
int[][] myNumbers = { {1, 2, 3, 4}, {5, 6, 7} };
int x = myNumbers[1][2];
System.out.println(x); // Outputs 7
```
* We can also use a for loop inside another for loop to get the elements of a two-dimensional array (we still have to point to the two indexes):
```
public class MyClass {
  public static void main(String[] args) {
    int[][] myNumbers = { {1, 2, 3, 4}, {5, 6, 7} };
    for (int i = 0; i < myNumbers.length; ++i) {
      for(int j = 0; j < myNumbers[i].length; ++j) {
        System.out.println(myNumbers[i][j]);
      }
    }
  }
```
* A method is a block of code which only runs when it is called. You can pass data, known as parameters, into a method. Methods are used to perform certain actions, and they are also known as functions. Why use methods? To reuse code: define the code once, and use it many times. A method must be declared within a class. It is defined with the name of the method, followed by parentheses (). Java provides some pre-defined methods, such as System.out.println(), but you can also create your own methods to perform certain actions. Create a method inside MyClass:
```
public class MyClass {
  static void myMethod() {
    // code to be executed
  }
}
```
* Para tipo char, usar aspas simples em vez de duplas.

## Cursos em vídeo
* [Curso completo DevDojo](https://www.youtube.com/watch?v=L151aRhoNSM&list=PL62G310vn6nHrMr1tFLNOYP_c73m6nAzL&index=34) - parei na aula 33
* [FCC Java](https://www.youtube.com/watch?v=grEKMHGYyns) - Primeiros 22min conceitos
* [Guanabara Java](https://youtu.be/xHgnlic7fj8?list=PLHz_AreHm4dkI2ZdjTwZA4mPMxWTfNSpR)

## Tutoriais em vídeo
* [Figma](https://www.youtube.com/watch?v=NB1mn2YVF8Q&feature=youtu.be)
* [Tetris em Java - 1](https://www.guj.com.br/t/tetris-em-java/100858)
* [Tetris em Java - 2](https://www.youtube.com/watch?v=KjEaD0KyL0w)
* [Tetris em Java - 3](http://zetcode.com/tutorials/javagamestutorial/tetris/)
* [Pattern factory - 1](https://www.devmedia.com.br/como-usar-o-pattern-factory-na-plataforma-java-ee/32814)
* [Pattern factory - 2](https://en.wikipedia.org/wiki/Factory_method_pattern#Java)

## Tutoriais em texto
* [Apostila JavaWeb Caellum](https://www.caelum.com.br/apostila-java-web/servlets/#mapeando-uma-servlet-no-webxml)
* [Apostila Desenvolvendo na prático com Spring e testes](https://www.caelum.com.br/apostila-java-testes-spring-design-patterns/)
* [Oracle](https://docs.oracle.com/javase/tutorial/java/concepts/index.html)

## Para ler e consultar:
* [Medium do Devs Javagirl](https://medium.com/devs-javagirl)
* [Prototipação básica online](https://wireframe.cc/)
* [Figma pra prototipação mais detalhada](https://www.figma.com/files/recent)
* [ThinkJava](https://books.trinket.io/thinkjava2/)

[Markdown](https://guides.github.com/features/mastering-markdown/) / [ResizeImage](https://resizeimage.net/)