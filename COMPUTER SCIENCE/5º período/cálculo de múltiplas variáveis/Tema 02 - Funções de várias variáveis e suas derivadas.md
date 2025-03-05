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



### 📌 **Relembrando o conjunto Rn

O conjunto Rn representa o **espaço n-dimensional** dos números reais.

🔹 Se n=1n = 1n=1, temos R, que é a reta real.  
🔹 Se n=2n = 2n=2, temos R2, que é o **plano cartesiano** (x1,x2).  
🔹 Se n=3n = 3n=3, temos R3, que é o **espaço tridimensional** (x1,x2,x3)  
🔹 Para n>3, não conseguimos visualizar, mas continua funcionando matematicamente.

Cada elemento do conjunto Rn é chamado de **n-upla**, ou seja, um conjunto ordenado de nnn números reais. Exemplo:

(2,−1,5)∈R3

Esse é um **vetor** com 3 componentes.

Agora, falamos sobre uma função que recebe um vetor de e retorna um valor em Rm:

*f:Rn→Rm*

Dependendo dos valores de n e m, teremos diferentes tipos de funções:

🔹 **Função escalar**: *f:Rn→R*
👉 A função recebe um vetor com n variáveis e retorna um número real. Exemplo: *f(x,y)=x2+y2*
Aqui, n=2 (entrada tem duas variáveis) e m=1 (imagem é um número real).

🔹 **Função vetorial**: *f:Rn→Rm* com *m>1*
👉 A função recebe um vetor e retorna outro vetor. Exemplo: *f(x,y)=(x+y,x−y)*
Aqui, *n=2* e *m=2*, pois a função retorna dois valores reais.


Essas são as possibilidades:

### 📌 **1. Funções Reais** *(f:R→R)*
🔹 A entrada e a saída são **números reais**.  
🔹 Exemplo:*f(x)=3x+5*

Se você colocar um valor x, a função retorna **apenas um número**.  
👉 Essas funções são estudadas no cálculo diferencial e integral de uma variável.

### 📌 **2. Funções Vetoriais** *(f:R→Rm)*
🔹 A entrada é um número real, mas a saída é **um vetor**.  
🔹 Exemplo: *f(t)=⟨t2+1,cos⁡t,5t⟩*

Isso significa que, para cada valor t, a função retorna um vetor com **3 componentes**.  
👉 Essas funções são muito usadas em Física para representar **trajetórias de partículas** no espaço.

### 📌 **3. Funções Escalares** *(f:Rn→R)*

🔹 A entrada é **um vetor** (várias variáveis), mas a saída é **um número real**.  
🔹 Exemplo: *f(x,y,z)=9xy*

Aqui, a entrada tem **três variáveis** (x,y,z) e a função retorna um **único valor real**.  
👉 Essas funções são usadas para modelar **temperatura, pressão, energia potencial, etc.**.

### 📌 **4. Campos Vetoriais** *(f:Rn→Rm)*

🔹 Tanto a entrada quanto a saída são **vetores**.  
🔹 Exemplo: *f(x,y,z)=⟨x+y,tan⁡x+2⟩*

Aqui, a entrada tem **3 variáveis** (x,y,z), e a saída é um vetor com **2 componentes**.  
👉 Campos vetoriais aparecem na Física para descrever **forças, campos elétricos e magnéticos**.

##### 📌 **Resumo Rápido**
| Tipo de Função      | Entrada    | Saída             | Exemplo                |
| ------------------- | ---------- | ----------------- | ---------------------- |
| **Função Real**     | x∈R        | y∈R (número real) | f(x)=3x+5              |
| **Função Vetorial** | t∈R        | Rm (vetor)        | f(t)=⟨t2+1,cos⁡t,5t⟩   |
| **Função Escalar**  | (x,y,z)∈Rn | R (número real)   | f(x,y,z)=9xy           |
| **Campo Vetorial**  | (x,y,z)∈Rn | Rm(vetor)         | f(x,y,z)=⟨x+y,tan⁡x+2⟩ |

# **Funções Escalares**
As **funções escalares** possuem diversas aplicações práticas, pois muitos fenômenos dependem de várias variáveis.
### 🔹 **Exemplos do cotidiano**:

- O **volume** de um recipiente depende do **raio e da altura**.
- A **temperatura** de uma região da Terra depende da **latitude, longitude e altura**.

Uma **função escalar** é definida como: *f:S⊂Rn→R* onde **S** é um subconjunto de *Rn*, com *n>1*.

### 🔹 **Variáveis**:
- **Variáveis independentes**: x1,x2,...,xn​.
- **Variável dependente**: y=f(x1,x2,...,xn).
Se o domínio **não for especificado**, considera-se o subconjunto de *Rn* que permite obter um número real pela equação da função.

#### 📝 Exemplo 1 – Determinação do domínio

Dada a função escalar:
![[Pasted image 20250305122310.png]]
Queremos determinar seu domínio.
##### Passo 1 – Condição para a raiz quadrada
Sabemos que a raiz quadrada só existe para números **maiores ou iguais a zero**:  *x + y - 2 ≥ 0 ⇒ x + y ≥ 2*
##### Passo 2 – Condição para o denominador
O denominador **não pode ser zero**: *x − y ≠ 0 ⇒ x ≠ y*
###### Domínio da função
*Dom(f)={(x, y)∈ R² ∣ x + y ≥ 2 e x ≠ y}*