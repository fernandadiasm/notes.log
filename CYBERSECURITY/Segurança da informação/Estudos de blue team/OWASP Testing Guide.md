O **OWASP Testing Guide** é um guia criado pela **Open Web Application Security Project (OWASP)** que fornece diretrizes detalhadas para **testes de segurança em aplicações web**. Ele ensina **como identificar, explorar e corrigir vulnerabilidades** em sites, APIs e sistemas web.

Esse guia é muito usado em **testes de penetração (pentests)** e auditorias de segurança porque segue uma abordagem **estruturada e prática** para encontrar falhas antes que sejam exploradas por atacantes.

#### 📌 O que o OWASP Testing Guide cobre?
Ele se baseia nos **10 principais riscos de segurança da OWASP** (_OWASP Top 10_). O **OWASP Top 10** é uma lista com os **10 principais riscos de segurança em aplicações web**, criada e mantida pela **OWASP (Open Web Application Security Project)**. Ela é atualizada periodicamente com base em **dados reais de ataques e vulnerabilidades** encontradas em sistemas ao redor do mundo.

A versão mais recente, **OWASP Top 10 - 2021**, traz os seguintes riscos:
##### 📌 OWASP Top 10 (2021) – Principais Riscos de Segurança Web
###### 1. Quebra de Controle de Acesso (Broken Access Control)
🔹 Ocorre quando usuários conseguem acessar **dados ou funções que não deveriam**.  
🔹 Exemplo: um usuário comum consegue alterar permissões de outro usuário ou acessar áreas administrativas.  
🔹 💡 **Como evitar?** Implementar controle de acesso adequado e testar permissões.
###### 2. Falhas Criptográficas (Cryptographic Failures)
🔹 Antigamente chamado de "Exposição de Dados Sensíveis", esse risco inclui **uso fraco ou ausência de criptografia**.  
🔹 Exemplo: senhas armazenadas sem hash, falta de HTTPS ou vazamento de chaves secretas.  
🔹 💡 **Como evitar?** Usar protocolos seguros (TLS 1.2+), criptografar dados sensíveis e armazenar senhas com bcrypt ou Argon2.
###### 3. Injeção (Injection)
🔹 Ocorre quando um atacante **injeta código malicioso** dentro de uma aplicação.  
🔹 Exemplo: **SQL Injection**, onde comandos maliciosos são inseridos em campos de entrada e executados no banco de dados.  
🔹 💡 **Como evitar?** Usar _prepared statements_, _ORMs_ e sanitização de entrada.
######  4. Design Inseguro (Insecure Design)
🔹 Aplicações com **arquitetura e lógica vulneráveis**, sem considerar segurança desde o início.  
🔹 Exemplo: um aplicativo bancário que permite transferências sem autenticação extra.  
🔹 💡 **Como evitar?** Aplicar **modelagem de ameaças** desde o início do desenvolvimento.
######  5. Falhas de Segurança e Configuração (Security Misconfiguration)
🔹 Configurações padrão ou erradas que deixam o sistema vulnerável.  
🔹 Exemplo: deixar um painel de administração acessível sem senha, usar serviços expostos na internet sem necessidade.  
🔹 💡 **Como evitar?** Remover serviços não utilizados, usar configurações seguras por padrão e revisar permissões.
###### 6. Componentes Vulneráveis e Desatualizados (Vulnerable and Outdated Components)
🔹 Uso de **bibliotecas, frameworks e softwares antigos ou sem suporte**, que podem conter vulnerabilidades conhecidas.  
🔹 Exemplo: usar uma versão antiga do **Log4j**, que permitia ataques de execução remota.  
🔹 💡 **Como evitar?** Manter softwares atualizados e monitorar vulnerabilidades conhecidas (**CVE, CVSS**).
######  7. Falhas de Identificação e Autenticação (Identification and Authentication Failures)
🔹 Senhas fracas, autenticação quebrada ou falha no gerenciamento de sessões.  
🔹 Exemplo: permitir login sem autenticação multifator (MFA) ou não invalidar sessões antigas.  
🔹 💡 **Como evitar?** Aplicar autenticação forte (MFA), bloquear tentativas excessivas de login e expirar tokens corretamente.
###### 8. Falhas na Integridade de Dados e Software (Software and Data Integrity Failures)
🔹 Problemas em **atualizações de software, pipelines de CI/CD e fontes de dados não verificadas**.  
🔹 Exemplo: baixar bibliotecas de fontes não confiáveis ou sofrer ataques de supply chain (como o caso do **SolarWinds**).  
🔹 💡 **Como evitar?** Assinar digitalmente os pacotes, validar fontes e monitorar integridade dos sistemas.
######  9. Falhas em Logs e Monitoramento de Segurança (Security Logging and Monitoring Failures)
🔹 Falta de logs ou monitoramento, dificultando a **detecção de ataques e resposta a incidentes**.  
🔹 Exemplo: não registrar tentativas de login suspeitas ou não ter alertas em tempo real.  
🔹 💡 **Como evitar?** Implementar logging centralizado e sistemas de SIEM para análise contínua.
###### 10. SSRF – Server-Side Request Forgery (Server-Side Request Forgery)
🔹 Permite que um atacante **faça requisições maliciosas a partir do servidor da vítima**, podendo acessar sistemas internos.  
🔹 Exemplo: um campo que aceita URLs externas pode ser explorado para acessar serviços internos via **localhost**.  
🔹 💡 **Como evitar?** Restringir solicitações externas, validar entradas e aplicar firewall de saída.


Além disso, o guia divide os testes em **fases**, incluindo:  

1️⃣ **Coleta de informações** → Identificar quais tecnologias a aplicação usa.  
2️⃣ **Mapeamento da aplicação** → Descobrir como funciona o fluxo do sistema.  
3️⃣ **Testes de autenticação e autorização** → Testar falhas de login e permissões.  
4️⃣ **Testes de gerenciamento de sessão** → Avaliar tokens de sessão, cookies e logout seguro.  
5️⃣ **Testes de injeção de código** → Procurar SQL Injection, XSS e falhas similares.  
6️⃣ **Testes de segurança na API** → Avaliar a exposição de endpoints e dados.

##### 📌 Resumo prático
🔹 O **OWASP Testing Guide** é um guia para **testes de segurança em aplicações web**.  
🔹 Ou seja, ele será útil para testar **sistemas web utilizados**.  
🔹 Seguir esse padrão melhora a proteção contra ataques como SQL Injection, XSS e falhas de autenticação.
