# Javascript

![Logo do Java](https://github.com/sheilagomes/diario-de-estudos/blob/main/Javascript/js-logo.png)

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
* Para reverter uma string: `str.split('').reverse().join('')`
* Substituição globa com replace: `replace(/,/g, "") // /,/g faz substituição global da vírgula`
* Ao usar um event listener obtido do DOM com getElementsByClassName é preciso colocar o índice do elemento obtido:
```
let diceFace = document.getElementsByClassName("dice");
diceFace[0].addEventListener("click", function(){...
```
* Para iterar e alterar elementos de um array:
`allDots.forEach(dot => dot.classList.remove(...dot.classList)) //remove as classes`
* O método `includes()` verifica a existência de um elemento em um array or string dentro de outra: `nums.includes("doze")`
* O método `every()` itera os elementos de um array, passando-os por uma função e retornando um boolean true se todos os elementos forem verdadeiros ou false, se algum não for:
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
```
* Funções arrow (similar ao lambda do Python) podem ser escritas em uma linha só, com parâmetros separados do corpo da função por `=>`. Se tiverem mais de um parâmetro, eles precisam estar entre parênteses. Se não houver parâmetros, usar `()`:
`nums.filter(nums => nums % index != 0);`

[Markdown](https://guides.github.com/features/mastering-markdown/) / [ResizeImage](https://resizeimage.net/)
