# Javascript

## Dicas da linguagem
* Ctrl + Shift + I no navegador pra abrir console
* Usar `let` Para criar variáveis que podem ser alteradas:
```
let variavel = "variável";
let maisJS = "JS";
let fraseInteira = variavel + " " + maisJS; //concatenação antiga, foi alterada no ES6
```
* Para apresentar no console:
`console.log(variavel + maisJS);`
* Estruturas de dados similares a Java, tipagem dinâmica como Python
* Comentários iguais a Java:
```
// uma linha
/* várias
linhas*/
```
* Para criar variáveis que não podem mudar:
`const naoMuda = "Imutável";`
* Por convenção, as linhas de código terminam igual ao Java, com ;
* Concatenação a partir do ES6: 
`console.log(`${firstName} ${lastName}`);`
* Alguns métodos de strings (podem ser acumulados e são resolvidos da esquerda para a direita):
```
console.log(`${firstName} ${lastName}`.trim().length); //trim tira espaços ao redor
console.log(`${firstName} ${lastName}`.toUpperCase());
console.log(`${firstName} ${lastName}`.toLowerCase());
console.log(`${firstName} ${lastName}`.split(' ')); //cria um array das strings separadas pelo atributo definido
console.log(`${firstName} ${lastName}`.split('')); //cria um array com cada letra separada das strings

```
* Números são sempre do tipo number, mas podem ser convertidos a partir de tipos ou formatos diferentes:
```
console.log(parseInt(7.77))
console.log(parseFloat('7.77'));
console.log('7.77'.toFixed(5));
```
* Usar o método toFixed() com menos dígitos que o número original arredonda-o para cima: `console.log('7.77'.toFixed(5)); // 7.8`
* O tipo resultante do método toFixed() é uma string
* Valores que dão `false` para boolean: NaN, null, 0, '', undefined
* Para criar arrays usamos colchetes, seguem alguns métodos:
```
let example1 = [];
let example2 = [5, 7, 6];
console.log(example1.length);
example1.push(8); // adiciona no final
console.log(example1);
example1.pop(); // remove o último
console.log(example1);
console.log(example2[0]);
example1.forEach((element) => { // percorre o array
    console.log(element)
});
const products = ["toilet paper", "bottled water", "sanitizer"];
products[0] = "paper towels";
products.pop();
products.push("bleach");
```
* Para criar objetos usamos chaves:
```
let example1 = {
    firstName: 'Dylan',
    lastName: 'Israel',
    address: {
        city: 'Austin',
        state: 'Texas'
    },
    age: 30,
    cats: ['Milo', 'Tito', 'Achieles']
};
console.log(example1.address.city);
example1.age = 31; // para alterar
console.log(example1.age);
```
* Para ver todas as chaves dos pares: `console.log(Object.keys(example1));`
* Para ver todos os valores dos pares: `console.log(Object.values(example1));`
* Para conferir se uma chave existe: 
`console.log(example1.hasOwnProperty('firstName2'));`
* Exemplo de objeto com aninhamento e atribuições:
```
const user = {
    firstName: 'Dylan',
    lastName: 'Israel'
};
user['address'] = {
    city: 'Tampa',
    state: 'Florida'
};
user.hobbies = ['Anime', 'Coding', 'Dating', 'Gaming'];
user.isGoldMember = true; //Boa prática para declarar booleans é usar verbo antes
console.log(user);
```
* Diferença entre os operadores relacionais == e ===: o primeiro verifica só se os valores são iguais, o segundo, se os valores e os tipos são iguais
* Incrementos e decrementos:
```
example1++;
example1--;
example1 += 5; // Também funciona com -=, *=, /=, %=
```
* Operadores de comparação são iguais aos do Java (&&, ||)
* Em declarações switch, todas as opções de case precisam ter break, menos a default
* Declaração for é igual à do Java:
```
for (let i = 0; i <5; i++) {
    total += i;
}
```
* For aprimorado para percorrer arrays:
```
for(const cartItem of cartItems) {
    total += cartItem.price * cartItem.quantity;
}
```
* Para criar funções:
```
function add(num1, num2) {
    return num1 + num2;
}

console.log(add(10, 6));
```
* Para inverter uma string: `str.split('').reverse().join('')`
* Substituição globa com replace: `replace(/,/g, "") // /,/g faz substituição global da vírgula`
* Ao usar um event listener obtido do DOM com getElementsByClassName é preciso colocar o índice do elemento obtido:
```
let diceFace = document.getElementsByClassName("dice");
diceFace[0].addEventListener("click", function(){...
```
* Para iterar e alterar elementos de um array:
`allDots.forEach(dot => dot.classList.remove(...dot.classList)) //remove as classes`
* O método `includes()` verifica a existência de um elemento em um array or string dentro de outra: `nums.includes("doze")`
* O método `every()` itera os elementos de um array, passando-os por uma função e retornando um boolean true (se todos os resultados forem verdadeiros) ou false (se algum não for):
```
let ages = [32, 33, 12, 40];

function checkAdult(age) {
  return age >= 18;
}

if (ages.every(checkAdult)) {
    document.getElementById("resposta").innerHTML = "Todos têm mais de 18 anos.";
} else {
    document.getElementById("resposta").innerHTML = "Nem todos têm mais de 18 anos.";
};
```
* Ao usar o operador de negação `!` em uma condição, ele deve estar dentro dos parênteses.
* Para converter strings em integers usamos `parseInt()`, mas ele não pode ser usado em um array, apenas em elementos únicos.
* O método `filter()` cria um array com os elementos que retornarem de uma função:
```
let ages = [32, 33, 16, 40];
function checkAdult(age) {
  return age >= 18;
}
ages.filter(checkAdult); // [32, 33, 40]

function validUserNames(usrArray) {
    return usrArray.filter(usr => usr.length < 10)
}
```
* Funções arrow (similar ao lambda do Python) podem ser escritas em uma linha só, com parâmetros separados do corpo da função por `=>`. Se tiverem mais de um parâmetro, eles precisam estar entre parênteses. Se não houver parâmetros, usar `()`:
`nums.filter(nums => nums % index != 0);`
* Para fazer entrada de dados por input do html e saída de resultado para html:
```
let inputWords = document.querySelector('input');
inputWords.addEventListener('keyup', function(event) {
    if (event.keyCode === 13) {
        document.getElementsByClassName('teste')[0].innerHTML = `${insertDashes(inputWords.value)}`;
    }
});
```
* Um array criado com `const` pode receber valores com `push()`, mas não pode receber o resultado de uma operação com `split()` 
* É possível interagir com variáveis SASS direto no [Javascript](https://codepen.io/kevinpowell/pen/47a7913feb4cff477b0c9d7b0fe2008a)
* Coisas que dá pra fazer com um operador spread: copiar um array, combinar arrays, adicionar um item a um array, adicionar uma propriedade a um objeto, usar funções Math(), arrays spread como argumentos de função, passar argumentos ilimitados a uma função, converter um nodeList em um array, desestruturar um objeto e explodir uma string.
* Como usar o operador spread(...) para unir arrays:
```
const arr1 [1,2,3];
const arr2 [4,5,6];
const arr3 [...arr1, ...arr2];
console.log(arr3);
// [ 1, 2, 3, 4, 5, 6 ]
```
* O operador spread também pode ser usado como o método push():
```
let arr1 = ['this', 'is', 'an'];
arr1 = [...arr1, 'array'];
console.log(arr1);
// [ 'this', 'is', 'an', 'array' ]
```
* Métodos para obter o timestamp:
```
new Date().getTime();
new Date().valueOf();
Date.now(); // exceto em navegadores antigos
```
* Como o JS traz o timestamp em milissegundos, para saber o número de segundos é preciso dividir por 1000: `Math.floor(new Date().getTime() / 1000);`
* Para converter o timestamp em uma data legível, usar o número em milissegundos e o método `toString`: `new Date(1610341839403).toString();`
* A diferença técnica entre um framework e uma biblioteca está em um termo chamado inversão de controle. Quando você usa uma biblioteca, fica responsável pelo fluxo do aplicativo. Você escolhe quando e onde usar a biblioteca. Quando você usa um framework, ele é responsável pelo fluxo.
* Expressões de função são funções sem nome atribuídas a uma variável e são chamadas da mesma forma que uma função normal:
```
const add = function (num1, num2) { return num1 + num2 };
add(3,4); // 7
```
* É possível passar uma função como argumento de outra, mas daí o argumento não precisa dos parênteses:
```
function soma(num1, num2) {
    return num1 + num2;
};

function doTwice(func) {
    console.log(func(1,2));
    console.log(func(1,2));
};

doTwice(soma); // 3, 3
```
* É possível criar uma factory function, ou fábrica de funções, usando uma função como retorno:
```
function makeBetweenFunc(min, max) {
    return function (num) {
        return num >= min && num <= max;
    }
}

const teste = makeBetweenFunc(1, 10);

console.log(teste(10)); // true
```
* Um método é uma função atribuída como propriedade de um objeto:
```
const myMath = {
    PI: 3.14159,
    square(num) {
        return num * num;
    },
    cube(num) {
        return num ** 3;
    }
}
```
* A palavra `this` se refere ao objeto onde está inserida. Se não for usada no contexto de um objeto, ela vai se referir ao objeto `window`, que representa uma janela que contém um elemento DOM; a propriedade `document` aponta para o documento `DOM document` carregado naquela janela.
* Para capturar erros e devolver de forma diferente da declaração de erro:
```
try {
	console.log("Expressão");
} catch {
	console.log("Erro na expressão") // se a parte dentro do try não funcionar
}
```
* Para aplicar uma função sobre cada elemento de um array podemos usar `forEach`:
```
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
numbers.forEach(function (el) {
    if (el % 2 === 0) {
        console.log(el)
    }
})
```
* Uma opção mais recente para aplicar uma função sobre cada elemento de um array é `for of`:
```
const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
for (let el of numbers) {
	console.log(el);
}
```
* A função `map` cria um array com os resultados da aplicação de uma função:
```
function cleanNames(el) {
    return el.map(function(str) {
        return str.trim();
    });
}
```
* Arrow functions são um jeito diferente de escrever expressões de função. Se a função não tiver argumentos, basta usar () antes da flecha, se houver mais de um argumento, eles devem estar entre parênteses, e se houver apenas um argumento, não precisa de parênteses:
```
const greet = name => {
    return `Hey ${name}!`;
};
```
* É possível simplificar uma arrow function ainda mais e eliminar chaves e a declaração `return` se a função tiver um retorno implícito e for composta por apenas uma linha:
`const greet = name => name.toUpperCase();`

* Quando é necessário adicionar event listeners a vários elementos do DOM de uma vez só:
```
document.querySelectorAll('.some-class').forEach(item => {
  item.addEventListener('click', event => {
    //handle click
  })
})
```
* Os comandos `setTimeout` e `setInterval` são usados para executar ações depois de um intervalo de tempo. No caso de `setTimeout`, a ação é executada uma vez, no caso de `setInterval`, repetidamente a cada intervalo definido. Para interromper a execução de `setInterval` é preciso usar o comando `clearInterval()`:
```
console.log("HELLO!!!...")
setTimeout(() => {
    console.log("...are you still there?")
}, 3000)
console.log("GOODBYE!!")

const id = setInterval(() => {
    console.log(Math.random())
}, 2000);

// clearInterval(id);
```
* O método `every` retorna `true` se os elementos de um array passarem na função definida, ou `false` se não passarem. O método `some` é muito similar, mas basta um valor passar na função para ele retornar `true`:
```
let grades = [6, 9, 7, 8];
grades.every(grade => grade > 6.9); // false
grades.some(grade => grade > 6.9); // true
```
* Com o método `reduce` é possível extrair um valor a partir de uma função aplicada a um array:
```
let grades = [6, 9, 7, 8];
let generalAverage = grades.reduce((average, grade) => average + grade)/grades.length;

```
* Para mostrar um número fixo de decimais depois de um número usamos o método `toFixed(1)` com o número de decimais que queremos.
* Para arredondar podemos usar `Math.round()`, `Math.ceil()` e `Math.floor`. O primeiro arredonda para baixo ou para cima, dependendo se os decimais estiverem abaixo ou acima  de 0.5, o segundo sempre para cima e o terceiro sempre para baixo.

## Artigos
* [Understanding the DOM](https://dev.to/joshcarvel/properly-understanding-the-dom-2cg0)

## Referências
* [CSS Variables - manipulating them with JavaScript](https://youtu.be/cZ0yt67A7OM)

[Markdown](https://guides.github.com/features/mastering-markdown/) / [ResizeImage](https://resizeimage.net/)
