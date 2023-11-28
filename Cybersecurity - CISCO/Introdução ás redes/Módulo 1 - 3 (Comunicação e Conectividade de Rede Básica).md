
# 1. Componentes de rede
## **Funções do Host**
Todos os computadores que estão conectados a uma rede e participam diretamente da comunicação em rede são classificados como hosts. **Os hosts podem ser chamados de dispositivos finais. Alguns hosts também são chamados de clientes.** No entanto, o termo hosts refere-se especificamente a dispositivos na rede que recebem um número para fins de comunicação. Este número identifica o host dentro de uma rede específica. Este número é chamado de **endereço IP** (Internet Protocol). **Um endereço IP identifica o host e a rede à qual o host está conectado.**

![[Pasted image 20231127102944.png]]

Um exemplo de software cliente é um navegador, como Chrome ou FireFox. Um único computador pode também executar vários tipos de software cliente. Por exemplo, um usuário pode verificar o e-mail e visualizar uma página da Web enquanto troca mensagens instantâneas e ouve um fluxo de áudio. A tabela lista três tipos comuns de software de servidor.


## Rede ponto a ponto
O software cliente e o servidor geralmente são executados em computadores separados, mas também é possível que um computador seja usado para ambas as funções ao mesmo tempo. Em pequenas empresas e em casas, muitos computadores funcionam como servidores e clientes na rede. Esse tipo de rede é chamado de rede ponto a ponto.
![[Pasted image 20231127105016.png]]

Vantagens da rede ponto a ponto:
* fácil de configurar;
* menos complexo;
* menor custo porque os dispositivos de rede e os servidores dedicados podem não ser necessários;
* pode ser usada para tarefas simples como transferir arquivos e compartilhar impressoras.

Desvantagens das rede ponto a ponto:
* nenhuma administração centralizada;
* não é tão segura;
* não é escalável;
* todos os dispositivos podem atuar como clientes e servidores, podendo deixar seu desempenho lento.


## Dispositivos finais
Os dispositivos de rede com os quais as pessoas estão mais familiarizadas são dispositivos finais. Para distinguir um dispositivo final de outro, cada dispositivo final em uma rede tem um endereço. Quando um dispositivo final inicia a comunicação, ele usa o endereço do dispositivo final de destino para especificar onde entregar a mensagem.
Um dispositivo final é a origem ou o destino de uma mensagem transmitida pela rede.

![[Pasted image 20231127105415.png]]


## Dispositivos intermediários
Dispositivos intermediários conectam os dispositivos finais individuais à rede. Eles podem conectar várias redes individuais para formar uma internetwork. Eles oferecem conectividade e asseguram que os dados fluam pela rede.
Esses dispositivos intermediários usam o endereço do dispositivo final de destino, em conjunto com as informações sobre as interconexões de rede, para determinar o caminho que as mensagens devem percorrer na rede. Exemplos dos dispositivos intermediários mais comuns e uma lista de funções são mostrados na figura.

![[Pasted image 20231127105511.png]]

Os dispositivos de rede intermediários executam algumas dessas funções:
* regenerar e retransmitir sinais de comunicação;
* manter informação sobre quais caminhos existem pela rede e pela rede interconectada;
* notificar outros dispositivos sobre erros e falhas de comunicação;
* direcionar dados por caminhos alternativos quando houver falha em um link;
* classificar e direcionar mensagens de acordo com as prioridades;
* permitir ou negar o fluxo de dados, com base em configurações de segurança.


## Meios de redes
A comunicação transmite através de uma rede na mídia. A mídia fornece o canal pelo qual a mensagem viaja da origem ao destino.

As redes modernas usam principalmente três tipos de mídia para interconectar dispositivos, como mostrado na figura:

- **Fios de metal dentro de cabos** - Os dados são codificados em impulsos elétricos.
- **Fibras de vidro ou plástico nos cabos (cabo de fibra óptica)** - Os dados são codificados em pulsos de luz.
- **Transmissão sem fio** - Os dados são codificados através da modulação de frequências específicas de ondas eletromagnéticas.
![[Pasted image 20231127105849.png]]


# 2. Representações e topologias de rede
## Redes de Rede
Arquitetos e administradores de rede devem ser capazes de mostrar como suas redes serão. Eles precisam ser capazes de ver facilmente quais componentes se conectam a outros componentes, onde eles serão localizados e como eles serão conectados. Os diagramas de redes geralmente usam símbolos, como os mostrados na figura, para representar os diferentes dispositivos e conexões que compõem uma rede.
![[Pasted image 20231127110102.png]]

Um diagrama fornece uma maneira fácil de entender como os dispositivos se conectam em uma rede grande. Esse tipo de “fotografia” de uma rede é conhecido como um diagrama de topologia. A capacidade de reconhecer as representações lógicas dos componentes físicos de rede é crucial para se permitir visualizar a organização e a operação de uma rede.

Além dessas representações, é utilizada terminologia especializada para descrever como cada um desses dispositivos e mídias se conectam:

- **Placa de interface de rede (NIC)** - Uma NIC conecta fisicamente o dispositivo final à rede.
- **Porta física** - Um conector ou tomada em um dispositivo de rede onde a mídia se conecta a um dispositivo final ou outro dispositivo de rede.
- **Interface** - Portas especializadas em um dispositivo de rede que se conectam a redes individuais. Como os roteadores conectam redes, as portas em um roteador são chamadas de interfaces de rede.

**Observação**: Os termos porta e interface são freqüentemente usados alternadamente.

## Diagramas de Topologia

Os diagramas de topologia são documentação obrigatória para qualquer pessoa que trabalhe com uma rede. Eles fornecem um mapa visual de como a rede está conectada. Existem dois tipos de diagramas de topologia: físicos e lógicos.

-> **Diagramas de topologia física**
Os diagramas de topologia física ilustram a localização física dos dispositivos intermediários e a instalação dos cabos, conforme mostrado na figura. Você pode ver que as salas em que esses dispositivos estão localizados estão rotuladas nesta topologia física.
![[Pasted image 20231127110311.png]]

-> **Diagramas de topologia lógica**
Diagramas de topologia lógica ilustram dispositivos, portas e o esquema de endereçamento da rede, conforme mostrado na figura. Você pode ver quais dispositivos finais estão conectados a quais dispositivos intermediários e que mídia está sendo usada.
![[Pasted image 20231127110427.png]]



## Questões 
1. Qual conexão conecta fisicamente o dispositivo final à rede?
    [ ]Porta
    [x]Placa de rede
    [ ]Interface

2. Quais conexões são portas especializadas em um dispositivo de rede que se conectam a redes individuais?
	[ ]Porta
	[ ]Placa de rede
	[x]Interface

3. Que tipo de topologia de rede permite que você veja quais dispositivos finais estão conectados a quais dispositivos intermediários e que mídia está sendo usada?
	[ ]Topologia Física
	[x]Topologia Lógica

4. Que tipo de topologia de rede permite que você veja a localização real dos dispositivos intermediários e da instalação de cabos?
	[x]Topologia Física
	[ ]Topologia Lógica


# 3. Tipos comuns de redes

## Redes de vários tamanhos
Existem redes de vários tamanhos. Eles variam de redes simples compostas por dois computadores a redes que conectam milhões de dispositivos.

As redes domésticas simples permitem que você compartilhe recursos, como impressoras, documentos, imagens e música, entre alguns dispositivos finais locais.

As redes de pequeno escritório e escritório doméstico (SOHO) permitem que as pessoas trabalhem em casa ou em um escritório remoto. Muitos trabalhadores independentes usam esses tipos de redes para anunciar e vender produtos, pedir suprimentos e se comunicar com os clientes.

Empresas e grandes organizações usam redes para fornecer consolidação, armazenamento e acesso a informações em servidores de rede. As redes fornecem e-mail, mensagens instantâneas e colaboração entre funcionários. Muitas organizações usam a conexão de sua rede à Internet para fornecer produtos e serviços aos clientes.

**A internet é a maior rede existente. Na verdade, o termo Internet significa uma “rede de redes”. É uma coleção de redes públicas e privadas interconectadas.**

Em pequenas empresas e residências, muitos computadores funcionam como servidores e clientes na rede. Esse tipo de rede é chamado de **rede ponto a ponto.**



## LANs e WANs

As infra-estruturas de rede variam muito em termos de:
- Tamanho da área coberta;
- Número de usuários conectados;
- Número e tipos de serviços disponíveis;
- Área de responsabilidade.

**Os dois tipos mais comuns de infraestruturas de rede são as redes locais (LANs) e as redes de longa distância (WANs). **

*Uma LAN é uma infraestrutura de rede que fornece acesso a usuários e dispositivos finais em uma pequena área geográfica.* Normalmente, uma LAN é usada em um departamento dentro de uma empresa, uma casa ou uma rede de pequenas empresas. 

*Uma WAN é uma infraestrutura de rede que fornece acesso a outras redes em uma ampla área geográfica*, que normalmente pertence e é gerenciada por uma corporação maior ou por um provedor de serviços de telecomunicações. 

A figura mostra LANs conectadas a uma WAN.
![[Pasted image 20231127111258.png]]

**-> LANs**
Uma LAN é uma infraestrutura de rede que abrange uma pequena área geográfica. As LANs têm características específicas:

- LANs interconectam dispositivos finais em uma área limitada, como uma casa, uma escola, um edifício de escritórios ou um campus.
- Uma LAN é geralmente administrada por uma única organização ou pessoa. O controle administrativo é imposto no nível da rede e governa as políticas de segurança e controle de acesso.
- As LANs fornecem largura de banda de alta velocidade para dispositivos finais internos e dispositivos intermediários, conforme mostrado na figura.

![[Pasted image 20231127111423.png]]

**-> WANs**
A figura mostra uma WAN que interconecta duas LANs. Uma WAN é uma infraestrutura de rede que abrange uma ampla área geográfica. As WANs geralmente são gerenciadas por provedores de serviços (SPs) ou provedores de serviços de Internet (ISPs).

As WANs têm características específicas:

- As WANS interconectam as LANs em grandes áreas geográficas, como entre cidades, estados, províncias, países ou continentes.
- As WANs são geralmente administradas por vários prestadores de serviço.
- As WANs geralmente fornecem links de velocidade mais lenta entre as LANs.

![[Pasted image 20231127111511.png]]




## A internet

A internet é uma coleção mundial de redes interconectadas (internetworks, ou internet para abreviar). A figura mostra uma maneira de visualizar a Internet como uma coleção de LANs e WANs interconectadas.
![[Pasted image 20231127111605.png]]

Algumas LANs do exemplo são conectados entre si por meio de uma WAN. As WANs estão conectadas entre si. As linhas de conexão de WAN, em vermelho, representam todas as variações de modos de conexão de rede. As WANs podem se conectar através de fios de cobre, cabos de fibra ótica e transmissões sem fio (não mostradas).

A internet não é de propriedade de nenhum indivíduo ou grupo. Garantir a comunicação efetiva por essa infraestrutura diversa exige a aplicação de tecnologias e protocolos consistentes e geralmente reconhecidos, bem como a cooperação de muitas agências de administração de redes. Existem organizações que foram desenvolvidas para ajudar a manter a estrutura e a padronização de protocolos e processos da Internet. Essas organizações incluem a Internet Engineering Task Force (IETF), a Internet Corporation for Assigned Names and Numbers (ICANN) e a Internet Architecture Board (IAB), além de muitas outras.


## Intranets e Extranets
