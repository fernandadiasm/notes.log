---
tags:
  - NETWORKING
curso: Faculdade
link do código: https://stecine.azureedge.net/repositorio/00212ti/00016/index.html#
---
# Divisão da estrutura das redes em camadas
## Arquitetura em camadas
### Modelo em camadas
*A internet é um conjunto de redes de computadores que permite a troca de informações entre dispositivos computacionais. Para que essa troca seja realizada de forma eficiente, devem ser estabelecidas regras de comunicação. Essas regras são os protocolos de rede*,  que devem garantir que a comunicação ocorra de forma confiável, segura, eficaz, no momento certo e para a pessoa certa.

São muitas regras que devem ser implementadas para garantir a efetividade da comunicação, tornando o processo de troca de dados entre computadores uma tarefa extremamente complexa. Por causa dessa complexidade, os engenheiros e projetistas de redes do passado pensaram em formas de facilitar o desenvolvimento das regras nos dispositivos computacionais. Eles utilizaram um princípio básico de resolução de diversos outros problemas: a técnica de **dividir para conquistar**.

-- Na técnica dividir para conquistar, os projetistas dividem o problema em problemas menores e resolvem cada um de forma isolada. Se cada pequeno problema for resolvido, o grande problema será resolvido.

Para que essa divisão ocorresse de forma simplificada, os projetistas dividiram a organização das redes de computadores em camadas, sendo cada camada responsável por cuidar de determinada regra ou protocolo necessário ao processo de comunicação.  
  
A quantidade de camadas utilizadas depende de como as funcionalidades são divididas. Quanto maior a divisão, maior o número de camadas que serão empilhadas, numerando da mais baixa, camada 1, para a mais alta, camada n.

![[Pasted image 20240318150426.png]]
As camadas se inter-relacionam da seguinte maneira: a camada superior utiliza os serviços oferecidos por outra imediatamente inferior, portanto, a **camada 3** utiliza os serviços oferecidos pela **camada 2**.  
  
De forma contrária, podemos dizer que a camada inferior oferece serviços para outra imediatamente superior, logo, a **camada 2** oferece serviços para a **camada 3**.


### Elementos da camada
As camadas são formadas por três elementos principais:

* **Serviço**: É o conjunto de funcionalidades que uma determinada camada oferece. Por exemplo, uma camada pode ser responsável pela verificação de erros na transmissão, por determinar o endereço de um computador, entre outras funcionalidades. O serviço diz o que a camada faz e não como ela faz.
* **Protocolo**: Responsável por como a camada faz. Assim, o protocolo é a implementação do serviço da camada, ou seja, executa as regras para que os erros possam ser corrigidos ou para que um computador possa ser identificado. "Um conjunto de camadas e protocolos é a arquitetura de rede e o conjunto de protocolos utilizados por determinado sistema é uma pilha de protocolos." (TANENBAUM, 2011, p. 38)
* **Interface**: Para que uma camada possa utilizar a camada imediatamente inferior, é necessário que haja um ponto de comunicação entre ambas, chamado interface. Por meio dela, uma camada pode utilizar o serviço de outra, passando informações para a camada vizinha.

### Os elementos da camada
Onde, exatamente, tudo isso é implementado no computador?  
  
O que está implementado são os **protocolos e interfaces**, que podem estar desenvolvidos em um hardware, como uma placa de rede, ou em um software, como no sistema operacional da máquina.  
  
Agora que os elementos da camada foram apresentados, é possível entender dois conceitos importantes da arquitetura de redes: **Comunicação Vertical e Comunicação Horizontal**.

## Comunicações horizontal e vertical
Já vimos que uma camada utiliza os serviços de outra imediatamente inferior, sucessivamente, até chegar à camada mais baixa. Como estão empilhadas, podemos fazer analogia à **comunicação vertical**, uma vez que o **dado original, no topo do conjunto de camadas, desce até a camada 1**, caracterizando a verticalidade desse processo.

![[Pasted image 20240318150752.png]]

Conforme o dado passa por determinada camada, o hardware ou o software, responsável por implementar o protocolo, irá preparar esse dado para que a regra (para a qual ele foi projetado) possa ser executada.  
  
Se a camada 2 é responsável pela verificação de erro, o dado será preparado na origem por essa camada para que, ao passar pela camada 2 do destino, seja verificado se houve erro ou não.  
  
No exemplo anterior, vimos que a camada 2 de origem preparou o dado para que a camada 2 de destino verificasse se a informação está correta, caracterizando a existência de uma conversa entre as duas camadas de mesmo nível em computadores distintos. Essa conversa é a **comunicação horizontal, realizada pelos protocolos que implementarão a regra**.

![[Pasted image 20240318150822.png]]

## Encapsulamento
Como a camada 2 da máquina de origem consegue conversar com a mesma camada na máquina de destino?  
  
A comunicação horizontal ocorre de forma virtual. A camada 2 da máquina de origem, ao preparar o dado para ser enviado, adiciona informações que serão lidas e tratadas única e exclusivamente pela mesma camada do dispositivo de destino. Essas informações são denominadas **cabeçalhos**.
![[Pasted image 20240318145837.png]]
Cada camada adicionará um novo cabeçalho ao dado que será enviado, e esse processo é chamado de **encapsulamento**.  
  
Cada camada receberá o dado da camada superior, através da interface, e adicionará seu próprio cabeçalho, encapsulando o dado recebido.
![[Pasted image 20240318145852.png]]
Nesse processo, quando determinada camada recebe os dados, ela não se preocupa com o conteúdo que recebeu, apenas adiciona o seu cabeçalho para permitir que o protocolo execute as regras necessárias à comunicação.  
  
Esse procedimento acontece, repetidamente, até alcançar a camada 1 e a informação ser transmitida ao destino, onde ocorrerá o processo inverso. A informação subirá, desencapsulando as informações, da camada 1 até o usuário do serviço.

> Após analisar o conceito de arquitetura de camadas e ver o processo de encapsulamento, é possível deduzir que a grande desvantagem é o acréscimo de informações ao dado original, aumentando o volume de tráfego.  Entretanto, essa desvantagem é mínima comparada às vantagens que temos de modularização, facilidade de manutenção e atualização dos protocolos, que permitiram uma enorme evolução na área de redes.

# Camadas do modelo OSI
## Modelo OSI
Na década de 1970, a International Organization for Standardization (ISO), um órgão que desenvolve padrões internacionais, criou um modelo de referência de camadas denominado OSI (_Open System Interconnection_ - **ISO/IEC 7498-1:1994**).

O objetivo foi elaborar um modelo que permitisse a comunicação entre sistemas diferentes, **independentemente de suas arquiteturas**, facilitando a comunicação, sem a necessidade de realizar mudanças na lógica do hardware ou software (FOROUZAN, 2010).

>Observe que o modelo OSI propriamente dito não é uma arquitetura de rede, pois não especifica os serviços e protocolos exatos que devem ser usados em cada camada. Ele apenas informa o que cada camada deve fazer. No entanto, a ISO também produziu padrões para todas as camadas, embora esses padrões não façam parte do próprio modelo de referência. Cada um foi publicado como um padrão internacional distinto. O modelo (em parte) é bastante utilizado, embora os protocolos associados há muito tempo tenham sido deixados de lado. (TANENBAUM, 2011, p. 45)

O que utilizamos hoje do **modelo OSI é a referência para as funções das camadas**. Então, quando ouvimos falar que determinado protocolo é da camada X (1, 2, 3, ...), esse X se refere ao OSI, tanto que é encontrada, em diversos livros e artigos, a expressão modelo de referência OSI (RM-OSI em inglês).

O **modelo OSI possui sete camadas**, de cima para baixo: **aplicação, apresentação, sessão, transporte, rede, enlace e física**.  
  
De acordo com o conceito de camadas que estudamos, cada uma delas é responsável por determinada tarefa no processo de transmissão de dados. Entretanto, já sabemos que, por mais que tenham sido especificados protocolos para cada camada, na prática, eles não são utilizados.

![[Pasted image 20240318151041.png]]

Os conceitos estudados de comunicação vertical, comunicação horizontal e encapsulamento são válidos nesse modelo. Portanto, um dado transmitido por um dispositivo de origem será inserido na estrutura de rede a partir da camada de aplicação e descerá até a camada física, quando será enviado pelo meio de transmissão. Cada camada adicionará o seu próprio cabeçalho, encapsulando a PDU da camada superior e permitindo a comunicação horizontal entre camadas de mesmo nível.

![[Pasted image 20240318151051.png]]

É possível dividir as sete camadas em três subgrupos.

* **Camadas mais altas**:  As três camadas mais altas (aplicação, apresentação e sessão) estão relacionadas a funções que dão suporte para que os usuários possam acessar os diversos serviços de redes, garantindo a interoperabilidade de sistemas heterogêneos (FOROUZAN, 2010).
* **Camadas mais inferiores**: As três camadas mais inferiores (rede, enlace e física) estão relacionadas às operações ligadas aos aspectos da movimentação dos dados de um dispositivo para o outro, dando suporte às operações de rede (FOROUZAN, 2010).
* **Camadas de transporte**: A camada de transporte faz a interligação entre o suporte ao usuário e o suporte de rede. Ela vai permitir que os dados que chegaram das camadas mais baixas estejam em condições de serem utilizados pelas camadas mais altas (FOROUZAN, 2010).

![[Pasted image 20240318151206.png]]
## Camadas de aplicação, apresentação e sessão
### Aplicação

A camada de aplicação é a que está **mais próxima de nós, usuários da rede**. Podemos citar algumas das aplicações oferecidas por essa camada:

- Serviço web.
- Serviço de correio eletrônico.
- Serviço de transferência de arquivos.
- Serviço de streaming de áudio e vídeo.
- Serviço de compartilhamento de arquivos.

Os serviços citados acima ou quaisquer outros oferecidos pela camada de aplicação são executados por processos dos usuários que estão em andamento em determinado dispositivo.

Sua **segunda tarefa** será traduzir, criptografar e comprimir dados. Organização é a palavra-chave!

### Apresentação

A camada de apresentação é responsável por **garantir a interoperabilidade dos sistemas** heterogêneos, ou seja, permitir que, independentemente do dispositivo que você esteja utilizando (computador, smartphone, televisão, carro etc.) e do sistema operacional (MS Windows, Apple IOS, Linux etc.), seja possível acessar qualquer tipo de serviço disponibilizado pela rede.  
  
Para que haja essa interoperabilidade, a camada de apresentação é responsável por fazer a transformação dos dados, por isso, podemos chamá-la de **tradutor da rede**. Ela será responsável pela conversão entre formatos, compressão de dados e criptografia.  
  
Sua **terceira tarefa** será estabelecer, gerenciar e encerrar sessões, garantindo a sincronia da comunicação.

### Sessão

Essa camada é responsável por organizar a **comunicação entre os dispositivos** e permitirá que os usuários, em diferentes máquinas, possam estabelecer sessões de comunicação; cada sessão terá dois serviços básicos: **controle de diálogo e sincronização**.

* Controle de diálogo: Define quem transmitirá em determinado momento. Considerando a existência de dois usuários, A e B, a camada de sessão determinará se eles podem transmitir simultaneamente, caracterizando a comunicação _full duplex_, ou de forma intercalada, em um sentido por vez, a exemplo da comunicação _half duplex_.
* Sincronização: Permite que sejam estabelecidos pontos de controle em determinado fluxo de dados. Esses pontos permitem que, se houver uma perda de comunicação, a transmissão de dados seja restabelecida a partir daquele ponto e não desde o início da transmissão.

## Camadas de transporte e rede

### Transporte
Essa camada tem por finalidade **garantir a entrega de processo a processo de todos os dados enviados pelo usuário**. Podemos dizer que a camada de transporte é responsável por entregar os dados corretamente para os processos que estão em execução na camada de aplicação.  
  
Esse papel da camada de transporte a torna uma das **mais complexas** dentro da estrutura do modelo OSI. Para garantir que as mensagens da camada de aplicação sejam entregues corretamente, diversas funções são necessárias:

* **Segmentação e remontagem**: A camada de transporte receberá os dados originados na camada de sessão (PDU da camada de sessão) e irá dividi-los em pedaços, **segmentos** de dados (PDU da camada de transporte), que possam ser enviados e, na camada de transporte de destino, irá remontá-los na ordem correta. Para isso, será necessário estabelecer números de sequência para garantir que, independentemente da ordem de chegada, os dados sejam remontados na ordem correta.
* **Controle de erros fim a fim**: A camada de transporte verificará se ocorreram erros na comunicação fim a fim, ou seja, entre os processos da camada de aplicação. Na origem, serão adicionadas informações que permitam identificar no destino se durante o tráfego pela rede ocorreu algum erro e, possivelmente, corrigi-lo.
* **Controle de fluxo**: A camada de transporte será encarregada de evitar que o processo na origem sobrecarregue o processo no destino.
* **Controle de conexão**: A camada de transporte pode ser orientada ou não à conexão. No serviço orientado à conexão, a camada de transporte será responsável por estabelecer a conexão entre os processos de origem e destino.
* **Endereçamento do ponto de acesso ao serviço**: Em um dispositivo, normalmente, estão em andamento diversos tipos de serviços executados por vários processos e não apenas um. A camada de transporte será responsável por fazer a entrega para o processo correto e, para isso, será utilizado o chamado endereço de porta. Ele indicará o serviço correto que deverá receber os dados.
* **Controle de congestionamento**: No mundo real, as máquinas não estão diretamente conectadas, ou seja, não há uma comunicação ponto a ponto direta. Entre a máquina de origem e de destino existem diversos outros dispositivos cuja finalidade é fazer a informação ir de um ponto a outro. Como esses equipamentos transmitirão dados de diversas outras origens, poderá haver uma sobrecarga desses dispositivos. A camada de transporte será responsável por monitorar esse congestionamento e, possivelmente, tratá-lo.

### Rede
A camada de rede é responsável por **determinar o caminho da origem até o destino**. Ela receberá os **segmentos** gerados pela camada de transporte e, no cabeçalho da camada de rede, irá inserir o endereço da máquina de destino para que seja enviado pela rede por meio dos diversos dispositivos intermediários. Enquanto a camada de transporte é responsável pela comunicação processo a processo, a camada de rede é encarregada da **comunicação máquina a máquina**.  
  
Veja a representação desse fluxo a seguir (Comparação entre camada de transporte e camada de rede.):
![[Pasted image 20240318151613.png]]
Para cumprir nosso objetivo, duas funcionalidades principais devem ser estabelecidas:
* Endereço lógico: O endereço da porta, definido pela camada de transporte, permitirá a entrega no processo de destino. Mas, para que isso aconteça, é necessário que os **segmentos** cheguem à máquina de destino. Por isso, são empregados endereços lógicos a fim de permitir que os dispositivos intermediários encaminhem os dados pelas redes e alcancem o destino.
* Roteamento: A função de roteamento permite estabelecer um caminho entre origem e destino. Os dispositivos intermediários verificarão o endereço lógico de destino e, com base nas informações de caminho que eles possuem, farão o processo de encaminhamento para outros dispositivos intermediários a fim de alcançar o destino da informação.

## Camadas de enlace e física

### Enlace
A camada de rede tem a responsabilidade da **entrega dos dados para a máquina de destino**. Normalmente, as máquinas não estão diretamente conectadas, ou seja, origem e destino não estão ligados diretamente por um meio físico, mas por dispositivos intermediários, como a internet. Então, como visto na camada de rede, os dados serão roteados por essa internet até chegar ao destino. Após ser definido por qual caminho os dados devem prosseguir, a **camada de enlace surgirá para garantir** essa comunicação ponto a ponto ou hop to hop.  
  
Veja a representação desse fluxo a seguir (Entrega desde a origem até o destino):
![[Pasted image 20240318151722.png]]
A camada de enlace é responsável por garantir a **comunicação entre dispositivos adjacentes**. Ela corrigirá quaisquer problemas que tenham ocorrido no meio físico de transmissão e entregará para a camada de rede um serviço de transmissão de dados aparentemente livre de erros.  
  
É possível fazer uma analogia entre as camadas de enlace e de transporte:
![[Pasted image 20240318151749.png]]

Por esse motivo, muitas das funções existentes na camada de transporte também estarão presentes na de enlace:

* Controle de erros: Os meios de transmissão não são livres de erro; portanto, os dados que trafegam através deles estão sujeitos a erros. A camada de enlace pode implementar mecanismos de controle de erro com a finalidade de agregar confiabilidade ao serviço de transmissão.
* Controle de acesso ao meio: Como alguns meios de transmissão são compartilhados, ou seja, mais de um dispositivo pode transmitir pelo mesmo meio, é necessário um mecanismo para controlar qual dos dispositivos pode transmitir naquele momento.
* Endereçamento físico: Enquanto o endereço de porta indica o processo na máquina de destino e o endereço lógico indica o dispositivo de destino, o endereço físico indicará qual será o próximo dispositivo no caminho origem-destino. Ao chegar à rede de destino, o endereço físico será o do dispositivo final.
* Controle de fluxo: Semelhante ao que acontece na camada de transporte, o controle de fluxo evitará que o nó de origem sobrecarregue o nó de destino.
* Enquadramento: A camada de enlace receberá os dados da camada de rede (PDU da camada de rede), encapsulando-os em quadros (PDU da camada de enlace). Os quadros criados pela camada de enlace terão uma função importante, que será a adição de delimitadores de início e fim do quadro na origem, para permitir que, no nó vizinho, a camada de enlace possa ver o fluxo de bits e definir corretamente onde inicia e termina o quadro.

### Física
Essa camada é responsável por **transmitir os dados pelo meio de transmissão**. Ela receberá os quadros da camada de enlace, que serão formados por uma sequência de bits, e irá codificar corretamente para que sejam enviados pelo meio de transmissão.  
  
A camada física será responsável pela representação dos bits, ou seja, de acordo com o meio de transmissão, ela irá definir se essa representação ocorrerá por pulsos de luz, no caso da fibra ótica, ou pulsos elétricos, no caso de empregar cabos de par trançado. Além disso, a camada física é responsável por:

* **Taxa de dados**: A velocidade em que os bits são inseridos no meio de transmissão é responsabilidade da camada física. Quando ouvimos a expressão megabits por segundo (Mbps), que define a taxa de transmissão de determinado enlace, é responsabilidade da camada física estabelecer esse valor. Assim, a taxa de transmissão definirá a duração de um bit: quanto maior a taxa, menor a duração do bit, e vice-versa.
* **Sincronização dos bits**: O nó transmissor e o receptor devem operar na mesma velocidade, ou seja, na mesma taxa de bits. Entretanto, os relógios (clocks) das camadas físicas têm pequenas diferenças; portanto, é possível que ocorram falhas de sincronismos. A camada física deve implementar algum tipo de mecanismo que permita o correto sincronismo dos bits entre origem e destino.
* **Topologia física**: Define como os nós da rede estão interligados, podendo ser uma configuração de um enlace ponto a ponto, em que cada nó está diretamente conectado a outro, sem compartilhamento do meio, ou uma ligação ponto-multiponto, em que o enlace é compartilhado por diversos nós.
* **Modo de transmissão**:A camada física definirá o modo de transmissão em um determinado meio: simplex, half duplex ou full duplex. Considerando dois dispositivos, A e B, no modo simplex só existe envio de dados em um sentido, por exemplo, de A para B; no modo half duplex, os dados podem ser enviados nos dois sentidos, mas não simultaneamente (de A para B em um momento e de B para A em outro momento); e no modo full duplex, os dados podem ser enviados simultaneamente por A e B.
### Resumo

Tendo percorrido o caminho da origem até o destino, passando por todas as camadas da rede, você é capaz de entender como as informações são transmitidas pelos dispositivos computacionais. Vamos relembrar o seu percurso!  
  
Veja um resumo das camadas e suas funcionalidades:
![[Pasted image 20240318152039.png]]

# Camadas da arquitetura TCP/IP
## Arquitetura e evolução do protocolo TCP/IP
A arquitetura foi criada utilizando quatro camadas: aplicação, transporte, internet e acesso à rede.  
  
As duas últimas camadas podem ser encontradas com nomes diferentes na literatura. A camada de internet pode ser encontrada como **rede e inter-rede** e a camada de acesso à rede pode ser encontrada como **camada de enlace, host-rede, intrarrede e host-network**.

>Quatro camadas: Apesar da arquitetura TCP/IP possuir quatro camadas, é comum encontrar, também na literatura, uma arquitetura de cinco camadas. Nessa arquitetura, a camada de acesso à rede é dividida em duas: enlace e física. Essa divisão tem foco em facilitar o estudo e aprendizado das funções executadas nos níveis mais baixos. Como este material tem por finalidade o aprendizado da arquitetura TCP/IP como um todo, e não vamos entrar em detalhes de operação de cada camada, manteremos a arquitetura original de quatro camadas.

![[Pasted image 20240318152223.png]]
Após identificarmos que a arquitetura TCP/IP tem apenas quatro camadas, é possível imaginar que **algumas das funções** executadas pelas camadas de apresentação, sessão, enlace e rede, ausentes na arquitetura TCP/IP, serão **acumuladas por outras camadas**.  
  
As funções das camadas de **apresentação e sessão** serão acumuladas pela camada de **aplicação** e a funções das camadas de **enlace e física** serão executadas pela camada de **acesso à rede**. Observe a relação entre os dois modelos a seguir.

![[Pasted image 20240318152239.png]]Uma grande diferença que temos entre o modelo de referência OSI e a arquitetura TCP/IP é:
![[Pasted image 20240318152527.png]]

É comum ouvirmos falar da pilha de protocolos TCP/IP. Agora que dominamos o conceito do modelo de camadas, como vimos no modelo OSI, fica fácil de entender que a pilha de protocolos TCP/IP é o conjunto de todos os protocolos implementados pela arquitetura. E não são poucos.  
  
Os principais protocolos de padrão aberto da arquitetura Internet foram desenvolvidos pelo **IETF** (The Internet Engineering Task Force), uma grande comunidade internacional aberta, composta por designers de rede, operadores, fornecedores e pesquisadores preocupados com a evolução da arquitetura da internet.

## Camadas: funções e principais protocolos
Depois de estudarmos o modelo OSI, é possível ter uma ideia geral dos serviços de cada camada; portanto, vamos focar, principalmente, nos protocolos.

### Aplicação
A camada de aplicação da arquitetura TCP/IP nos engloba os serviços das camadas de aplicação, apresentação e sessão do modelo OSI. Através da camada de aplicação é possível **acessar uma infinidade de serviços na internet**. Desde os que são utilizados de forma direta pelos usuários, como o serviço Web, serviço de correio eletrônico, entre outros, bem como os que funcionam dando suporte à operação da rede, como o serviço de nomes (DNS).  
  
Os serviços são implementados pelos **diversos protocolos existentes**. Correlacionamos, a seguir, alguns serviços e protocolos utilizados na camada de aplicação.

|Serviço|Protocolo|
|---|---|
|Web|HTTP, HTTPS|
|Correio Eletrônico|SMTP, POP, e IMAP|
|Nomes|DNS|
|Transferência de arquivos|FTP, TFTP|
|Áudio e vídeo em tempo real|RTP|
|Configuração automática de estações|DHCP|

Os **protocolos apresentados** são implementados **por meio de softwares**, que são executados nos diversos dispositivos computacionais, e podem estar associados a dois tipos principais de arquitetura:

* **Cliente-servidor**: Na arquitetura cliente-servidor, como já evidencia o nome, existirá um cliente e um servidor. O cliente será executado por um usuário como nós e irá requisitar um serviço do servidor. Por exemplo, para o serviço Web, o cliente é o navegador que acessa determinado servidor, por exemplo, o servidor que está disponibilizando esse conteúdo.
* **Par a par (peer-to-peer (P2P))**: A arquitetura P2P foi pensada no emprego mínimo de servidores, caso exista algum. A ideia da arquitetura peer-to-peer é que os usuários possam trocar informações de forma direta. Esse tipo de arquitetura ficou muito conhecida com os programas de compartilhamento de arquivos, mas também pode ser utilizada em outras situações, como em um chat entre duas pessoas.

Independentemente da arquitetura utilizada, dizemos que os processos da camada de aplicação trocam **mensagens**, que é o nome da unidade de dados do protocolo (PDU) da camada de aplicação.

### Transporte
Tem a mesma funcionalidade da camada existente no modelo OSI: **garantir a entrega de processo a processo de todos os dados enviados pelo usuário**. Porém, na arquitetura TCP/IP, temos **dois protocolos** principais:

![[Pasted image 20240318152738.png]]![[Pasted image 20240318152806.png]]

Então, por que usamos o UDP?  
  
Ele é importante para as **aplicações que demandam tempo de resposta baixo na comunicação**, como em um áudio ou uma videoconferência, e nas aplicações que podem funcionar tolerando algum tipo de perda.

### Internet
A camada internet ou simplesmente camada de rede tem por objetivo **permitir que os dados injetados na rede pela máquina de origem possam alcançar o destino**. O principal protocolo da camada de rede é o IP (Internet Protocol).  
  
Ele é encontrado em duas versões principais:
![[Pasted image 20240318152840.png]]

* Objetivo: Os dois protocolos têm por objetivo definir o endereço lógico, conhecido como endereço IP, e permitir o tratamento dos **datagramas** (PDU-R) para que possam ser roteados da origem até o destino.
* Diferença: A diferença entre as duas versões do protocolo está no tamanho do endereço lógico, 32 bits para o IPv4 e 128 bits para o IPv6, no formato do **datagrama** e em algumas funções mais específicas que não abordaremos neste material.
* Semelhança: Os dois protocolos têm em comum o fato de não serem orientados à conexão e não terem confiabilidade, ou seja, não realizam o tratamento de erros e os **datagramas** são enviados de forma independente. Portanto, podem chegar em ordem diferente da qual foram enviados.

**Dizemos que o serviço da camada internet é de melhor esforço**.  
  
Será feito o maior esforço de entregar as informações, mas não será garantida a entrega, nem a ordem, nem a ausência de erro. Qualquer problema deverá ser corrigido pelas camadas superiores.

> Atenção! Além do protocolo IP, a camada internet emprega outros protocolos que dão suporte ao encaminhamento dos dados. Existem protocolos com o objetivo de fazer sinalização e avisos de erros, como o ICMP (Internet Control Message Protocol), tradução do endereço lógico para o físico, como o ARP (Address Resolution Protocol), e a chamada comunicação multicast, que permite o envio dos dados para um grupo de estações, como o protocolo IGMP (Internet Group Management Protocol).

### Acesso à rede

A camada de acesso à rede não foi bem definida pela arquitetura TCP/IP, nem define um protocolo específico a ser empregado. O que foi dito inicialmente é que a camada de acesso à rede seria **qualquer coisa que pudesse ligar o dispositivo ao enlace de transmissão**.  
  
Mas, como para chegar até aqui já estudamos vários conceitos, sabemos que, apesar de não estar definida pela arquitetura TCP/IP, nessa camada encontraremos os serviços que são oferecidos pelas camadas de enlace e física do modelo OSI.  
  
Embora não faça parte da arquitetura TCP/IP, a arquitetura desenvolvida pelo Instituto de Engenheiros Eletricistas e Eletrônicos (Institute of Electrical and Electronics Engineers – IEEE), denominada **IEEE 802**, é largamente utilizada na camada de acesso à rede. Ela define diversos **padrões utilizados nas redes locais e metropolitanas**, como o padrão Ethernet e o famoso WiFi, que provavelmente você está usando agora para acessar este conteúdo.  
  
Agora que terminamos a apresentação dos principais protocolos da arquitetura TCP/IP, podemos fazer uma correlação entre a arquitetura internet e seus protocolos com o modelo OSI, conforme se vê a seguir:
![[Pasted image 20240318163922.png]]
> Saiba mais:
>A arquitetura internet ou TCP/IP como uma estrutura de camadas não evoluiu ao longo dos anos. A grande evolução que tivemos foi nos protocolos empregados.  
  Inicialmente, os protocolos da camada de aplicação eram concentrados nas aplicações textuais, com um pequeno volume de informação a ser trocado, como o Serviço Web criado por Sir Tim Berners-Lee, com foco em páginas textuais para troca de informações entre os centros de pesquisa.  
  Atualmente, os protocolos evoluíram significativamente para oferecer maior qualidade de serviço, suporte ao tráfego de vídeo, segurança, transações financeiras, entre outros. Falando novamente do serviço Web, o protocolo https:// evoluiu de um protocolo textual para binário, a fim de dar suporte aos diversos usos do serviço Web, como assistir a vídeos, CRMs, ERPs, entre muitos outros sistemas complexos.