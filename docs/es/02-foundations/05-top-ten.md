![Top 10 logo](../../assets/images/logos/top10.png "OWASP Top 10"){ align=right width=180 }

El OWASP Top Ten es una lista muy conocida de riesgos de seguridad en aplicaciones web,
y está incluida en el Modelo de Madurez de Aseguramiento de Software de OWASP [(SAMM)][samm]
en la práctica de Educación y Orientación dentro de la función empresarial de Gobernanza.

#### Descripción General

El proyecto OWASP [Top 10 de Riesgos de Seguridad en Aplicaciones Web][top10project]
es probablemente el concepto de seguridad más conocido dentro de la comunidad de seguridad,
logrando una amplia aceptación y fama poco después de su lanzamiento en 2003.
Generalmente conocido simplemente como el 'OWASP Top Ten', es una lista que identifica las amenazas más importantes
para las aplicaciones web y busca clasificarlas según su importancia y gravedad.

La lista ha cambiado con el tiempo, con algunos tipos de amenazas convirtiéndose en un problema mayor
para las aplicaciones web y otras amenazas convirtiéndose en un riesgo menor a medida que las tecnologías cambian.
La [última versión][top10] fue publicada en 2021 y cada categoría se resume a continuación.

Tenga en cuenta que existen varios proyectos 'OWASP Top Ten', por ejemplo,
el 'OWASP Top 10 para Aplicaciones de Modelos Extensos de Lenguaje',
por lo que para evitar confusiones se debe tener en cuenta el contexto al referirse a estas listas.

#### A01:2021 Pérdida de Control de Acceso

El control de acceso involucra el uso de mecanismos de protección que pueden categorizarse como:

* Autenticación (evidenciar la identidad de un actor)
* Autorización (asegurar que un actor dado tenga acceso a un recurso)
* Responsabilidad (seguimiento de las actividades realizadas)

La Pérdida de Control de Acceso ocurre cuando el producto no restringe, o restringe incorrectamente,
el acceso a un recurso por parte de un actor no autorizado o malicioso. Cuando un control de seguridad falla
o no se aplica, los atacantes pueden comprometer la seguridad del producto obteniendo privilegios,
leyendo información sensible, ejecutando comandos, evadiendo la detección, etc.

La Pérdida de Control de Acceso puede tomar muchas formas, como la navegación por directorios
o la elevación de privilegios, por lo cual consulte tanto la [Enumeración de Debilidades Comunes CWE-284][cwe284]
como [A01 Pérdida de Control de Acceso][a01] y también siga las diversas
[Hojas de Referencia de OWASP][a01cs] relacionadas con los controles de acceso.

#### A02:2021 Fallos Criptográficos

Refiriéndose a [OWASP Top 10 A02:2021][a02], los datos sensibles deben protegerse tanto en reposo como en tránsito.
Los fallos criptográficos ocurren cuando el control de seguridad criptográfico ha sido vulnerado o no se aplica,
y los datos quedan expuestos a actores no autorizados, maliciosos o no.

Es importante proteger los datos tanto en reposo, cuando están almacenados en un área de memoria,
como cuando están en tránsito, como cuando se transmiten a través de un canal de comunicación o se están transformando.
Un buen ejemplo de protección de transformación de datos se da en [A02 Fallos Criptográficos][a02]
donde los datos sensibles están correctamente cifrados en una base de datos,
pero la función de exportación descifra automáticamente los datos, llevando a la exposición de datos sensibles.

Los fallos criptográficos pueden tomar muchas formas y pueden ser sutiles - un control de seguridad que
parece seguro puede ser fácilmente vulnerado.
Siga las [Hojas de Referencia][a02cs] de criptografía para implementar los controles criptográficos básicos
y considere establecer una auditoría criptográfica.

#### A03:2021 Inyección

La falta de validación y sanitización de entrada puede llevar a operaciones de inyección,
y este riesgo ha sido una característica constante del OWASP Top Ten desde que se publicó la primera versión en 2003.
Estas vulnerabilidades ocurren cuando se utilizan directamente datos hostiles dentro de la aplicación
y pueden resultar en que datos maliciosos se utilicen para modificar la aplicación; consulte [A03 Inyección][a03]
para más explicaciones.

El control de seguridad es directo: todas las entradas de fuentes no confiables deben ser sanitizadas y validadas.
Consulte las [Hojas de Referencia de Inyección][a03cs] para los diversos tipos de entrada y sus controles.

#### A04:2021 Diseño Inseguro

Es importante que la seguridad se incorpore en las aplicaciones desde el principio
y no se aplique como una ocurrencia tardía.
La categoría [A04 Diseño Inseguro][a04] reconoce esto y aconseja que el uso del modelado de amenazas,
patrones de diseño seguro y arquitecturas de referencia debe incorporarse dentro de las actividades de diseño
y arquitectura de la aplicación.

En la práctica, esto implica establecer un ciclo de vida de desarrollo seguro que fomente
la identificación de requisitos de seguridad, el uso habitual del modelado de amenazas y la inclusión de bibliotecas
y marcos seguros existentes.
Esta categoría se introdujo en la versión 2021 y por ahora las hojas de referencia de soporte solo cubren
el [modelado de amenazas][cstm]; a medida que esta categoría se establezca más,
se espera que más información de soporte esté disponible.

#### A05:2021 Configuración Incorrecta de Seguridad

Los sistemas y aplicaciones grandes suelen ser configurables,
y esta configuración a menudo se utiliza para asegurar el sistema/aplicación.
Si esta configuración se aplica incorrectamente, la aplicación puede dejar de ser segura y,
en su lugar, ser susceptible a vulneraciones bien conocidas.
La página [A05 Configuración Incorrecta de Seguridad][a05] contiene un ejemplo común de configuración incorrecta
donde las cuentas predeterminadas y sus contraseñas siguen habilitadas y sin cambios.
Estas contraseñas y cuentas suelen ser bien conocidas y proporcionan una manera fácil
para que los actores maliciosos pongan en peligro las aplicaciones.

Tanto el [OWASP Top 10 A05:2021][a05] como las [Hojas de Referencias de OWASP][a05cs] vinculadas proporcionan estrategias
para establecer un proceso concertado y repetible de configuración de seguridad de aplicaciones
para minimizar la configuración incorrecta.

#### A06:2021 Componentes Vulnerables y Desactualizados

Quizás una de las actividades de seguridad más fáciles y efectivas es mantener actualizadas
todas las dependencias de software de terceros.
Si un actor malicioso identifica una dependencia vulnerable durante la fase de reconocimiento de un ataque,
hay bases de datos disponibles, como [Exploit Database][exploit], que proporcionarán una descripción de cualquier exploit.
Estas bases de datos también pueden proporcionar scripts y técnicas ya preparados
para atacar una vulnerabilidad dada, facilitando la explotación de dependencias de software de terceros vulnerables.

El riesgo [A06 Componentes Vulnerables y Desactualizados][a06] subraya la importancia de esta actividad
y recomienda que las correcciones y actualizaciones de la plataforma subyacente,
marcos y dependencias se basen en una evaluación de riesgos y se realicen de manera "oportuna".
Se pueden usar varias herramientas para analizar dependencias y marcar vulnerabilidades,
consulte las [Hojas de Referencias][a06cs] para estas.

#### A07:2021 Fallos de Identificación y Autenticación

La confirmación de la identidad del usuario, la autenticación y la gestión de sesiones es crítica
para proteger el sistema o aplicación contra ataques relacionados con la autenticación.
Refiriéndose al riesgo [A07 Fallos de Identificación y Autenticación][a07],
la autorización puede fallar de varias maneras que a menudo involucran otros riesgos del OWASP Top Ten:

* controles de acceso vulnerados (A01)
* fallo criptográfico (A02)
* contraseñas predeterminadas (A05)
* bibliotecas desactualizadas (A06)

Consulte las [Hojas de Referencia][a07cs] para las varias buenas prácticas que se necesitan para una autorización segura.
También hay proveedores externos de Gestión de Identidad y Acceso (IAM) que proporcionarán esto como servicio,
considere el costo/beneficio de usar estos proveedores (a menudo comerciales).

#### A08:2021 Fallos de Integridad de Software y Datos

Los fallos de integridad de software y datos se relacionan con código e infraestructura
que no protege contra violaciones de integridad.
Esta es una categoría de amplio alcance que describe [ataques a la cadena de suministro][cschain],
actualizaciones automáticas comprometidas y uso de componentes no confiables,por ejemplo.
[A08 Fallos de Integridad de Software y Datos][a08] fue una nueva categoría introducida en 2021,
por lo que hay poca información disponible en las [Hojas de Referencia][a08cs],
pero esto seguramente cambiará para una amenaza tan importante.

#### A09:2021 Fallos en el Registro y Monitoreo de Seguridad

El registro y monitoreo ayuda a detectar, escalar y responder a infracciones activas;
sin éste, las infracciones no serán detectadas.
[A09 Fallos en el Registro y Monitoreo de Seguridad][a09] enumera varias técnicas de registro
y monitoreo que deberían ser familiares, pero también otras que pueden no ser tan comunes;
por ejemplo, monitorear la cadena de suministro de DevOps puede ser tan importante como monitorear la aplicación o sistema.
Las [Hojas de referencia][a09cs] proporcionan orientación sobre registro suficiente
y también proporcionan un vocabulario común de registro.
El objetivo de este vocabulario común es proporcionar un registro que utilice un conjunto común de términos,
formatos y palabras clave; y esto permite facilitar el monitoreo, análisis y las alertas.

#### A10:2021 Falsificación de Solicitud del Lado del Servidor

Refiriéndose a [A10 Falsificación de Solicitudes del Lado del Servidor (SSRF)][a10],
estas vulnerabilidades pueden ocurrir cuando una aplicación web está recuperando un recurso remoto
sin validar la URL proporcionada por el usuario.
Estos exploits permiten a un atacante forzar a la aplicación a enviar una solicitud manipulada a un destino inesperado,
incluso cuando está protegido por un firewall, VPN u otro tipo de lista de control de acceso a la red.
Recuperar una URL se ha convertido en un escenario común para las aplicaciones web modernas
y como resultado la incidencia de SSRF está aumentando, especialmente para [servicios en la nube][cscloud]
y arquitecturas de aplicaciones más complejas.

Esta es una nueva categoría introducida en 2021 con una única (por ahora)
[Hoja de Referencia][a10cs] que trata acerca de SSRF.

#### Proyectos Top 10 de OWASP

Hay varios proyectos 'Top 10' creados por OWASP que, dependiendo del contexto,
también pueden ser referidos como 'Top 10 de OWASP'.
Aquí hay una lista de los proyectos 'Top 10 de OWASP' estables:

* [Top 10 de Seguridad de API][apisec]
* [Top 10 de Seguridad de Datos][data10]
* [Top 10 sin código o Low-Code/No-Code][lcnc10]
* [Top 10 Móvil][mobile10]
* [Top 10 sin Servidor o Serverless][serverless10]
* [Top 10 de Riesgos de Seguridad CI/CD][cicd10]
* [Top 10 para Aplicaciones de Modelos Extensos de Lenguaje][llm10]
* [Top 10 de Riesgos de Privacidad][privacy10]
* [Top 10 de Controles Proactivos][proactive10]
* [Top 10 de Riesgos de Seguridad en Aplicaciones Web][top10]

Otros Top 10 de OWASP son proyectos 'incubadora', que están en progreso, por lo que esta lista cambiará con el tiempo.

----

Traducción de versión [original en inglés][en0405].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario;
si ve algo que necesita cambios, entonces [cree un issue][issue0405] o [edítelo en GitHub][edit0405].

[a01]: https://owasp.org/Top10/A01_2021-Broken_Access_Control/
[a01cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a012021-broken-access-control
[a02]: https://owasp.org/Top10/A02_2021-Cryptographic_Failures/
[a02cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a022021-cryptographic-failures
[a03]: https://owasp.org/Top10/A03_2021-Injection/
[a03cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a032021-injection
[a04]: https://owasp.org/Top10/A04_2021-Insecure_Design/
[a05]: https://owasp.org/Top10/A05_2021-Security_Misconfiguration/
[a05cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a052021-security-misconfiguration
[a06]: https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/
[a06cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a062021-vulnerable-and-outdated-components
[a07]: https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/
[a07cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a072021-identification-and-authentication-failures
[a08]: https://owasp.org/Top10/A08_2021-Software_and_Data_Integrity_Failures/
[a08cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a082021-software-and-data-integrity-failures
[a09]: https://owasp.org/Top10/A09_2021-Security_Logging_and_Monitoring_Failures/
[a09cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a092021-security-logging-and-monitoring-failures
[a10]: https://owasp.org/Top10/A10_2021-Server-Side_Request_Forgery_%28SSRF%29/
[a10cs]: https://cheatsheetseries.owasp.org/IndexTopTen.html#a102021-server-side-request-forgery-ssrf
[apisec]: https://owasp.org/API-Security
[cicd10]: https://owasp.org/www-project-top-10-ci-cd-security-risks/
[cschain]: https://cheatsheetseries.owasp.org/cheatsheets/Software_Supply_Chain_Security_Cheat_Sheet
[cscloud]: https://cheatsheetseries.owasp.org/cheatsheets/Secure_Cloud_Architecture_Cheat_Sheet
[cstm]: https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet
[cwe284]: https://cwe.mitre.org/data/definitions/284.html
[data10]: https://owasp.org/www-project-data-security-top-10/
[edit0405]: https://github.com/OWASP/DevGuide/blob/main/docs/es/02-foundations/05-top-ten.md
[exploit]: https://www.exploit-db.com/
[en0405]: https://devguide.owasp.org/en/02-foundations/05-top-ten/
[issue0405]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2002-foundations/05-top-ten
[lcnc10]: https://owasp.org/www-project-top-10-low-code-no-code-security-risks/
[mobile10]: https://owasp.org/www-project-mobile-top-10/
[privacy10]: https://owasp.org/www-project-top-10-privacy-risks/
[proactive10]: https://owasp.org/www-project-proactive-controls/
[samm]: https://owaspsamm.org/about/
[serverless10]: https://owasp.org/www-project-serverless-top-10/
[top10project]: https://owasp.org/www-project-top-ten/
[top10]: https://owasp.org/Top10/
[llm10]: https://owasp.org/www-project-top-10-for-large-language-model-applications/
