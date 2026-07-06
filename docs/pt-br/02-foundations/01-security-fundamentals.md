Os princípios fundamentais da segurança de aplicativos baseiam-se nos conceitos
de segurança mencionados neste guia do desenvolvedor.
Esta seção tem como objetivo fornecer uma introdução aos princípios fundamentais
com os quais qualquer equipe de desenvolvimento deve estar familiarizada.

#### Modelo de Maturidade de Software Assurance

![SAMM logo](../../assets/images/logos/samm.png "OWASP SAMM"){: .image-right-small }

O Modelo de Maturidade de Software Assurance ([SAMM][samm]) fornece contexto para o escopo da segurança de software
e os fundamentos das boas práticas de segurança:

* [Governança][sammg]
* [Design][sammd]
* [Implementação][sammi]
* [Verificação][sammv]
* [Operações][sammo]

O modelo SAMM descreve esses fundamentos de segurança de software como Funções de Negócio,
que são subdivididos em Práticas de Negócio.
O Modelo de Maturidade de Software Assurance OWASP ([SAMM][samm]) é usado ao longo deste Guia do Desenvolvedor;
a maioria das seções do Guia do desenvolvedor faz referência a pelo menos uma das funções ou práticas de negócios do SAMM.

#### Tríade CID

Segurança é simplesmente controlar quem pode interagir com sua informação,
o que eles podem fazer com ela e quando podem interagir com ela.
Estas características de segurança podem ser descritas utilizando a tríade CID.

CID significa Confidencialidade, Integridade e Disponibilidade,
e geralmente é retratada como um triângulo que representa os fortes laços entre seus três princípios.
Esta tríade é considerada os pilares de segurança de aplicações,
frequentemente Confidencialidade, Integridade ou Disponibilidade são usadas como propriedades
de dados ou processos dentro de um determinado sistema.
A tríade CID pode ser ampliada com a tríade AAA: Autorização, Autenticação e Auditoria.

#### Confidencialidade

Confidencialidade é a proteção dos dados contra a divulgação não autorizada;
trata-se de garantir que apenas aqueles com a autorização correta possam acessar os dados
e se aplica tanto aos dados em repouso quanto aos dados em trânsito.
Confidencialidade também está relacionada ao conceito mais amplo de privacidade de dados.

#### Integridade

Integridade refere-se à proteção os dados contra modificações não autorizadas ou garantir a confiabilidade dos dados.
O conceito contém a noção de integridade de dados (os dados não foram alterados acidental ou deliberadamente)
e a noção de integridade da fonte (os dados vieram ou foram alterados por uma fonte legítima).

#### Disponibilidade

Disponibilidade refere-se à garantia da presença de informação ou recursos.
Este conceito não se baseia apenas na disponibilidade dos dados em si, por exemplo,
através da utilização da replicação de dados,
mas também na proteção dos serviços que fornecem acesso aos dados, por exemplo,
através da utilização de balanceamento de carga.

#### Tríade AAA

A tríade CID é frequentemente ampliada com Autenticação, Autorização e Auditoria,
uma vez que estas estão intimamente ligadas aos conceitos da CID.
A CID depende fortemente da autenticação e autorização;
a confidencialidade e a integridade de dados sensíveis não podem ser garantidas sem elas.
A auditoria é adicionada porque pode fornecer o mecanismo para garantir a prova de qualquer interação com o sistema.

#### Autenticação

[Autenticação][csauthn] consiste em confirmar a identidade da entidade que deseja interagir com um sistema seguro.
Por exemplo, a entidade poderia ser um cliente automatizado ou um ator humano;
em ambos os casos, a autenticação é necessária para um aplicativo seguro.

#### Autorização

[Autorização][csauthz] consiste em especificar direitos de acesso a recursos
seguros (dados, serviços, arquivos, aplicativos, etc.).
Esses direitos descrevem os privilégios ou níveis de acesso relacionados aos recursos que estão sendo protegidos.
Autorização geralmente é precedida por uma autenticação bem-sucedida.

#### Auditoria

Auditoria trata-se do registro de eventos em nível de implementação,
bem como eventos em nível de domínio que ocorrem em um sistema.
Isso ajuda a proporcionar o não repúdio, o que significa que as alterações ou ações no sistema protegido são inegáveis.
Auditoria pode fornecer não apenas informações técnicas sobre o sistema em execução,
mas também prova de que ações específicas foram realizadas.
As perguntas típicas respondidas pela auditoria são "Quem fez o quê, Quando e potencialmente Como?"

#### Vulnerabilidades

O NIST define [vulnerabilidade][nistvuln] como 'Fragilidade em um sistema de informação, procedimentos de
segurança do sistema, controles internos ou implementação que possa ser explorada ou desencadeada por uma fonte de ameaça.'

Existem muitas fragilidades ou bugs em todas as aplicações grandes, mas o termo vulnerabilidade é geralmente reservado
para aquelas fragilidades ou bugs onde existe o risco de um agente de ameaça poder explorá-las usando um vetor de ameaça.

Vulnerabilidades de segurança bem conhecidas:

* [Clickjacking][csclick]
* [Credential Stuffing][cscreds]
* [Cross-site leaks][csxsleaks]
* Ataques de [Negação de Serviço][csdos] (DoS)
* [Ataque de XSS][csdom] baseado em DOM incluindo [DOM Clobbering][csdomclub]
* [IDOR][csidor] (Referência Direta Insegura a Objetos)
* [Injeção][csinjection] incluindo [Injeção de Comando do OS][csosinjection] e [XXE][csxxe]
* [Ataques de injeção][csldap] específicos de LDAP
* [Poluição de protótipos][csproto]
* Ataques de [SSRF][csssrf]
* [Injeção de SQL][cssql] e o uso de [Parametrização de queries][csquery]
* [Redirecionamentos e encaminhamentos não validados][csredirect]
* [Ataques de XSS][csxss] e [Evasão de Filtro XSS][csxssevade]

#### HTTP and HTML

Embora não seja uma segurança fundamental como tal, as aplicações web dependem de comunicações HTTP e HTML.
Tanto os desenvolvedores de aplicações quanto os engenheiros de segurança devem ter um bom entendimento de HTTP
e a linguagem HTML juntamente com seus vários controles de segurança.

A maioria das equipes de desenvolvimento de aplicações estará familiarizada com as comunicações HTTP e o padrão HTML
mas, se necessário, consulte o treinamento do [W3 Consortium][w3consortium] ou da [W3 Schools][w3schools].
O OWASP [Cheat Sheet Series][cheatsheets] fornece aos desenvolvedores de aplicações web as informações
necessárias para produzir software seguro:

* A folha de dicas [HTML5 Security][cshtml5] descreve uma grande variedade de controles,
  alinhados com o atual [HTML Living Standard][htmlliving]
* Consulte a folha de dicas para CSS [Securing Cascading Style Sheets][cscss]
* Os cabeçalhos HTTP precisam sem seguros, veja a folha de dicas [HTTP Security Response Headers][csheaders]
* Considere fortemente [HTTP Strict Transport Security][csstrict]
* Se a aplicação tem uma funcionalidade de upload de arquivo, siga a folha de dicas [File Upload][csfile]
* Certifique-se de que a política de segurança de conteúdo esteja em vigor usando
  a folha de dicas [Content Security Policy][cscsp]
* Usando JWTs para uma aplicação Java? Consulte a folha de dicas [JSON Web Token][csjwt]
* Armazenando our enviando objetos? Confira a folha de dicas [Deserialization][csserial]

#### Referências

* [WHATWG][whatwg] [HTML Living Standard][htmlliving]
* OWASP [Cheat Sheet Series][cheatsheets]
* OWASP [Modelo de Maturidade de Software Assurance][samm] (SAMM)

----

O Guia do Desenvolvedor da OWASP é um trabalho da comunidade; se há algo que precisa ser mudado
então [submeta uma issue][issue0401] ou [edite no GitHub][edit0401].

[cheatsheets]: https://cheatsheetseries.owasp.org/
[csclick]: https://cheatsheetseries.owasp.org/cheatsheets/Clickjacking_Defense_Cheat_Sheet
[cscreds]: https://cheatsheetseries.owasp.org/cheatsheets/Credential_Stuffing_Prevention_Cheat_Sheet
[cscsp]: https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet
[cscss]: https://cheatsheetseries.owasp.org/cheatsheets/Securing_Cascading_Style_Sheets_Cheat_Sheet
[csdom]: https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet
[csdomclub]: https://cheatsheetseries.owasp.org/cheatsheets/DOM_Clobbering_Prevention_Cheat_Sheet
[csdos]: https://cheatsheetseries.owasp.org/cheatsheets/Denial_of_Service_Cheat_Sheet
[csidor]: https://cheatsheetseries.owasp.org/cheatsheets/Insecure_Direct_Object_Reference_Prevention_Cheat_Sheet
[csinjection]: https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet
[csosinjection]: https://cheatsheetseries.owasp.org/cheatsheets/OS_Command_Injection_Defense_Cheat_Sheet
[csldap]: https://cheatsheetseries.owasp.org/cheatsheets/LDAP_Injection_Prevention_Cheat_Sheet
[csproto]: https://cheatsheetseries.owasp.org/cheatsheets/Prototype_Pollution_Prevention_Cheat_Sheet
[csauthn]: https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet
[csauthz]: https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet
[csfile]: https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet
[csheaders]: https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Headers_Cheat_Sheet
[cshtml5]: https://cheatsheetseries.owasp.org/cheatsheets/HTML5_Security_Cheat_Sheet
[csjwt]: https://cheatsheetseries.owasp.org/cheatsheets/JSON_Web_Token_Cheat_Sheet
[csredirect]: https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet
[csserial]: https://cheatsheetseries.owasp.org/cheatsheets/Deserialization_Cheat_Sheet
[cssql]: https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet
[csquery]: https://cheatsheetseries.owasp.org/cheatsheets/Query_Parameterization_Cheat_Sheet
[csssrf]:  https://cheatsheetseries.owasp.org/cheatsheets/Server_Side_Request_Forgery_Prevention_Cheat_Sheet
[csstrict]: https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet
[csxss]: https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet
[csxsleaks]: https://cheatsheetseries.owasp.org/cheatsheets/XS_Leaks_Cheat_Sheet
[csxssevade]: https://cheatsheetseries.owasp.org/cheatsheets/XSS_Filter_Evasion_Cheat_Sheet
[csxxe]: https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet
[edit0401]: https://github.com/OWASP/DevGuide/blob/main/docs/pt-br/02-foundations/01-security-fundamentals.md
[issue0401]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2002-foundations/01-security-fundamentals
[htmlliving]: https://html.spec.whatwg.org/multipage/
[nistvuln]: https://csrc.nist.gov/glossary/term/vulnerability
[samm]: https://owaspsamm.org/about/
[sammd]: https://owaspsamm.org/model/design/
[sammg]: https://owaspsamm.org/model/governance/
[sammi]: https://owaspsamm.org/model/implementation/
[sammo]: https://owaspsamm.org/model/operations/
[sammv]: https://owaspsamm.org/model/verification/
[w3consortium]: https://www.w3.org/
[w3schools]: https://www.w3schools.com/html/
[whatwg]: https://whatwg.org/
