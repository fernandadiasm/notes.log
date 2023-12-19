---
tags:
  - JAVASCRIPT
  - "#EXERCÍCIOS"
curso: "JavaScript: manipulando elementos no DOM - Alura"
link do código: https://github.com/fernandadiasm/cursos/tree/main/1-alura/03-js-manipulando-elementos-do-dom-alura
---
#### Capturando os elementos
Primeiro é preciso buscar a tag HTML:
```javascript
const html = document.querySelector('html')
```

Também é necessário fazer referência aos **botões**, já que pretendemos usar eventos quando eles forem clicados.
```javascript
const html = document.querySelector('html')
const focoBt = document.querySelector('.app__card-button--foco')
const curtoBt = document.querySelector('.app__card-button--curto')
``````

#### Evento de clique
Chamaremos a variável `focoBt`, que obtivemos ao selecionar o primeiro botão, e aplicaremos um evento de clique. Para isso, usaremos `addEventListener()`, indicando que o evento é um clique por meio de `'click'` entre aspas. Associaremos uma _arrow function_ para descrever o que deve ocorrer quando esse botão for clicado.
Na função, a intenção é modificar um atributo da variável HTML. Para isso, usaremos outro método chamado `setAttribute()`. Este método exige dois argumentos.
Primeiramente, devemos especificar **qual elemento será modificado**. Desejamos alterar o `dataAttribute` da variável HTML, o `data-contexto`. Para isso, fornecemos o valor `data-contexto` seguido de uma vírgula. Quanto ao que será inserido quando o botão `focoBt` for clicado, queremos que o novo valor seja atribuído à variável, ou seja, `foco`.
```javascript
const html = document.querySelector('html')
const focoBt = document.querySelector('.app__card-button--foco')
const curtoBt = document.querySelector('.app__card-button--curto')

focoBt.addEventListener('click', () => {
    html.setAttribute('data-contexto', 'foco')
})
```

Podemos aplicar isso para os outros botões.
Por exemplo, faremos o mesmo procedimento com o `curtoBt`. Também aplicaremos um `addEventListener`(), com o evento definido como `'click'`, seguido de uma _Arrow Function_. Em seguida, utilizarei novamente `html.setAttribute()`, passando `data-contexto` como argumento e o valor do próximo atributo que será inserido. Nesse caso, esse valor será `descanso-curto`.
```javascript
const html = document.querySelector('html')
const focoBt = document.querySelector('.app__card-button--foco')
const curtoBt = document.querySelector('.app__card-button--curto')

focoBt.addEventListener('click', () => {
    html.setAttribute('data-contexto', 'foco')
})

curtoBt.addEventListener('click', () => {
    html.setAttribute('data-contexto', 'descanso-curto')
})
```

#### Testando o projeto
Ao testar o botão e clicar em "descanso curto", podemos verificar a cor de fundo mudar para verde, e ao clicarmos em "foco", ela retornará ao lilás.

Nesse processo, aprendemos dois métodos essenciais para manipulação de elementos no DOM.

O primeiro método que usamos, o `addEventListener()`, não está restrito apenas ao evento de clique; ele engloba diversos outros eventos, tais como _scroll_ (rolagem) e _resize_ (redimensionamento). Para que você possa aprofundar seu entendimento sobre o `EventListener`, apresentarei uma atividade extra que explora esse tópico em detalhes.

Adicionalmente, utilizamos o `setAttribute()`, uma ferramenta que continuaremos a utilizar ao longo deste curso. Ele é acompanhado por vários outros métodos que podemos considerar como "companheiros", como o `getAttribute()` e o `removeAttribute()`. Sendo assim, disponibilizarei uma atividade adicional que oferece uma explicação mais abrangente sobre esses métodos, com o objetivo de fornecer um contexto mais claro.


#### Alterando as imagens
Precisamos referenciar a tag `<img>` e alterar a imagem. Para fazer isso, vamos pegar a tag pela classe `app__image`. No arquivo `script.js`, vamos criar uma nova variável na linha 5 chamada `banner`, que receberá o método `document.querySelector()`. Entre aspas simples, chamaremos a classe `.app__image`.
```js
const banner = document.querySelector('.app__image')
```

##### Alterando o caminho das imagens
Agora, dentro do próprio evento de clique (`addEventListener()`) da variável `focoBt`, podemos alterar também a imagem. Então, no escopo da _arrow function_, vamos chamar a variável `banner` e aplicar a mesma metodologia que usamos na variável `html` para alterar a cor de fundo.
Chamaremos o método `setAttribute()` após a variável `banner` e passaremos como parâmetro o que queremos alterar, que no caso é o caminho da imagem, ou seja, o atributo `src`.
Então, vamos passar primeiro o parâmetro `src` entre aspas simples, e em seguida, o caminho da imagem também entre aspas simples. A imagem desejada está inserida na pasta "imagens", com o nome `foco.png`, a qual já está aplicada na página.
Teremos o seguinte código:
```js
focoBt.addEventListener('click', () => {
    html.setAttribute('data-contexto', 'foco')
    banner.setAttribute('src', '/imagens/foco.png')
})
```

A metodologia será a mesma para alterar as outras imagens nos demais eventos de clique. Na linha 14, dentro do `addEventListener()` da variável `curtoBt`, vamos chamar a variável `banner` seguida do método `setAttribute()` que receberá os parâmetros `src` (atributo) e `/imagens/descanso-curto.png` (caminho da imagem).

```js
curtoBt.addEventListener('click', () => {
    html.setAttribute('data-contexto', 'descanso-curto')
    banner.setAttribute('src', '/imagens/descanso-curto.png')
})

//...

longoBt.addEventListener('click', () => {
    html.setAttribute('data-contexto', 'descanso-longo')
    banner.setAttribute('src', '/imagens/descanso-longo.png')
})
```
Com isso, finalizamos todo o método para alterar as imagens! Agora, ao clicar em "Descanso curto" no temporizador, teremos a imagem verde da mergulhadora, e ao clicar em "Descanso longo", teremos a imagem azul da segunda mergulhadora.

#### Refatorando
Não é à toa que o nome dos atributos, como `foco`, `descanso-curto` e `descanso-longo`, são iguais aos nomes das imagens.
Na linha 22 do arquivo `script.js`, criaremos uma função chamada `alterarContexto()`, que receberá a variável `html` com o método `setAttribute()` recebendo os parâmetros `data-contexto` e `contexto`.
```js
function alterarContexto() {
    html.setAttribute('data-contexto', contexto)
}
```

Em seguida, vamos chamar a variável `banner` também com o método `setAttribute()`, recebendo como parâmetro o atributo `src` e o `contexto`. Porém, precisamos inserir `contexto` em um caminho de imagem, então vamos passar entre acentos graves o segundo parâmetro `/imagens/${contexto}.png`.
```js
function alterarContexto() {
    html.setAttribute('data-contexto', contexto)
    banner.setAttribute('src', `/imagens/${contexto}.png`)
}
```
> Note que usamos uma _template string_ (`${}`), porque estamos inserindo um valor JavaScript dentro de um conjunto de elementos HTML.

##### Ajustando os métodos addEventListener( )
Agora, como passar o `contexto` para a função `alterarContexto()`? Faremos isso por meio do clique do `addEventListener()`. Por exemplo: vamos apagar da linha 8 à linha 9 no primeiro evento de clique; feito isso, vamos chamar a função `alterarContexto()`, recebendo o valor `foco`, que é tanto o caminho da imagem quanto o valor do atributo.
```js
focoBt.addEventListener('click', () => {
    alterarContexto('foco')
})
```

Faremos o mesmo processo para o segundo e para o terceiro eventos de clique.
```js
curtoBt.addEventListener('click', () => {
    alterarContexto('descanso-curto')
})
longoBt.addEventListener('click', () => {
    alterarContexto('descanso-longo')
})
```

Para passar o valor do parâmetro para uma função, basta incluir `contexto` como parâmetro de `alterarContexto()` na linha de código 19. Dessa forma, será percorrida toda a função e substituído tanto o valor do atributo como também o caminho da imagem.
```js
function alterarContexto(contexto) {
    html.setAttribute('data-contexto', contexto)
    banner.setAttribute('src', `/imagens/${contexto}.png`)
}
```


#### Alterando o texto da página
Podemos usar essa classe para referenciar a tag `<h1>` no código JavaScript. Então, no arquivo `script.js`, vamos criar uma variável para a classe `app__title` chamada `titulo`, que recebe o método `document.querySelector()` chamando a classe `.app__title` entre aspas simples.
```js
const titulo = document.querySelector('.app__title')
```

#### Criando um bloco switch
Faremos a mudança de elementos quando houver um evento de clique. Então, como faremos uma alternância de contexto, podemos passar as informações no escopo da função `alterarContexto()`.

Para isso, utilizaremos um bloco `switch`. A depender de cada `case`, isto é, cada contexto, faremos a iteração. Ao adicionar o bloco, teremos o seguinte código:
```js
function alterarContexto(contexto) {
    html.setAttribute('data-contexto', contexto)
    banner.setAttribute('src', `/imagens/${contexto}.png`)
    switch (key) {
        case value:
        
            break;
        
        default:
            break;
    }
}
```

Vamos começar alterando o `key` para `contexto`, pois é ele que o `switch` receberá e com quem irá trabalhar. Além disso, vamos alterar o `value` da linha 24 para o primeiro contexto com o qual iremos trabalhar, que será o `foco`.

Dentro desse primeiro `case`, chamaremos a variável `titulo` que acabamos de criar. Para inserir um texto na página, usaremos um novo método para manipular elementos no DOM. No nosso caso, o método usado será específico para trabalhar com textos no HTML: o `innerHTML`.

>Para passar as informações, usamos o sinal de igual (`=`) e entre crases inserimos o texto.

Agora podemos trabalhar nos próximos `case`. O segundo será o `descanso-curto`, onde usaremos a variável `titulo` com o método `innerHTML`. Dessa vez, o texto será "Que tal dar uma respirada? Faça uma pausa curta!".

Da mesma forma, vamos inserir as tags `<strong class="app__title-strong">` e `</strong>` envolvendo o trecho "Faça uma pausa curta!". Para finalizar, faremos o `break`.

Na sequência, criaremos o último `case`, chamado `descanso-longo`, que receberá na linha 36 a variável `titulo` com o método `innerHTML`, para o qual passaremos o texto "Hora de voltar à superfície. Faça uma pausa longa.", adicionando as tags de estilo.

Ao final, temos o item `default`, contendo apenas `break`. Ele serve para o caso de não encontrar nenhum tipo dos valores anteriores.

```js
function alterarContexto(contexto) {
    html.setAttribute('data-contexto', contexto)
    banner.setAttribute('src', `/imagens/${contexto}.png`)
    switch (contexto) {
        case "foco":
            titulo.innerHTML = `
            Otimize sua produtividade,<br>
                <strong class="app__title-strong">mergulhe no que importa.</strong>
            `
            break;
        case "descanso-curto":
            titulo.innerHTML = `
            Que tal dar uma respirada? <strong class="app__title-strong">Faça uma pausa curta!</strong>
            ` 
            break;
        case "descanso-longo":
            titulo.innerHTML = `
            Hora de voltar à superfície.<strong class="app__title-strong"> Faça uma pausa longa.</strong>
            `
        default:
            break;
    }
}
```

#### Alterando a cor do botões conforme o clique
No arquivo "script.js", chamaremos a variável `focoBt` no primeiro `AddEventListener`, usando o método `.classList`, que trabalha com várias classes. Com ele, podemos acrescentar um `.add('active')`.
```js
focoBt.addEventListener('click', () => {
        alterarContexto('foco')
        focoBt.classList.add('active')
})

//Faremos o mesmo com os demais `addEventListener`:
curtoBt.addEventListener('click' , () => {
        alterarContexto('descanso-curto')
        curtoBt.classList.add('active')
})

longBt.addEventListener('click' , () => {
        alterarContexto('descanso-longo')
        longoBt.classList.add('active')
})
```

Com isso, ao ativarmos o evento `click`, estamos adicionando a classe `active` nos botões. Para testar o código, clicaremos no botão "Descanso curto" e observaremos que a classe `active` foi inserida, colocando um fundo com borda em torno do botão e o destaque em negrito. O mesmo acontece quando clicamos em "Descanso longo".

No entanto, ainda precisamos retirar a classe `active` conforme o clique, para que fique apenas um botão ativo por vez. Do contrário, todos os botões permanecem ativos.

Também podemos usar o `classList` para remover uma classe. Conferindo o arquivo "index.html", copiaremos a classe `app__card-button`, usada para os três botões. Em "script.js", faremos um `array` de botões da seguinte forma:

Criaremos uma variável do tipo `const` chamada `botoes`. Ela será igual a `document.querySelectorAll()`, tendo como parâmetro a classe `app__card-button`:

```javascript
const botoes = document.querySelectorAll('app__card-button')
```

O `querySelectorAll` é o método para podermos pegar mais de um elemento. A função `alterarContexto()` já passa o parâmetro que precisamos para alterar os elementos.

Dentro das chaves de `alterarContexto`, chamaremos a variável que acabamos de criar (`botoes`) e usaremos o `.forEach`, cujo parâmetro será uma `function` de parâmetro `contexto`.

Nesse `contexto`, usaremos o `.classList` novamente, mas acrescentando o `.remove('active')`.

```js
function alterarContexto(contexto) {
    botoes.forEach(function (contexto) {
        contexto.classList.remove('active')
})
```

Com isso, conseguimos remover a classe conforme o `contexto`. De volta ao VS Code, testaremos o código. Ao clicarmos em "Descanso curto" e em "Descanso longo", percebemos que cada um deles fica em destaque por vez.

Assim, usamos o método `classList()` para adicionar e remover classes. Ele não tem só essas duas funções, mas também o `contains` e o `toggle`. 

#### Desenvolvendo o temporizador
om o VS Code aberto, vamos acessar o arquivo `script.js` e criar uma variável que irá guardar esse valor do temporizador que será utilizado. Para isso, digitaremos `let` na linha 11 para declarar a variável `tempoDecorridoEmSegundos`, que receberá o valor `5`, correspondente a cinco minutos inicialmente.

```js
let tempoDecorridoEmSegundos = 5
```

##### Criando uma função de seta
Uma vez declarada a variável, podemos criar uma **função** para decrementar esse valor. Na linha 65, criaremos a função de seta, ou _arrow function_ (`() =>`), que ficará guardada em uma constante (`const`) chamada `contagemRegressiva`.
```js
const contagemRegressiva = () => {

}
```

No escopo dessa função, faremos a decrementação, ou seja, vamos reduzir o valor 5 da variável `tempoDecorridoEmSegundos`. Para isso, vamos chamar essa variável dentro da função seguida do sinal `-=` e do valor `1`.

Por fim, podemos imprimir isso com a função `console.log()`. Queremos conferir o valor do temporizador, então vamos digitar `Temporizador:` entre aspas simples, e fazer uma concatenação com a variável `tempoDecorridoEmSegundos`.
```js
const contagemRegressiva = () => {
    tempoDecorridoEmSegundos -= 1
    console.log('Temporizador: ' + tempoDecorridoEmSegundos)
}
```
> Concatenação é a junção de um dado do tipo _string_ com um dado do tipo JavaScript. O dado string é colocado entre aspas simples, e usamos o sinal de `+` para unir com a variável.

##### Referenciando a tag `<button>`
Queremos que essa função seja executada quando houver um clique no botão "Começar". Então, precisamos encontrar esse botão no código HTML. No arquivo `index.html`, identificamos que esse botão inicia na linha 65 e vai até a linha 68.

Vamos referenciar esse elemento de botão através do `id`, que é `start-pause`. Na linha 8 do arquivo `script.js`, criaremos uma constante chamada `startPauseBt`, que receberá o método `document.querySelector()` chamando o ID `#start-pause`.
```js
const startPauseBt = document.querySelector('#start-pause')
```

##### Criando um evento de clique
Agora que temos nosso botão referenciado, a partir disso, podemos criar um evento de clique. Para fazer isso com uma função que foi criada dentro de uma constante, precisamos chamá-la após ela ser escrita. Ou seja, não podemos fazer o evento de clique no topo do código.

Na linha 71, vamos chamar a variável `startPauseBt` que acabamos de declarar, seguida do método `addEventListener()`, que será um evento de `click`. Ao acontecer um clique, queremos que seja chamada a função `contagemRegressiva`.

```js
startPauseBt.addEventListener('click', contagemRegressiva)
```

Podemos salvar o código e testar isso. De volta à tela do Fokus, vamos acessar a aba de inspeção e ir até o console. Ao clicar no botão "Começar", teremos o retorno `Temporizador: 4`, decrementando do valor 5. Ao clicar novamente, o valor é reduzido para 3 (`Temporizador: 3`), e assim sucessivamente.

Porém, o temporizador deve ser **automatizado** e decrementar a cada 1 segundo. Precisamos adicionar isso ao nosso código.

##### Automatizando o temporizador
De volta ao código `script.js`, criaremos uma nova função chamada `iniciar()` na linha 73, para iniciar a contagem. Essa função irá receber uma variável, a qual será criada para trabalhar com o temporizador.
```js
function iniciar() {

}
```

Na linha 13, vamos declarar a variável `intervaloId` usando `let`, que receberá o valor `null` por padrão.
```js
let intervaloId = null
```

De volta à função `iniciar()`, vamos chamar a variável `intervaloId`, que receberá um método muito conhecido para executar alguma função ou algum código em determinado período: o `setInterval()`.

Esse método sempre espera receber dois parâmetros. O primeiro pergunta qual método queremos que seja executado; no nosso caso, queremos que seja executada a função `contagemRegressiva`, então vamos passá-la como primeiro parâmetro.

O segundo valor esperado é em quanto tempo queremos que isso seja executado; queremos a cada 1 segundo, então, passaremos `1000`, pois o valor é em milissegundos por padrão.

```js
function iniciar() {
    intervaloId = setInterval(contagemRegressiva, 1000)
}
```

Para que tudo funcione corretamente, precisamos associar a função `iniciar()` à função `contagemRegressiva`. Então, no escopo da função de seta, na linha 68, vamos chamar a função `iniciar()`.
```js
const contagemRegressiva = () => {
    iniciar()
    tempoDecorridoEmSegundos -= 1
    console.log('Temporizador: ' + tempoDecorridoEmSegundos)
}
```

##### Testando o código
Feito isso, vamos salvar o código e testá-lo. De volta à aplicação Fokus no navegador, ao clicar no botão "Começar", a contagem será feita no console.

Porém, se clicarmos mais de uma vez no botão, isso será executado várias vezes. Dessa forma, em poucos segundos, teremos a contagem avançado para valores negativos como -2000, -4000, e assim por diante. Essa é uma questão muito importante.

> Comentaremos a função `iniciar()` na linha 68 para parar a execução.

Quando utilizamos o método `setInterval()`, ele sempre irá executar algum método dentro de um período específico. Então, se não criarmos uma forma de interromper a execução, isso pode consumir muitos dados da nossa máquina e até mesmo travá-la.

#### Pausando o temporizador
Na linha de código 73 em `script.js`, dentro do evento de clique, chamamos a função `contagemRegressiva`. Porém, podemos chamar diretamente a função `iniciar`.
```js
startPauseBt.addEventListener('click', iniciar)
```

Em seguida, vamos apagar a linha 68, onde antes havíamos comentado a função `iniciar()` dentro da função `contagemRegressiva`. Teremos o seguinte resultado:
```js
const contagemRegressiva = () => {
    tempoDecorridoEmSegundos -= 1
    console.log('Temporizador: ' + tempoDecorridoEmSegundos)
}
```

De volta à aplicação no navegador, vamos clicar no botão "Começar" para conferir como está o temporizador. Ele começa normalmente, mas alcança números negativos. Nós precisamos **interromper a contagem** quando chegar a zero. Para isso, criaremos um método de verificação, de modo que quando o tempo chegar a zero, a execução do código seja interrompida.

##### Interrompendo a contagem do temporizador
No Visual Studio Code, podemos fazer essa verificação dentro da função `contagemRegressiva`. Na linha 68, vamos adicionar um bloco condicional `if`, que receberá entre parênteses a condição `tempoDecorridoEmSegundos <= 0`. Neste caso, queremos que aconteça uma ação específica. Dentro das chaves da condicional, vamos inserir um `alert()` com a string `Tempo finalizado!`.

Na linha abaixo, vamos utilizar o `return` para interromper o código.
```js
const contagemRegressiva = () => {
    if(tempoDecorridoEmSegundos <= 0){
        alert('Tempo finalizado!')
        return
    }
    tempoDecorridoEmSegundos -= 1
    console.log('Temporizador: ' + tempoDecorridoEmSegundos)
}
```
>Se não utilizarmos o `return`, mesmo com o tempo decorrido em segundos sendo menor ou igual a zero, será dado o alerta, mas continuará a execução, e não é isso que desejamos.

##### Testando o código
Vamos testar o código? Retornando ao navegador e clicando em "Começar" novamente, o temporizador inicia e, ao chegar a zero, um alerta aparece na tela, conforme esperado.

No entanto, ao confirmar o alerta clicando no botão "OK", ele continua a aparecer. Isso ocorre porque o temporizador está com o valor zero, então é entendido que, quando estiver com esse valor, deve continuar sendo enviado o alerta para a pessoa usuária.

Nós precisamos zerar esse valor, e para fazer isso, devemos zerar o `intervaloId`, que é o identificador de `tempoDecorridoEmSegundos`. Precisamos fazer com que ele seja nulo (`null`).

##### Criando a função `zerar()`
Para isso, criaremos uma nova função na linha 82, chamada `zerar()`. No escopo da função, vamos utilizar o método do JavaScript `clearInterval()`, que interrompe a execução do `intervaloId`.

Feito isso, vamos definir o `intervaloId` como `null`.
```js
function zerar() {
    clearInterval(intervaloId) 
    intervaloId = null
}
```

Criamos a função, mas ainda não a chamamos. O momento ideal para chamá-la é no escopo da função `contagemRegressiva`. Faremos isso dentro do bloco `if`, antes do `alert()`.

```js
const contagemRegressiva = () => {
    if(tempoDecorridoEmSegundos <= 0){
        zerar()
        alert('Tempo finalizado!')
        return
    }
    tempoDecorridoEmSegundos -= 1
    console.log('Temporizador: ' + tempoDecorridoEmSegundos)
}
```
Com isso, o temporizador consegue parar corretamente ao atingir o tempo zero.

##### Modificando a função `iniciar()`
A partir disso, podemos também pausar o nosso temporizador. Ao clicar em "Começar", queremos que seja possível clicar novamente no botão e interromper a execução.

Para pausar o temporizador, podemos modificar a função `iniciar()`. Na linha 80, faremos um bloco condicional: chamaremos o `if` recebendo entre parênteses `intervaloId`, indicando que se a variável tiver algum valor, podemos pausar a execução. Então, chamaremos a função `zerar()` configurada para definir o valor de `intervaloId`.

Ao final, usaremos o `return` para interromper a execução do código.
```js
function iniciar() {
    if(intervaloId){
        zerar()
        return
    }
    intervaloId = setInterval(contagemRegressiva, 1000)
}
```

##### Ajustando o nome da função

Vamos verificar uma questão de contexto sobre o nome da função. A função `iniciar()` na linha 79, não apenas inicia o temporizador, mas também o pausa. Portanto, podemos alterar seu nome para `iniciarOuPausar()`. Ajustaremos o nome também na linha 77.
```js
startPauseBt.addEventListener('click', iniciarOuPausar)
```

```js
function iniciarOuPausar() {
    if(intervaloId){
        zerar()
        return
    }
    intervaloId = setInterval(contagemRegressiva, 1000)
}
```