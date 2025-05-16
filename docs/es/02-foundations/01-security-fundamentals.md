Los principios fundamentales de la seguridad de aplicaciones se basan en los conceptos de seguridad
a los que se hace referencia en esta Guía del Desarrollador.
Esta sección tiene como objetivo proporcionar una introducción a los principios fundamentales
con los que cualquier equipo de desarrollo debe estar familiarizado.

#### Modelo de madurez de Seguridad de Software

![SAMM logo](../../assets/images/logos/samm.png "OWASP SAMM"){ align=right width=250 }

El modelo de madurez de Aseguramiento de Software ([SAMM][samm]) proporciona contexto para el alcance
de la seguridad del software y los fundamentos de las buenas prácticas de seguridad:

* [Gobernanza][sammg]
* [Diseño][sammd]
* [Implementación][sammi]
* [Verificación][sammv]
* [Operaciones][sammo]

El modelo SAMM describe estos fundamentos de seguridad de software como funciones comerciales,
que a su vez se dividen en Prácticas Comerciales.
El Modelo de Madurez de Aseguramiento de Software de OWASP ([SAMM][samm]) se utiliza en esta Guía del Desarrollador;
la mayoría de las secciones de la Guía del desarrollador hacen referencia a al menos una de las funciones
o prácticas comerciales de SAMM.

#### Tríada CIA

La seguridad consiste simplemente en controlar quién puede interactuar con la información,
qué pueden hacer con ella y cuándo pueden interactuar con ella.
Estas características de seguridad se pueden describir utilizando la tríada CIA.

CIA significa Confidencialidad, Integridad y Disponibilidad y generalmente se representa como un triángulo
que representa los fuertes vínculos entre sus tres principios.
Esta tríada se considera los pilares de la seguridad de las aplicaciones, a menudo, la confidencialidad, la integridad
o la disponibilidad se utilizan como propiedades de los datos o procesos dentro de un sistema determinado.
La tríada de la CIA se puede ampliar con la tríada AAA: Autorización, Autenticación y Auditoría.

#### Confidencialidad

La confidencialidad es la protección de los datos contra la divulgación no autorizada;
se trata de garantizar que sólo aquellos con la autorización correcta puedan acceder a los datos
y se aplica tanto a los datos en reposo como a los datos en tránsito.
La confidencialidad también está relacionada con el concepto más amplio de privacidad de datos.

#### Integridad

La integridad consiste en proteger los datos contra modificaciones no autorizadas
o garantizar la confiabilidad de los datos.
El concepto contiene la noción de integridad de los datos (los datos no han sido modificados accidental
o deliberadamente) y la noción de integridad de la fuente (los datos provienen de una fuente legítima
o fueron modificados por ella).

#### Disponibilidad

La disponibilidad consiste en garantizar la presencia de información o recursos.
Este concepto se basa no sólo en la disponibilidad de los datos en sí,
por ejemplo mediante el uso de replicación de datos,
sino también sobre la protección de los servicios que proporcionan acceso a los datos,
por ejemplo mediante el uso del equilibrio de carga.

#### Tríada AAA

La tríada de la CIA a menudo se amplía con Autenticación, Autorización y Auditoría,
ya que están estrechamente vinculadas a los conceptos de la CIA.
La CIA tiene una fuerte dependencia de la autenticación y la autorización;
la confidencialidad y la integridad de los datos sensibles no pueden garantizarse sin ellos.
Se agrega la auditoría, ya que puede proporcionar el mecanismo para garantizar pruebas de cualquier interacción
con el sistema.

#### Autenticación

La [autenticación][csauthn] consiste en confirmar la identidad de la entidad que desea interactuar con un sistema seguro.
Por ejemplo, la entidad podría ser un cliente automatizado o un actor humano;
en cualquier caso, se requiere autenticación para una aplicación segura.

#### Autorización

La [autorización][csauthz] consiste en especificar derechos de acceso a recursos seguros
(datos, servicios, archivos, aplicaciones, etc.).
Estos derechos describen los privilegios o niveles de acceso relacionados con los recursos que se están protegiendo.
La autorización suele ir precedida de una autenticación exitosa.

#### Auditoría

La auditoría consiste en realizar un seguimiento de los eventos a nivel de implementación,
así como de los eventos a nivel de dominio que tienen lugar en un sistema.
Esto ayuda a proporcionar no repudio, lo que significa que los cambios o acciones en el sistema protegido son innegables.
La auditoría puede proporcionar no sólo información técnica sobre el sistema en ejecución,
pero también prueba de que se han realizado acciones particulares.
Las preguntas típicas que se responden mediante la auditoría son "¿Quién hizo Qué, Cuándo y potencialmente Cómo?"

#### Vulnerabilidades

NIST define una [vulnerabilidad][nistvuln] como 'Debilidad en un sistema de información,
procedimientos de seguridad del sistema, controles internos o implementación que podría ser explotada
o activada por una fuente de amenaza.'

Hay muchas debilidades o errores en toda aplicación grande, pero el término vulnerabilidad generalmente está reservado.
para aquellas debilidades o errores en los que existe el riesgo de que un actor de amenazas pueda explotarlos utilizando
un vector de amenazas.

Las vulnerabilidades de seguridad más conocidas son:

* [Clickjacking][csclick]
* [Credential Stuffing][cscreds]
* [Fugas Cross-site][csxsleaks]
* Ataques de [Denegación de Servicio][csdos] (DoS)
* Ataques basado en DOM [ataques XSS][csdom] incluido [destrucción de DOM][csdomclub]
* [IDOR][csidor] (Referencia directa a objetos inseguros)
* [Inyección][csinjection] incluyendo [Inyección de comando OS][csosinjection] y [XXE][csxxe]
* [Ataques de inyección][csldap] específico de LDAP
* [Contaminación de prototipo][csproto]
* Ataques [SSRF][csssrf]
* [Inyección SQL][cssql] y el uso de [parametrización de consultas][csquery]
* [Redirecciones y reenvíos no validados][csredirect]
* [Ataques XSS][csxss] y [evasión de filtro XSS][csxssevade]

#### HTTP y HTML

Aunque no son un elemento fundamental de seguridad como tal, las aplicaciones web dependen de comunicaciones HTTP y HTML.
Tanto los desarrolladores de aplicaciones como los ingenieros de seguridad deben tener un buen conocimiento de HTTP
y del lenguaje HTML junto con sus diversos controles de seguridad.

La mayoría de los equipos de desarrollo de aplicaciones estarán familiarizados con las comunicaciones HTTP
y el estándar HTML, pero si es necesario consulte la formación del [Consorcio W3][w3consortium]
o de las [Escuelas W3][w3schools].
La [serie de hojas de referencia][cheatsheets] de OWASP proporciona a los desarrolladores de aplicaciones web
la información necesario para producir software seguro:

* La hoja de referencia [Seguridad HTML5][cshtml5] describe una amplia gama de controles,
  alineado con el actual [Estándar de vida HTML][htmlliving]
* Consulte la hoja de referencia para CSS [Seguridad de Hojas de estilo en cascada][cscss]
* Los encabezados HTTP deben ser seguros; consulte la hoja de referencia [HTTP Security Response Headers][csheaders]
* Considere seriamente [Seguridad estricta de transporte HTTP][csstrict]
* Si la aplicación tiene una función de carga de archivos, siga la hoja de referencia de [Carga de archivos][csfile]
* Asegúrese de que la política de seguridad de contenido esté implementada con la hoja de referencia
  [Política de seguridad de contenido][cscsp]
* ¿Utiliza JWT para una aplicación Java? Consulte la hoja de referencia de [JSON Web Token][csjwt]
* ¿Almacenar o enviar objetos? Consulte la hoja de referencia [Deserialización][csserial]

#### Referencias

* [WHATWG][whatwg] [Estándar de vida HTML][htmlliving]
* [Serie de Hojas de referencia][cheatsheets] de OWASP
* [Modelo de Madurez de Aseguramiento de Software][samm] de OWASP(SAMM)

----

Traducción de versión [original en inglés][en0401].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario;
si ve algo que necesita cambios, entonces [cree un issue][issue0401] o [edítelo en GitHub][edit0401].

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
[csjwt]: https://cheatsheetseries.owasp.org/cheatsheets/JSON_Web_Token_for_Java_Cheat_Sheet
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
[edit0401]: https://github.com/OWASP/DevGuide/blob/main/docs/es/02-foundations/01-security-fundamentals.md
[htmlliving]: https://html.spec.whatwg.org/multipage/
[en0401]: https://devguide.owasp.org/en/02-foundations/01-security-fundamentals/
[issue0401]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2002-foundations/01-security-fundamentals
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
