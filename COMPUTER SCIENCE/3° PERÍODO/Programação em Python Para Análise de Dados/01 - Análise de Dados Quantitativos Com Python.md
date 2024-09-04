---
tags:
  - PYTHON
  - DADOS
curso: Faculdade
link do código:
---
# Ferramentas de análise exploratória de dados
A análise exploratória de dados é a parte da estatística responsável pelo primeiro contato com as informações. Essa técnica nos dá um indicativo de como os dados estão distribuídos. Além disso, é útil na detecção de erros, de valores extremos (_outliers_), na verificação de suposições relacionadas à inferência estatística, na seleção preliminar de modelos estatísticos, entre outras utilidades.

 A seguir detalharei os principais conceitos e ferramentas para a exploração correta dos dados:
### Classificação das variáveis
Variáveis são características de interesse em um estudo qualquer. Elas podem ser classificadas de duas formas diferentes:
* **Quantitativas**: Quando assumem valores numéricos.
* **Qualitativas**: Quando seus possíveis valores não são numéricos.

Observe de forma resumida como as variáveis são classificadas:

![[Pasted image 20240514104022.png]]

### Conceitos básicos
Definição de alguns conceitos básicos:
* **População**: Conjunto de indivíduos ou objetos com pelo menos uma característica em comum.
* **Amostra**: Parte da população.
* **Dados brutos**: Conjunto de dados que não tem uma ordem aparente.
* **Rol**: Conjunto de dados que tem um ordenamento, seja crescente ou decrescente.
* **Amplitude total**: Diferença entre o maior e o menor valor observado no conjunto de dados.
* **Distribuição de frequência**: é o arranjo dos dados em classes com suas respectivas frequências absolutas.

## Distribuições de frequência
É uma das formas mais simples e úteis de resumir um conjunto de dados, uma vez que é a apresentação dos dados em classes para suas respectivas frequências absolutas. As classes são divisões dos valores da variável em estudo.

Exemplo: a distribuição de frequência a seguir representa as notas na disciplina de estatística em uma turma de 40 alunos

|**Classe (Notas)**|**_FI_**|**_fi%_**|
|---|---|---|
|0 ⊢ 2|1|2,5|
|2 ⊢ 4|5|12,5|
|4 ⊢ 6|12|30,0|
|6 ⊢ 8|15|37,5|
|8 ⊢ 10|7|17,5|
|Soma|40|100|

A próxima distribuição de frequência refere-se à quantidade de famílias que receberam auxílio escolar por número de filhos. Acompanhe:

|**Classe (N° de filhos)**|**_Fi_**|
|---|---|
|1|52|
|2|38|
|3|18|
|4|12|
|Soma|120|
### Elementos da distribuição de frequência
#### Limites de classe
São as várias formas de expressar os limites de classe em uma distribuição de frequência. O **limite à esquerda é chamado de limite inferior (Li)** e o **limite à direita é chamado de limite superior (Ls)** da classe. Confira alguns exemplos:
- **Li |---| Ls**: indica uma classe que é fechada à esquerda e à direita, em que os limites inferior e superior estão incluídos na classe.
- **Li |--- Ls**: indica uma classe que é fechada à esquerda e aberta à direita, ou seja, o limite inferior está incluído na classe, mas o limite superior não.
- **Li ---| Ls**: indica uma classe que é fechada à direita e aberta à esquerda, ou seja, o limite superior está incluído na classe, mas o limite inferior não.

Dentre os limites de classes apresentados, o mais utilizado é o da letra B, isto é, fechada à esquerda e aberta à direita.

#### Amplitude de classe (AC)
É a diferença entre o limite superior e o limite inferior da classe.

#### Ponto médio da classe (XI)
É a média aritmética entre o limite inferior e o limite superior da classe: 2 |---4. Logo o ponto médio dessa classe será:

![[Pasted image 20240514110234.png]]
No cálculo do ponto médio da classe (Xi), os limites superior e inferior são considerados, independentemente da classe ser fechada ou aberta nos limites Li ou Ls.


#### Frequência relativa (Fi%)
É a frequência relativa dada por: **𝑓𝑖%=𝐹𝑖/𝑛**, em que **𝑛=∑𝐹𝑖**. Confira um exemplo:

|**Classe (Notas)**|**_FI_**|**_fi%_**|
|---|---|---|
|0 ⊢ 2|1|2,5|
|2 ⊢ 4|5|12,5|
|4 ⊢ 6|12|30,0|
|6 ⊢ 8|15|37,5|
|8 ⊢ 10|7|17,5|
|Soma|40|100|
Observe que para obter a frequência relativa de cada classe, basta dividir a frequência absoluta de cada uma por n, que é o tamanho do conjunto de dados ou tamanho da amostra. Então:
![[Pasted image 20240514110402.png]]

#### Frequência acumulada (FAC)
É o acúmulo das frequências absolutas. A partir da primeira frequência, somam-se as respectivas frequências absolutas. Veja um exemplo:

|**Classe (Notas)**|**_FI_**|**_fi%_**|
|---|---|---|
|0 ⊢ 2|1|1|
|2 ⊢ 4|5|6|
|4 ⊢ 6|12|18|
|6 ⊢ 8|15|33|
|8 ⊢ 10|7|40|
|Soma|40|-|
Para a primeira classe, a frequência acumulada é igual à frequência absoluta. A partir daí, começamos a somar as frequências absolutas, de forma que a acumulada da segunda classe é a frequência absoluta da primeira classe mais a frequência absoluta da segunda classe, ou seja: 
![[Pasted image 20240514111322.png]]

Para determinar a frequência acumulada da terceira classe, somamos a frequência acumulada da segunda com a frequência absoluta da terceira, logo:
![[Pasted image 20240514111336.png]]

### Como construir uma distribuição de frequência
Muitas vezes, a distribuição dos dados é obtida de forma que estão simplesmente dispostos em rol ou mesmo como dados brutos, ou seja, sem ordem aparente.

Quando a quantidade de dados é muito grande, a melhor forma de apresentá-los é por meio de uma tabela.

No intuito de melhorar a apresentação, é comum dispor os dados em uma distribuição de frequência. Desse modo, vejamos algumas etapas práticas para construir essa distribuição:

1. **Determinar o número de classes (k)**: A fim de calcular o número de classes de uma distribuição de frequência, utilizaremos a seguinte fórmula:  **𝑘=√𝑛**. Nesse caso, n é o tamanho do conjunto de dados ou da amostra.

2. **Determinar a amplitude total (AT)**: A amplitude de classe é a diferença entre o maior e o menor valor no conjunto de dados.

3. **Determinar a amplitude de classe (Ac)**: A amplitude é obtida por: Ac = AT/k.

4. **Construção da distribuição de frequência**: A partir dos três elementos vistos nos passos 1, 2 e 3, iniciaremos a construção da distribuição de frequência pelo menor valor do conjunto de dados, que será o limite inferior da primeira classe.  A partir desse valor, acrescentamos a amplitude de classe para obter o limite superior da primeira classe. Esse limite superior da primeira classe será o limite inferior da segunda, independentemente do tipo de classe escolhida; o limite superior da segunda classe será o limite inferior da segunda somada à amplitude de classe; e o limite superior da segunda classe será o limite inferior da terceira e assim por diante.

É comum na última classe usarmos a classe fechada tanto no limite inferior como no limite superior. Por exemplo, o rol a seguir representa a altura (em centímetros) de 26 jogadores de uma equipe de futebol. Veja:  **160 165 166 168 170 170 172 174 175 175 175 178 180 180 182 183 185 185 187 188 188 190 191 195 198 200**
Então, vamos construir uma distribuição de frequência das alturas dos jogadores dessa equipe de futebol. É só acompanhar os passos adiante:

1.  Nesse caso, usaremos a regra de arredondamento e consideraremos k igual a 5, mas em alguns casos é interessante arredondar para cima, sempre verificando se a distribuição de frequência contempla todo o conjunto de dados. Temos, portanto, a equação:
![[Pasted image 20240514111951.png]]

2. Logo em seguida, temos: 
![[Pasted image 20240514112011.png]]

3. Depois, a equação será:
![[Pasted image 20240514112027.png]]

4. Por fim, construindo a distribuição de frequência, temos o seguinte resultado:

|**Classe (Alturas)**|**_Fi_**|
|---|---|
|160 ⊢ 168|3|
|168 ⊢ 176|8|
|176 ⊢ 184|5|
|184 ⊢ 192|7|
|192 ⊢ 200|3|
|Soma|26|

## Representações gráficas
* **Gráfico de barras ou colunas**: É o tipo de gráfico mais utilizado em geral, pois serve para representar quaisquer dados quantitativos. 
Exemplo: Considere a distribuição de frequência referente à quantidade de famílias que receberam auxílio escolar por número de filhos.

![](https://stecine.azureedge.net/repositorio/00212ti/07622/img/2.jpg)

* **Histograma**: É o gráfico típico da distribuição de frequência. A diferença desse gráfico para o gráfico de barras ou colunas se dá pelo fato de as colunas apresentarem-se justapostas, ou seja, sem espaçamento entre elas. Em geral, a abcissa desse gráfico é representada pelas classes e a ordem é representada pela frequência absoluta ou relativa. 
Exemplo: Considere a distribuição de frequência a seguir, que representa as notas na disciplina de estatística em uma turma de 40 alunos.

![](https://stecine.azureedge.net/repositorio/00212ti/07622/img/3.jpg)

* **Gráfico de linhas**: É o gráfico mais apropriado quando trabalhamos com uma série de tempo. 
Exemplo: Número de acidentes por mês ao longo de um ano.

![](https://stecine.azureedge.net/repositorio/00212ti/07622/img/4.jpg)

* **Setor**: É o gráfico mais apropriado quando trabalhamos com porcentagens. 
Exemplo: Em uma pesquisa de satisfação sobre determinado produto, 55% dos entrevistados disseram que estavam satisfeitos, 35% disseram que estavam insatisfeitos e 10% disseram que eram indiferentes.

![](https://stecine.azureedge.net/repositorio/00212ti/07622/img/5.jpg)

* **Caixa (boxplot)**: É um dos gráficos mais utilizados atualmente, visto que traz várias informações sobre o conjunto de dados. Com esse gráfico é possível verificar a tendência central, a variabilidade e a simetria da distribuição dos dados, conceitos esses que serão vistos de forma mais detalhada posteriormente.  
  Outra vantagem desse gráfico é que podemos observar a presença de valores atípicos (_outliers_). Para isso é necessário determinar o intervalo interquartil (IQR), que é a diferença entre o 3º e o 1º quartil. Multiplicando esse IQR por 1,5, obtemos a faixa interquartil. Quando subtraímos o 1º quartil dessa faixa e somamos o 3º quartil a esta, encontramos o intervalo no qual seria comum a variação dos dados. Valores acima desse intervalo são considerados _outliers_.  
Exemplo: Considere os dados referentes aos preços de aluguéis de imóveis (em reais) em certo bairro do Rio de Janeiro: 1000 1500 1800 2000 2200 2500 2600 3000 3500 7000

![](https://stecine.azureedge.net/repositorio/00212ti/07622/img/6.jpg)]

Observe que, nesse gráfico, temos informações sobre o primeiro e o terceiro quartis, a mediana e a média. Os traços abaixo do primeiro quartil e acima do terceiro representam o menor e o maior valor dentro do intervalo normal de variação dos dados.  
  
Como vimos, o IQR é calculado subtraindo o terceiro quartil do primeiro, que, nesse caso, é igual a 1400. Note que a faixa interquartil (1,5IQR) é igual a 2100; logo, se somarmos o terceiro quartil a essa faixa interquartil, temos o valor limite (5225), que seria considerado normal para variação dos aluguéis. No entanto, como o aluguel de R$7.000,00 reais está acima de R$5.225,00, podemos dizer que se trata de um valor atípico.

###### Questões
1. Considere dados sobre o peso de navios. Essa variável é classificada em: **Quantitativa contínua.**
2. Analisando as alternativas a seguir, qual das alternativas é falsa? 
3. Dados sobre atendimentos médicos por faixa etária foram coletados e organizados na seguinte distribuição de frequência:

| **Classes** | **0 ⊢ 10** | **10 ⊢ 20** | **20 ⊢ 40** | **40 ⊢ 80** | **Soma** |
| ----------- | ---------- | ----------- | ----------- | ----------- | -------- |
| **_Fi_**    | 280        | 320         | 180         | 220         | 1000     |
Dito isso, determine o ponto médio da terceira classe: **30**, pois a terceira classe tem limite inferior e limite superior de classe, respectivamente igual a 20 e 30. Portanto, como o ponto médio da classe é a média aritmética entre os limites inferior e superior, temos que Xi é igual a 30.

4. Considerando a questão anterior, qual a frequência acumulada da terceira classe? **780**, Para determinar a frequência acumulada da terceira classe, lembre-se de que, para a primeira classe, a frequência acumulada é igual à frequência absoluta. A partir daí, começamos a somar as frequências absolutas, de forma que a frequência acumulada da segunda classe é a frequência absoluta da primeira classe mais a frequência absoluta da segunda classe, ou seja:
![[Pasted image 20240514113257.png]]
Para determinar a frequência acumulada da terceira classe somamos a frequência acumulada da segunda classe com a frequência absoluta da terceira classe, ou seja:
![[Pasted image 20240514113346.png]]

5. Julgue as alternativas a seguir e assinale a alternativa verdadeira: **O histograma é o gráfico típico da distribuição de frequência.**

6. De acordo com o diagrama de caixa a seguir, julgue a alternativa verdadeira: **O primeiro quartil é aproximadamente 16.**
![](https://stecine.azureedge.net/repositorio/00212ti/07622/img/7.jpg)


7. O conjunto de dados, a seguir, representa o número de horas extras mensais trabalhadas por 17 funcionários de um banco de investimentos: **10 12 12 14 15 16 16 18 19 20 20 21 24 24 25 28 30**. Dito isso, organize os dados em uma distribuição de frequência.

![[Pasted image 20240514115547.png]]


8. Dados sobre evasão escolar em determinado município estão exibidos na distribuição de frequência a seguir. Veja:

|**Classes**|**0 ⊢ 6**|**6 ⊢ 10**|**10 ⊢ 14**|**14 ⊢ 17**|**Soma**|
|---|---|---|---|---|---|
|**_Fi_**|20|44|64|72|200|
Agora, determine a amplitude entre as frequências relativas: Observe que, inicialmente, devemos determinar as frequências relativas com base nos dados da distribuição de frequência. Lembre-se de que a frequência relativa para cada classe é dada por: fi% = fi/n = 100

|**Classes**|**0 ⊢ 6**|**6 ⊢ 10**|**10 ⊢ 14**|**14 ⊢ 17**|**Soma**|
|---|---|---|---|---|---|
|**_Fi_**|20|44|64|72|200|
|**_f1%_**|10|22|32|36|100|

Como desejamos a amplitude entre as frequências relativas, basta calcular a diferença entre a maior e a menor frequência relativa. Assim, a amplitude entre as frequências relativas é igual a 36-10=**26**.

9. Considerando novamente a distribuição de frequência da questão anterior:

|**Classes**|**0 ⊢ 6**|**6 ⊢ 10**|**10 ⊢ 14**|**14 ⊢ 17**|**Soma**|
|---|---|---|---|---|---|
|**_Fi_**|20|44|64|72|200|
Qual o gráfico mais apropriado para representar esse conjunto de dados? **Histograma**, pois o gráfico que representa os dados em distribuição de frequência é o histograma, que nada mais é do que um gráfico de barras justapostas, cujas classes se encontram ao longo do seu eixo horizontal (abcissa) e as frequências absolutas ou relativas são apresentadas no eixo vertical (ordenada).

# Medidas de posição ou tendência central
São medidas que visam representar os fenômenos por seus valores centrais, em torno dos quais tendem a concentrar-se os dados. Apresentaremos essas medidas de acordo com os conceitos vistos anteriormente, ou seja, considerando que os dados podem se apresentar de duas formas distintas:

* Agrupados: Quando estão dispostos em uma distribuição de frequência.
* Não agrupados: Quando estão dispostos em rol ou dados brutos.

## Média (X)
### Para dados não agrupados
Média é a medida de posição mais conhecida e mais usada na prática para verificar o comportamento central dos dados. Quando os dados estão dispostos como dados brutos ou rol, a média é definida por:
![[Pasted image 20240514120554.png]]

Por exemplo, vamos determinar a média para o seguinte rol de dados: 1, 2, 3, 4, 5. Nesse caso, sua solução será: a média é igual a 3.
![[Pasted image 20240514120611.png]]

### Para dados agrupados
Quando os dados se apresentam em distribuição de frequência, a média é definida por:
![[Pasted image 20240514120643.png]]

Em que:
- 𝑋𝑖 é ponto médio da classe i.
- 𝐹𝑖 é a frequência absoluta da classe i.
- n é o tamanho do conjunto de dados ou da amostra.

### Exemplo
os dados sobre o peso (em kg) de recém-nascidos de certa maternidade, dispostos na seguinte distribuição de frequência:

|**Classe**|**_Fi_**|
|---|---|
|2,0 ⊢ 2,5|2|
|2,5 ⊢ 3,0|4|
|3,0 ⊢ 3,5|7|
|3,5 ⊢ 4,0|5|
|4,0 ⊢ 4,5|5|
|4,5 ⊢ 5,0|7|
|Soma|30|
Como resolução, veja que, para calcular a média para dados agrupados, usamos a expressão:
![[Pasted image 20240514120643.png]]
Dessa forma, precisamos determinar o produto de 𝑋𝑖𝐹𝑖. Assim, podemos utilizar a própria distribuição de frequência acima para obter esse produto. Então:

| **Classe** | **_Fi_** | **_Xi_** | **_Xi_,_Fi_** |
| ---------- | -------- | -------- | ------------- |
| 2,0 ⊢ 2,5  | 2        | 2,25     | 4,5           |
| 2,5 ⊢ 3,0  | 4        | 2,75     | 11            |
| 3,0 ⊢ 3,5  | 7        | 3,25     | 22,75         |
| 3,5 ⊢ 4,0  | 5        | 3,75     | 18,75         |
| 4,0 ⊢ 4,5  | 5        | 4,25     | 21,25         |
| 4,5 ⊢ 5,0  | 7        | 4,75     | 33,25         |
| Soma       | 30       | -        | 111,5         |
Portanto, a média é calculada como:
![[Pasted image 20240514121035.png]]
Logo, a média do peso dos recém-nascidos dessa maternidade é de aproximadamente 3,72 kg.

## Mediana (MD)
### Para dados não agrupados
Disposto o conjunto de dados em ordem crescente ou decrescente, a mediana é o elemento que ocupa a posição central, isto é, divide o conjunto de dados em duas partes iguais, de forma que metade dos dados está acima e a outra metade está abaixo da mediana.
Para o cálculo da mediana para dados não agrupados, atente-se nestes dois fatores:
1. Se o tamanho da amostra é ímpar ou par.
2. Se é referente ao elemento mediano, que é o elemento que nos dá a posição ocupada pela mediana.

**Se n é ímpar**: 
![[Pasted image 20240514121600.png]]

**Se n é par**: 
![[Pasted image 20240514121614.png]]

### Para dados agrupados
1. Determinar o elemento mediano: EMd = n/2
2. Determinar a classe mediana (𝐶𝑀𝑑), que é a classe que contém o elemento mediano.
3. Aplicar a fórmula:
![[Pasted image 20240514121744.png]]

Em que:  
𝐿𝑀𝑑= limite inferior da classe mediana.  
𝐹𝑎𝑎𝑐= frequência acumulada anterior à classe mediana.  
𝐹𝑀𝑑= frequência absoluta da classe mediana.  
ℎ= amplitude da classe mediana (diferença entre as amplitudes de classe superior e inferior).

Considerando os dados dos pesos dos recém-nascidos na tabela adiante, vamos determinar o valor da mediana.

|**Classe**|**_Fi_**|
|---|---|
|2,0 ⊢ 2,5|2|
|2,5 ⊢ 3,0|4|
|3,0 ⊢ 3,5|7|
|3,5 ⊢ 4,0|5|
|4,0 ⊢ 4,5|5|
|4,5 ⊢ 5,0|7|
|Soma|30|
Vimos que, para calcular a mediana, é necessário obter a classe mediana. Dessa forma, para determinar quem é a classe mediana, é necessário obter a frequência acumulada (Fac) para cada classe. Para determinar as frequências acumuladas de cada classe, basta ir acumulando (somando) as frequências absolutas.

|**Classe**|**_Fi_**|**_Fac_**|
|---|---|---|
|2,0 ⊢ 2,5|2|2|
|2,5 ⊢ 3,0|4|6|
|3,0 ⊢ 3,5|7|13|
|3,5 ⊢ 4,0|5|18|
|4,0 ⊢ 4,5|5|23|
|4,5 ⊢ 5,0|7|30|
|Soma|30|-|
Seguindo os passos para o cálculo da mediana para dados agrupados, devemos:

*  Determinar o elemento mediano

Note que esse elemento mediano ocupa a décima quinta posição no conjunto de dados.  
  
𝐸𝑀𝑑=30/2=15

* Determinar a classe mediana (𝐶𝑀𝑑)

É a classe que contém ∘𝐸𝑀𝑑.  
  
A classe que contém o elemento mediano é a quarta classe, visto que ela contém o décimo quinto elemento.

Note ainda que essa classe mediana (𝐶𝑀𝑑) contém do décimo quarto ao décimo oitavo elemento. Observe:
![](https://stecine.azureedge.net/repositorio/00212ti/07622/img/8.jpg)

Sendo assim, a formula é:
![[Pasted image 20240514121950.png]]

Por isso, a mediana do peso dos recém-nascidos é igual a 3,7 kg. A interpretação da frequência acumulada é feita desta forma: note que na primeira classe, temos o primeiro e o segundo elementos do conjunto de dados, pois os dados estão em ordem crescente, conforme definição de mediana.