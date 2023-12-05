---
tags:
  - JAVASCRIPT
---
# DOCUMENT OBJECT MODEL (DOM)
É uma interface que representa documentos HTML e XML através de objetos. Com ela é possível manipular a estrutura, estilo e conteúdo destes documentos.


![[EX. Document Object Model.png]]

### Window e Document
São os objetos principais do DOM, boa parte da manipulação é feita através dos seus métodos e propriedades.

```` javascript
window.alert('Isso é um alerta');
alert('Isso é um alerta'); // Funciona

document.querySelector('h1'); // Seleciona o primeiro h1
document.body; // Retorna o body
````
> window é o objeto global, por isso não precisamos chamar ele na frente dos seus métodos e propriedades.

Exemplos:
```javascript
const titulo = document.querySelector('h1');

titulo.innerText; // retorna o texto;
titulo.classList; // retorna as classes;
titulo.id; // retorna o id;
titulo.offsetHeight; // retorna a altura do elemento;

titulo.addEventListener('click', callback);
// ativa a função callback ao click no titulo
```


### Seleção de elementos
* **ID**: `getElementById` seleciona e retorna elementos do DOM.
```javascript
// Seleciona pelo ID
const animaisSection = document.getElementById('animais');
const contatoSection = document.getElementById('contato');

// Retorna null caso não exista
const naoExiste = document.getElementById('teste');
```
* **Classe e Tag**: `getElementsByClassName` e `getElementsByTagName` selecionam e retornam uma lista de elementos do DOM. A lista retornada está ao vivo, significa que se elementos forem adicionados, ela será automaticamente atualizada.
```javascript
// Seleciona pela classe, retorna uma HTMLCollection
const gridSection = document.getElementsByClassName('grid-section');
const contato = document.getElementsByClassName('grid-section contato');

// Seleciona todas as UL's, retorna uma HTMLCollection
const ul = document.getElementsByTagName('ul');

// Retorna o primeiro elemento
console.log(gridSection[0]);
```
* **Seletor geral único**: `querySelector` retorna o primeiro elemento que combinar com o seu seletor CSS.
```javascript
const animais = document.querySelector('.animais');
const contato = document.querySelector('#contato');
const ultimoItem = document.querySelector('.animais-lista li:last-child');
const linkCSS = document.querySelector('[href^="https://"]');
const primeiroUl = document.querySelector('ul');

// Busca dentro do Ul apenas
const navItem = primeiroUl.querySelector('li');
```
* **Seletor Geral**: `querySelectorAll` retorna todos os elementos compatíveis com o seletor CSS em uma NodeList.
```javascript
const gridSection = document.querySelectorAll('.grid-section');
const listas = document.querySelectorAll('ul');
const titulos = document.querySelectorAll('.titulo');
const fotosAnimais = document.querySelectorAll('.animais-lista img');

// Retorna o segundo elemento
console.log(gridSection[1]);
```

> Para pegar elementos na tela em HTML pelo console do navegador basta utilizar os seletores de elementos com a classe, id ou tag necessária.


### Foreach
Constantemente é preciso selecionar uma lista de itens do dom. A melhor forma para interagir com os mesmos é utilizando o método forEach.
```js
const imgs = document.querySelectorAll('img');

imgs.forEach(function(item){
  console.log(item);
});
```


### Parâmetros do foreach
O primeiro parâmetro é o callback, ou seja, a função que será ativada a cada item. Esse função pode receber três parâmetros: valorAtual, index e array;
```js
const imgs = document.querySelectorAll('img');

imgs.forEach(function(valorAtual, index, array){
  console.log(item); // o item atual no loop
  console.log(index); // o número do index
  console.log(array); // a Array completa
});
```


### Foreach e array
ForEach é um método de Array, alguns objetos array-like possuem este método. Caso não possua, o ideal é transformá-los em uma array.
```js
const titulos = document.getElementsByClassName('titulo');
const titulosArray = Array.from(titulos);

titulosArray.forEach(function(item){
  console.log(item);
});
```


### Arrow Function
Sintaxe curta em relação a `function expression`. Basta remover a palavra chave function e adicionar a fat arrow `=>` após os argumentos.
```js
const imgs = document.querySelectorAll('img');

imgs.forEach((item) => {
  console.log(item);
});
```

