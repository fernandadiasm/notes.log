---
tags:
  - C
curso: Faculdade
link do código:
---
## Módulo 1 -  Conceitos de tipos de dados

### Dados
#### Tipos de dados
Um algoritmo pode ser entendido como uma linha de produção fabril semelhante à do Fordismo, uma vez que transformamos os dados de entrada para alcançarmos ou calcularmos determinado valor.

Veja na imagem ao lado a representação do carregamento do código na linguagem C como uma linha de produção. Os espaços de memória recebem inputs (entradas) para transformá-los em códigos (saídas). Com a execução do código, esses espaços são preenchidos por variáveis que dão origem à linguagem de programação.

![[Pasted image 20240328121050.png]]

Para o cálculo do índice de massa corpórea (IMC) de uma pessoa, medimos sua altura e seu peso. Normalmente, ela é medida em metros e possui valores com casas decimais. Da mesma forma, ele o é em quilogramas, apresentando casas decimais. Suponhamos que essas medidas apresentem os seguintes números apresentados na imagem a seguir.

![[Pasted image 20240328121113.png]]


A representação em casas decimais de números tão comuns do nosso dia a dia também pode ser feita nas linguagens de programação.

Para desenvolver um algoritmo, precisamos:
1. Identificar quais dados de entrada serão utilizados e como representá-los em nossa linguagem de programação.
2. Fazer com esses dados já identificados as transformações necessárias para modificar ou realizar cálculos.

Da mesma forma que, para montar um carro, Ford iniciava o processo com uma carroceria a fim de poder agregar seus demais componentes, como portas, sistema de suspensão e motor, nós o começamos com uma região de memória na qual serão acrescentados os dados necessários para a realização do nosso cálculo.

Desde sua concepção, a linguagem C possui quatro tipos de dados básicos:

1. _char_;
2. _int_;
3. _float_;
4. _double_.

Por meio deles e de suas manipulações, é possível representar qualquer tipo de informação do mundo real.


##### char
O tipo _char_ representa um caractere (podendo ser uma letra, um número ou um símbolo) e ocupa um _byte_ na memória. Em computação, ele é representado pela tabela ASCII (Sigla para American Standard Code for Information Interchange) com seus 256 símbolos. 

![[Pasted image 20240328121326.png]]


Esses caracteres podem ser usados de diversas formas. Exemplo:
A representação dos termos masculino e feminino em um cadastro é feita pelos caracteres _M_ e _F_. Utilizam-se aspas simples para a sua representação quando ambos forem mostrados em uma implementação. Desse modo, o caractere **M** de **masculino** é representado por ‘_M_’ e o **F** de **feminino**, por ‘_F_’.

Observemos que a tabela ASCII representa os caracteres minúsculos e maiúsculos de forma distinta:  Assim, conforme pode ser visto, o ‘_m_’ (**m** minúsculo) é diferente de ‘_M_’ (**M** maiúsculo). Notemos também que, para cada caractere da tabela, existe um índice representado em decimal ou hexadecimal.


### Variáveis e constantes
#### Manipulação de variáveis e constantes
A variável é um tipo de espaço de memória que pode ser alterado a qualquer tempo. A constante, por sua vez, não pode. As duas formas permitem a referenciação deles em um espaço de memória. Esses espaços são identificados por meio de rótulos. Chamados de identificadores, eles possibilitam, a partir de seu uso, o acesso ao conteúdo armazenado em memória.

##### Definição das variáveis
Formalmente, um espaço de memória é rotulado por intermédio de um identificador quando as variáveis são definidas: 
![[Pasted image 20240328121600.png]]

Para criar uma variável, utiliza-se a seguinte notação:
![[Pasted image 20240328121612.png]]


O tipo do dado pode ser qualquer um dos quatro tipos já abordados: _char_, _int_, _float_ e _double_.

De acordo com o que vimos, como estaria descrita a representação dos valores de peso e altura?

```` c
float peso;
float altura;
````

Ainda podemos definir as variáveis com outro formato:
```` c
TIPO NOME_DO_IDENTIFICADOR_1, NOME_DO_IDENTIFICADOR_2;
````

Como estaria descrita, portanto, a representação dos valores de peso e altura?
```c
float peso, altura;
//OU
float altura, peso;
```

Também é possível estabelecer uma quantidade maior de variáveis separando-as sempre das demais pelo uso de vírgula, enquanto a última deve conter um ponto e vírgula para finalizar.

Recomendamos a definição de poucas variáveis por vez. Caso haja algum tipo de relação entre elas, essa identificação deve ser feita por meio de comentários.

Seguindo o exemplo do caso de peso e altura, faríamos assim:
```` c
float altura, peso;
//Valores de altura e peso do usuário,
//medidos em metros e quilograma,
//respectivamente.
````

Outro ponto importante é que uma variável sempre deve ser definida antes de seu uso. Assim, quando formos usar determinada variável, sua definição deverá ocorrer previamente.

Coloquialmente conhecidos como **nomes de variáveis**, os identificadores podem ter até 32 caracteres formados por:

1. Letras do alfabeto (maiúsculas e minúsculas);
2. Dígitos (0-9);
3. Símbolo de underscore _ .

O primeiro caractere deve ser uma letra do alfabeto ou o underscore.

**Não usamos caracteres acentuados ao definirmos um identificador.**


##### Aplicação dos conceitos apresentados
Da teoria da informação, surgem os conceitos de:

 * Dados: Considerado um valor sem contextualização.
 * Informação: Quando é contextualizado, o dado transforma-se em informação.

Hoje em dia, a informação é o principal fator de destaque em empresas vencedoras. A partir dos dados contextualizados, é possível compreender tudo à nossa volta. Afinal, eles dão origem a áreas que estão revolucionando o mercado nos últimos anos. Só será possível analisar os dados, entendendo suas correlações e regras de formação, se eles forem tratados da melhor forma à medida que estiverem sendo capturados no mundo real.

#### Exercícios
1. (Adaptada de: MPU - FCC - Analista de Informática - Desenvolvimento de Sistemas - 2007) O tipo de dados float refere-se aos dados do tipo: **Real, pois os dados do tipo float são dados com casas decimais.**
2. (Adaptada de: IBGC - Hemominas - Técnico de Informática - 2013) Assinale a alternativa que apresenta um exemplo típico de dados numéricos sem casas decimais: **558.**



## Módulo 2 -  Operadores matemáticos, lógicos, relacionais, atribuição e tabela verdade
### Manipulação de Dados e Operadores Matemáticos em C: Dominando as Operações Fundamentais.
#### Operadores
Essa manipulação é realizada de acordo com os operadores disponibilizados pela linguagem.
##### Operadores matemáticos
O objetivo dos operadores matemáticos é representar as operações matemáticas do mundo real. Suas operações possuem peculiaridades para os quatro tipos de dados diferentes (char, int, float e double) da linguagem.

Os números reais são representados na linguagem C pelos tipos float e double por apresentarem uma maior similaridade com o mundo real.

São ofertadas pela linguagem as seguintes operações:
1.  Soma: Representada pelo símbolo ‘+’
2. Subtração: Símbolo ‘-’ 
3. Multiplicação: Representada pelo símbolo ‘ * ’
4. Divisão: Símbolo ‘/’ .

Essas operações funcionam exatamente da mesma forma que no mundo real, possuindo como única diferença a precisão numérica calculada.

Mundo real: Os números podem possuir representação infinita.
No computador: Isso não é possível, pois, nesse ambiente, a representação é finita.

Desse modo, é possível ocorrer algum problema de precisão numérica ao serem realizados os cálculos matemáticos. Embora seja pouco significativo na maioria dos casos, esse problema acarreta uma decisão sobre o tipo de ponto flutuante utilizado, que pode ser o de precisão.
_float_ (simples) ou _double_ (dupla)

| Operação matemática | Símbolo utilizado | Exemplo   |         |
| ------------------- | ----------------- | --------- | ------- |
| Equação             | Resultado         |           |         |
| Soma                | +                 | 1.2 + 3.4 | 4.6     |
| Subtração           | -                 | 1.2 - 3.4 | -2.2    |
| Multiplicação       | *                 | 1.2 * 3.4 | 4.08    |
| Divisão             | /                 | 1.2 / 3.4 | -0.3529 |
Para os inteiros, números sem casa decimal, as diferenças começam a aparecer. As operações de soma, subtração e multiplicação funcionam essencialmente conforme já explicamos, considerando que os dois operandos sejam números inteiros.

Se um desses operadores for um número inteiro (_int_) e o outro, um real (_float_ ou _double_), seu resultado também será um número real (_float_ ou _double_, respectivamente).

Para a operação de divisão, quando os dois operandos são números inteiros, o resultado também é um inteiro. Portanto, essa operação é chamada de **divisão inteira**, embora ela use o mesmo símbolo utilizado para números reais.

##### Exemplo
Observe que 5 / 2 tem como resultado o número 2, ou seja, o maior inteiro que pode ser obtido dentro do resultado matemático – que, neste caso, seria 2,5.

Caso a operação de divisão envolva dois números – um real (_float_ ou _double_) e um inteiro (_int_) –, o resultado será um número real (_float_ ou _double_). Ainda existe outra operação que é particular de números inteiros: resto da divisão. Usando o símbolo _%_, ela retorna o resto da divisão de dois números inteiros.

##### Exemplo
Note que 5 % 2 tem como resultado o número 1.

Observemos mais um resumo do que aprendemos.
![[Pasted image 20240328122841.png]]

A divisão inteira dos números inteiros (_int_) a e b resulta no valor d e no resto c. Assim, os valores c e d podem ser obtidos por meio das seguintes equações:
  
d=a/b
c=a%b

##### Classificação
Perante a quantidade de operandos possíveis, os operadores podem ser classificados como:

1. Unários: Só possuem um operando. O operando dos operadores unários é chamado de **incremento** ou **decremento**. Esses operadores podem ser usados de forma pré-fixa ou pós-fixa. Nas duas situações, os valores são acrescidos (incremento) ou decrescidos (decremento) de uma unidade. Desse modo, a expressão **a++** ou **++a** calcula o valor **a+1**.
2. Binários: Possuem dois operandos.
3. Ternários: Possuem três operandos.

Todos os operadores apresentados até aqui são considerados BINÁRIOS, pois eles possuem dois operandos.

Vejamos esta tabela com um resumo do que foi exposto:

| Operação matemática | Símbolo utilizado | Exemplo |     |
| ------------------- | ----------------- | ------- | --- |
| Equação             | Resultado         |         |     |
| Soma                | +                 | 1 + 2   | 3   |
| Subtração           | -                 | 3 - 4   | -1  |
| Multiplicação       | *                 | 5 * 6   | 30  |
| Divisão inteira     | /                 | 5 / 2   | 2   |
| Resto da divisão    | %                 | 5 % 2   | 1   |
| Incremento          | ++                | 2++     | 3   |
| Incremento          | ++                | ++2     | 3   |
| Decremento          | --                | 2--     | 1   |
| Decremento          | --                | --2     | 1   |

Quando utilizados como operandos de operação matemática, os dados do tipo char são traduzidos para números inteiros, possuindo o mesmo funcionamento descrito anteriormente. Essa tradução é realizada graças ao uso da tabela ASCII apresentada no módulo 1.

##### Operadores relacionais
Os operadores relacionais permitem a realização de comparações entre valores. Elas são expressas por meio dos valores verdadeiro e falso.

Um dos tipos utilizados no desenvolvimento de algoritmos é o lógico. Ele modela a álgebra de Boole ou álgebra booleana, base para o desenvolvimento da eletrônica presente na computação. Nessa álgebra, são utilizados os valores verdadeiro e falso. Na linguagem C, não há um tipo de dado que represente tais valores diretamente. Essa representação ocorre pela interpretação do valor da variável. Assim, os valores 0, vazio ou _null_ são interpretados como falso; os outros, como verdadeiro. As operações são:
1. Menor: Expressa pelo símbolo '<'.< /p>
2. Maior: Símbolo '>'.
3. Menor ou igual: Combinação dos símbolos '<='.< /p>
4. Maior ou igual: Combinação dos símbolos '>='.
5. Igualdade: Combinação dos símbolos '== '.
6. Desigualdade: Combinação dos símbolos '!='.

Caso seja necessário verificar se uma pessoa tem mais de 1,90m de altura, o que podemos fazer?
Resposta: Devemos comparar os valores de altura da pessoa pela variável **a** e pelo valor de referência 1,90m. Na linguagem C, esse conhecimento é representado por: **a** > 1.9

Note que a unidade de medida não é expressa na equação. Caso fosse realizada a comparação anterior, seria necessário manter essa unidade.

Demonstraremos a seguir uma tabela com um resumo do assunto abordado:

| Operação matemática      | Símbolo utilizado     | Exemplo    | Exemplo        |
| ------------------------ | --------------------- | ---------- | -------------- |
| ------------------------ | --------------------- | Equação    | Resultado      |
| Maior                    | >                     | 1.2 > 3.4  | 0 (falso)      |
| Menor                    | <                     | 1.2 < 3.4  | 1 (verdadeiro) |
| Menor ou igual           | <=                    | 1.2 <= 3.4 | 1 (verdadeiro) |
| Maior ou igual           | >=                    | 1.2 >= 3.4 | 0 (falso)      |
| Igualdade                | ==                    | 1.2 == 3.4 | 0 (falso)      |
| Desigualdade             | !=                    | 1.2 != 3.4 | 1 (verdadeiro) |
##### Operadores lógicos
Eles possuem como operandos os tipos verdadeiro e falso apresentados anteriormente. Existem dois tipos de operadores lógicos: