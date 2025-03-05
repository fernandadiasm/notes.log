---
curso: Ciência da computação
tags:
  - CÁLCULO
---
### 📌 **O que são funções de múltiplas variáveis?**

Até agora, você deve estar acostumado com funções de **uma variável**, como:

f(x)=x2+3x+5f(x) = x^2 + 3x + 5f(x)=x2+3x+5

Aqui, o valor de saída (imagem) depende apenas de **uma** variável de entrada (xxx).

Mas na vida real, muitas coisas dependem de **várias** variáveis ao mesmo tempo. Por exemplo:  
🔹 A temperatura em um ponto de uma sala depende da posição (x,y,zx, y, zx,y,z).  
🔹 O lucro de uma empresa pode depender do preço de venda (xxx) e da quantidade vendida (yyy).

#### 🧩 **Como representar isso matematicamente?**

Chamamos essas funções de **funções escalares de várias variáveis**, porque elas recebem um **vetor** como entrada e retornam um número real. Exemplo:

f(x,y)=x2+y2f(x, y) = x^2 + y^2f(x,y)=x2+y2

Isso significa que, para cada ponto (x,y)(x, y)(x,y) no espaço, a função nos dá um valor numérico.

Outro exemplo mais realista:

T(x,y,z)=20−x2−y2−z2T(x, y, z) = 20 - x^2 - y^2 - z^2T(x,y,z)=20−x2−y2−z2

Isso poderia representar a **temperatura** TTT em um ponto (x,y,z)(x, y, z)(x,y,z) dentro de uma sala.

##### 📌 **Resumo rápido**

✅ Funções de múltiplas variáveis recebem **mais de uma variável** como entrada.  
✅ Elas podem representar fenômenos do mundo real, como temperatura ou lucro.  
✅ O domínio delas é um subconjunto de Rn\mathbb{R}^nRn (um espaço com nnn dimensões).



### 📌 **Relembrando o conjunto Rn\mathbb{R}^nRn**

O conjunto Rn\mathbb{R}^nRn representa o **espaço n-dimensional** dos números reais.

🔹 Se n=1n = 1n=1, temos R\mathbb{R}R, que é a reta real.  
🔹 Se n=2n = 2n=2, temos R2\mathbb{R}^2R2, que é o **plano cartesiano** ((x1,x2)(x_1, x_2)(x1​,x2​)).  
🔹 Se n=3n = 3n=3, temos R3\mathbb{R}^3R3, que é o **espaço tridimensional** ((x1,x2,x3)(x_1, x_2, x_3)(x1​,x2​,x3​)).  
🔹 Para n>3n > 3n>3, não conseguimos visualizar, mas continua funcionando matematicamente.

Cada elemento do conjunto Rn\mathbb{R}^nRn é chamado de **n-upla**, ou seja, um conjunto ordenado de nnn números reais. Exemplo:

(2,−1,5)∈R3(2, -1, 5) \in \mathbb{R}^3(2,−1,5)∈R3

Esse é um **vetor** com 3 componentes.