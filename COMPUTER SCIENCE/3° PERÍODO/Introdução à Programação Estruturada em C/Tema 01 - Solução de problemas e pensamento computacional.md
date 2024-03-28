---
tags:
  - C
curso: Faculdade
link do código: https://stecine.azureedge.net/repositorio/00212ti/00012/index.html#
---
## Módulo 01 -  Conceitos de solução estruturada

### Solução estruturada
O computador não tem discernimento para julgar culturalmente se algo é certo ou errado. No entanto, ele pode ser instruído para tomar decisões lógicas, baseadas em critérios objetivos, e seguir instruções ordenadas (**solução estruturada**).

Propor uma solução estruturada para um problema consiste em elaborar uma sequência de passos a serem dados, de forma que, ao seguir esta sequência, exista uma resposta coerente para esse problema. Já que os computadores podem seguir instruções adequadamente programadas para realizar certas tarefas, podemos concluir que eles têm comportamento previsível. Este fato nos permite prever o que determinado programa fará ao ser executado, caso tenhamos acesso ao conjunto de instruções que o gerou.

### Pensamento computacional
Aplicar o pensamento computacional é o primeiro passo para conseguir instruir o computador a executar determinada tarefa. De acordo com Grover e Pea (2013), o pensamento computacional tem nove elementos que o levam a atender alunos interdisciplinarmente, além de avaliar seu desempenho. São eles:
1. Abstração e reconhecimento de padrões;
2. Processamento sistemático da informação;
3. Noções de controle de fluxo em algoritmos;
4. Decomposição de problemas estruturados:
5. Sistema de símbolos e representações;
6. Pensamento iterativo, recursivo e paralelo:
7. Lógica condicional;
8. Eficiência e restrições de desempenho;
9. Depuração e detecção de erro sistemático.

De acordo com Brackmann (2017), o pensamento computacional tem quatro pilares para a resolução de problemas. São eles:
* **Decomposição**: A decomposição consiste em dividir o problema inicial em partes menores, permitindo que cada parte menor seja mais facilmente resolvida. Problemas não decomposto têm a resolução mais difícil de enxergar e desenvolver.
* **Reconhecimento de padrões**: O reconhecimento de padrões se caracteriza por identificar repetições ou regras de recorrência, aumentando a chance de se conhecer alguma solução para problemas similares.
* **Abstração**: A abstração consiste na filtragem e classificação dos dados, concentrando a atenção no que realmente é importante (BRACKMANN, 2017), permitindo que decisões sejam tomadas com maior qualidade. Por isso, ela pode ser vista como o pilar principal, além de ser utilizada em diversos momentos.
* **Algoritmos**: Os algoritmos são procedimentos para resolver um problema com as ações a serem executadas e a ordem em que elas devem acontecer.


#### Exercícios
1. Tendo em vista o pensamento computacional, qual das opções abaixo apresenta apenas pilares para este conceito? **Reconhecimento de padrões e algoritmos.**
2. O reconhecimento de padrões está presente em nossas vidas desde a educação básica. Pode-se afirmar que ele consiste em: **identificar repetições ou regras de recorrência.**



## Módulo 02 -  Ferramentas de soluções
### Fluxograma
Além dos algoritmos, o fluxograma é outra ferramenta bem útil para a representação de uma solução, e pode ser entendido como a representação gráfica de um algoritmo. É como se pudéssemos fazer um esquema, com regras simples, que represente a sequência de passos e condições que compõem um algoritmo. Fluxogramas também podem ser usados para representar sistemas ou processos.

Para utilizar corretamente o fluxograma, é necessário entender os seus principais componentes:
![[Pasted image 20240328114217.png]]


#### Exemplo
O critério para verificar se um número é par ou não é ser divisível por 2. Poderíamos pensar que ser divisível significa ter resto zero na divisão. Logo, um possível algoritmo para responder a um amigo se o número que ele falou é divisível por 2 ou não vem a seguir:

• Perguntar ao seu amigo o número que ele quer testar;  
• Ouvir a resposta dele;  
• Calcular o resto da divisão do número informado por 2;  
• Se o resto da divisão do número informado por 2 for zero, então: responder ao amigo que o número é par;  
• Se não for: responder ao amigo que o número é ímpar.

Um algoritmo que esteja organizado, como o exemplo que acabamos de ver, já está bem próximo do que precisamos fazer para instruir corretamente um computador a executar a tarefa. O algoritmo que usamos para responder a um amigo, se o número que ele falou é divisível por 2 ou não, pode ser representado pelo seguinte fluxograma:
![[Pasted image 20240328114408.png]]

![[Pasted image 20240328114421.png]]

Supondo que o usuário informe, no passo 3, o número 125. Qual será o resultado deste fluxograma? O número não é um quadrado perfeito”, uma vez que 125 não tem raiz inteira. Assim, na decisão 5, o caminho será da seta “não”.


#### Exercícios
1. Considere o fluxograma a seguir:
![[Pasted image 20240328114514.png]]

Suponha que o usuário tenha informado o valor 1,80 no passo 3 e o valor 70 no passo 5. Qual será o resultado deste fluxograma? **Será exibida a frase "você não está abaixo do peso.**

2. (FCC - 2016 - Adaptada) Considere o diagrama abaixo.
![[Pasted image 20240328115123.png]]

Analisando o raciocínio lógico e as estruturas lógicas utilizadas no diagrama, é correto afirmar que:
**a lógica implementa a solução de cálculo da média de 2 números diferentes de zero.**



## Módulo 03 -  Pseudocódigo e Portugol Studio

Pseudocódigo é uma linguagem artificial e informal que ajuda programadores a desenvolver algoritmos. O pseudocódigo parece com a forma natural que usamos para nos expressar, mas também tem semelhanças com uma linguagem de programação para um computador real. Assim, ele é útil para ajudar o programador a pensar na solução, mas não pode ser executado por uma máquina.

````
Pedir um número inteiro ao usuário;

Ler (a);

Pedir um número inteiro ao usuário;

Ler (b);
Se (a > = b)

    Imprimir a;

Senão

    Imprimir b.
````

Observação:  É muito comum utilizar o operador de atribuição, que em pseudocódigo, normalmente, é simbolizado pela seta (←). No Portugol Studio, que você vai conhecer na sequência, o operador é simbolizado pelo igual (=).

É importante perceber que o operador de atribuição não é uma igualdade. Ele atribui à variável do lado esquerdo o valor que está do lado direito. Ou seja, a linha:  
  
**a ← 10 (pseudocódigo) [ou a = 10 (no Portugol Studio)]**  
  
atribui o valor 10 à variável a.  
  
É usual escrevermos a instrução  
  
**a ← a + 1 (pseudocódigo) [ou a = a + 1 (no Portugol Studio)]**  
  
que causa estranheza no primeiro contato, mas simplesmente atribui à variável a o valor que ela tinha antes, acrescido de uma unidade. Ou seja, se as duas linhas acima estivessem em sequência, como a seguir:  
  
**a ← 10 (pseudocódigo) [ou a = 10 (no Portugol Studio)]**  
  
**a ← a + 1 (pseudocódigo) [ou a = a + 1 (no Portugol Studio)]**  
  
a variável a teria o valor 11 ao final da execução.

#### Exercícios
1. Observe o trecho de pseudocódigo a seguir:  
a ← 10  
b ← 15  
a ← a + b  
Imprimir (a)  
  
Determine a saída de um programa que fosse escrito com este trecho: **25**

2. Considere o seguinte programa, escrito em Portugol:
![[Pasted image 20240328115630.png]]
Na linha em que está escrito //TRECHO OMITIDO, deve ser inserida uma instrução que imprima na tela a seguinte frase: “O número digitado foi: ” seguida do valor que o usuário digitou. Ou seja, se o usuário tiver digitado o valor 1 quando foi solicitado, a frase impressa na tela deve ser O número digitado foi: 1 Para executar corretamente essa instrução, a linha omitida deve ser: **escreva ("o número digitado foi: numero")**
