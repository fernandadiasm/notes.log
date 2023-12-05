---
tags:
  - JAVASCRIPT
---
# DOCUMENT OBJECT MODEL (DOM)
É uma interface que representa documentos HTML e XML através de objetos. Com ela é possível manipular a estrutura, estilo e conteúdo destes documentos.


![[EX. Document Object Model.png]]

#### Window e Document
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


#### Parâmetros do foreach
O primeiro parâmetro é o callback, ou seja, a função que será ativada a cada item. Esse função pode receber três parâmetros: valorAtual, index e array;
```js
const imgs = document.querySelectorAll('img');

imgs.forEach(function(valorAtual, index, array){
  console.log(item); // o item atual no loop
  console.log(index); // o número do index
  console.log(array); // a Array completa
});
```


#### Foreach e array
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


#### Parâmetros e parênteses
```js
const imgs = document.querySelectorAll('img');

// parâmetro único não precisa de parênteses
imgs.forEach(item => {
  console.log(item);
});

// multiplos parâmetros precisam de parênteses
imgs.forEach((item, index) => {
  console.log(item, index);
});

// sem parâmetro precisa dos parênteses, mesmo vazio
let i = 0;
imgs.forEach(() => {
  console.log(i++);
});
```


#### Return
É possível omitir as chaves `{}` para uma função que retorna uma linha.
```js
const imgs = document.querySelectorAll('img');

imgs.forEach(item => 
  console.log(item)
);

imgs.forEach(item => console.log(item));
```


### Classlist
Retorna uma lista com as classes do elemento. Permite adicionar, remover e verificar se contém.
```js
const menu = document.querySelector('.menu');

menu.className; // string
menu.classList; // lista de classes
menu.classList.add('ativo');
menu.classList.add('ativo', 'mobile'); // duas classes
menu.classList.remove('ativo');
menu.classList.toggle('ativo'); // adiciona/remove a classe
menu.classList.contains('ativo'); // true ou false
menu.classList.replace('ativo', 'inativo');
```


#### Attributes
Retorna uma array-like com os atributos do elemento.
```js
const animais = document.querySelector('.animais');

animais.attributes; // retorna todos os atributos
animais.attributes[0]; // retorna o primeiro atributo
```

#### GetAttribute e SetAttribute
Métodos que retornam ou definem de acordo com o atributo selecionado
```js
const img = document.querySelector('img');

img.getAttribute('src'); // valor do src
img.setAttribute('alt', 'Texto Alternativo'); // muda o alt
img.hasAttribute('id'); // true / false
img.removeAttribute('alt'); // remove o alt

img.hasAttributes(); // true / false se tem algum atributo
```
>É muito comum métodos de get e set;


#### Read only vs writable
Existem propriedades que não permitem a mudança de seus valores, essas são considerados Read Only, ou seja, apenas leitura.
```js
const animais = document.querySelector('.animais');

animais.className; // string com o nome das classes
animais.className = 'azul'; // substitui completamente a string
animais.className += ' vermelho'; // adiciona vermelho à string

animais.attributes = 'class="ativo"'; // não funciona, read-only
```
> Lembre-se que podemos modificar o valor de uma propriedade `objeto.propriedade = ''`


### Eventos
#### addEventListener
Adiciona uma função ao elemento, esta chamada de `callback`, que será ativada assim que certo `evento` ocorrer neste elemento.
```js
const img = document.querySelector('img');

// elemento.addEventListener(event, callback, options)
img.addEventListener('click', function() {
  console.log('Clicou');
})
```
> O terceiro parâmetro é opcional.


#### Callback
É boa prática separar a função de callback do addEventListener, ou seja, declarar uma função ao invés de passar diretamente uma função anônima
```js
const img = document.querySelector('img');
function callback() {
  console.log('Clicou');
}

img.addEventListener('click', callback); // 🚀
img.addEventListener('click', callback()); // undefined
img.addEventListener('click', function() {
  console.log('Clicou');
})
img.addEventListener('click', () => {
  console.log('Clicou');
})
```


#### Event
O primeiro parâmetro do callback é referente ao evento que ocorreu.
```js
const img = document.querySelector('img');

function callback(event) {
  console.log(event);
}

img.addEventListener('click', callback);
```
> Geralmente utilizam `e` como nome do parâmetro.


#### Propriedades do Event
```js
const animaisLista = document.querySelector('.animais-lista');

function executarCallback(event) {
  const currentTarget = event.currentTarget; // this
  const target = event.target; // onde o clique ocorreu
  const type = event.type; // tipo de evento
  const path = event.path;
  console.log(currentTarget, target, type, path);
}

animaisLista.addEventListener('click', executarCallback);
```


#### event.preventDefault( )
Previne o comportamento padrão do evento no browser. No caso de um link externo, por exemplo, irá previnir que o link seja ativado.
```js
const linkExterno = document.querySelector('a[href^="http"]');

function clickNoLink(event) {
  event.preventDefault();
  console.log(event.currentTarget.href);
}

linkExterno.addEventListener('click', clickNoLink);
```


#### this
A palavra chave `this` é uma palavra especial de JavaScript, que pode fazer referência a diferentes objetos dependendo do contexto. No caso de eventos, ela fará referência ao elemento em que addEventListener foi adicionado.
```js
const img = document.querySelector('img');

function callback(event) {
  console.log(this); // retorna a imagem
  console.log(this.getAttribute('src'));
}

img.addEventListener('click', callback);
```
>Geralmente igual ao event.currentTarget.


#### Diferentes eventos
Existem diversos eventos como `click`, `scroll`, `resize`, `keydown`, `keyup`, `mouseenter` e mais. Eventos podem ser adicionados a diferentes elementos, como o `window` e `document` também.
```js
const h1 = document.querySelector('h1');

function callback(event) {
  console.log(event.type, event);
}

h1.addEventListener('click', callback);
h1.addEventListener('mouseenter', callback);
window.addEventListener('scroll', callback);
window.addEventListener('resize', callback);
window.addEventListener('keydown', callback);
```
>https://developer.mozilla.org/en-US/docs/Web/Events


#### Keyboard
Você pode adicionar atalhos para facilitar a navegação no seu site, através de eventos do `keyboard`.
```js
function handleKeyboard(event) {
  if(event.key === 'a')
    document.body.classList.toggle('azul');
  else if(event.key === 'v')
    document.body.classList.toggle('vermelho');
}

window.addEventListener('keydown', handleKeyboard);
```


#### forEach e eventos
O método `addEventListener` é adicionado à um único elemento, então é necessário um loop entre elementos de uma lista, para adicionarmos à cada um deles.
```js
const imgs = document.querySelectorAll('img');

function imgSrc(event) {
  const src = event.currentTarget.getAttribute('src');
  console.log(src);
}

imgs.forEach((img) => {
  img.addEventListener('click', imgSrc);
});
```


### Traversing e manipulação
#### outerHTML, innerHTML e innerText
Propriedades que retornam uma string contendo o html ou texto. É possível atribuir um novo valor para as mesmas `element.innerText = 'Novo Texto'`.
```js
const menu = document.querySelector('.menu');

menu.outerHTML; // todo o html do elemento
menu.innerHTML; // html interno
menu.innerText; // texto, sem tags

menu.innerText = '<p>Texto</p>'; // a tag vai como texto
menu.innerHTML = '<p>Texto</p>'; // a tag é renderizada
```

#### traversing
Como navegar pelo DOM, utilizando suas propriedades e métodos.
```js
const lista = document.querySelector('.animais-lista');

lista.parentElement; // pai
lista.parentElement.parentElement; // pai do pai
lista.previousElementSibling; // elemento acima
lista.nextElementSibling; // elemento abaixo

lista.children; // HTMLCollection com os filhos
lista.children[0]; // primeiro filho
lista.children[--lista.children.length]; // último filho

lista.querySelectorAll('li'); // todas as LI's
lista.querySelector('li:last-child'); // último filho
```


#### element vs node
Element's represetam um elemento html, ou seja, uma tag. Node representa um nó, e pode ser um elemento (Element), texto, comentário, quebra de linha e mais.
```js
const lista = document.querySelector('.animais-lista');

lista.previousElementSibling; // elemento acima
lista.previousSibling; // node acima

lista.firstChild; // primeiro node child
lista.childNodes; // todos os node child
```
>Geralmente estamos atrás de um elemento e não de qualquer node em si.


#### manipulando elementos
É possível mover elementos no dom com métodos de Node.
```js
const lista = document.querySelector('.animais-lista');
const contato = document.querySelector('.contato');
const titulo = contato.querySelector('.titulo');

contato.appendChild(lista); // move lista para o final de contato
contato.insertBefore(lista, titulo); // insere a lista antes de titulo
contato.removeChild(titulo); // remove titulo de contato
contato.replaceChild(lista, titulo); // substitui titulo por lista
```


#### novos elementos
Podemos criar novos elementos com o método `createElement()`.
```js
const animais = document.querySelector('.animais');

const novoH1 = document.createElement('h1');
novoH1.innerText = 'Novo Título';
novoH1.classList.add('titulo');

animais.appendChild(novoH1);
```


#### clonar elementos
Todo elemento selecionado é único. Para criarmos um novo elemento baseado no anterior, é necessário utilizar o método `cloneNode()`.
```js
const titulo = document.querySelector('h1');
const titulo2 = document.querySelector('h1');
const novoTitulo = titulo;
// titulo, titulo2 e novoTitulo são iguais

const cloneTitulo = titulo.cloneNode(true);
const contato = document.querySelector('.contato');
contato.appendChild(cloneTitulo);
```
> `true` sinaliza para incluir os filhos
