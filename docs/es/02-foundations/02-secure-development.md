El desarrollo seguro se describe en las funciones de negocio de [Diseño][sammd], [Implementación][sammi]
y [Verificación][sammv] del Modelo de Madurez de Aseguramiento de Software
de OWASP [(SAMM-Software Assurance Maturity Model)][samm].

#### Introducción

La mejor introducción al desarrollo práctico de software seguro es el artículo de OWASP
sobre [Fragmentación de la Seguridad de Aplicaciones][sdlc]:

_O cómo me preocupé menos y me apoyé en los hombros de gigantes._ - Spyros Gasteratos, Elie Saad

Gran parte del material de esta sección fue extraído del proyecto [Estándares de Integración][intstand] de OWASP.

#### Descripción general

Casi todo el software moderno se desarrolla de manera iterativa, pasando por diferentes fases,
como la identificación de requisitos del cliente, implementación y testeo.
Estas fases se vuelven a aplicar de forma cíclica a lo largo de la vida útil de la aplicación.
A continuación se muestra un Ciclo de Vida de Desarrollo de Software (SDLC) teórico; en la práctica, puede haber más
o menos fases según los procesos adoptados por la organización.

![Ciclo de vida SDLC](../../assets/images/sdlc_diag.png "ciclo de vida SDLC teórico"){: .image-right }

Con el creciente número y sofisticación de los ataques contra casi todas las aplicaciones o sistemas empresariales,
la mayoría de las empresas han adoptado un Ciclo de Vida de Desarrollo de Software (SDLC) seguro.
El SDLC seguro nunca debe ser un ciclo de vida separado del ciclo de vida de desarrollo de software existente,
sino que debe ser siempre el mismo ciclo de vida de desarrollo que antes,
pero con acciones de seguridad integradas en cada fase.
De lo contrario, las acciones de seguridad pueden ser dejadas de lado por equipos de desarrollo ocupados.
Tenga en cuenta que aunque el SDLC Seguro podría escribirse como 'SSDLC', casi siempre se escribe como 'SDLC'.

DevOps integra y automatiza muchas de las fases del SDLC e implementa canales(pipelines) de Integración Continua (CI)
y Entrega/Despliegue Continuo (CD) para proporcionar gran parte de la automatización del SDLC.

DevOps y los canales han sido explotados con éxito con graves consecuencias a gran escala, por lo que,
de manera similar al SDLC, muchas de las acciones de DevOps también han incorporado seguridad.
DevOps seguro, o DevSecOps, incorpora prácticas de seguridad en las actividades de DevOps
para protegerse contra ataques y proporcionar al SDLC pruebas de seguridad automatizadas.

Ejemplos de cómo DevSecOps está "incorporando seguridad" son la provisión de
Pruebas de Seguridad de Aplicaciones Interactivas, Estáticas y Dinámicas (IAST, SAST y DAST)
y la implementación de seguridad en la cadena de suministro,
y hay muchas otras actividades de seguridad que se pueden aplicar.
Consulte la [hoja de Referencia de Seguridad CI/CD][cscicd] para conocer los últimos controles de seguridad de DevSecOps.

#### Ciclo de vida de desarrollo seguro

Refiriéndonos al ciclo de desarrollo de [Wayfinder para Seguridad de Aplicaciones][intstand] de OWASP,
hay cuatro fases iterativas durante el desarrollo de la aplicación:
Requerimientos, Diseño, Implementación y Verificación.
Las otras fases se realizan de manera menos iterativa en el ciclo de desarrollo,
pero forman una parte igualmente importante del SDLC:
Análisis de Brechas, Métricas, Operación y también Formación y Construcción de Cultura.

Todas estas fases del SDLC deberían tener actividades de seguridad integradas,
en lugar de realizarse como actividades separadas.
Si la seguridad se integra en estas fases, la sobrecarga se vuelve mucho menor
y la resistencia de los equipos de desarrollo disminuye.
El objetivo es que el SDLC seguro se convierta en un proceso tan familiar como antes,
con los equipos de desarrollo asumiendo plena responsabilidad de las actividades de seguridad dentro de cada fase.

Hay muchas herramientas y recursos de OWASP para ayudar a integrar la seguridad en el SDLC.

* **Requerimientos**: esta fase determina los requisitos funcionales, no funcionales y de seguridad para la aplicación.
Los requerimientos deben revisarse periódicamente y verificarse su completitud y validez,
y vale la pena considerar varias herramientas de OWASP para ayudar con esto;
  * el [Estándar de Verificación de Seguridad de Aplicaciones (ASVS)][asvs] proporciona a los desarrolladores
    una lista de requisitos para el desarrollo seguro,
  * el [proyecto de Seguridad de Aplicaciones Móviles][masproject] proporciona un estándar de seguridad
    para aplicaciones móviles y [SecurityRAT][srat] ayuda a identificar un conjunto inicial de requisitos de seguridad.

* **Diseño**: es importante diseñar la seguridad en la aplicación - nunca es demasiado tarde para hacerlo,
pero cuanto antes mejor y más fácil de hacer. OWASP proporciona dos herramientas,
[Modelado de Amenazas Pythónico][pytm] y [Threat Dragon][tdtm],
para el modelado de amenazas junto con la gamificación de seguridad usando [Cornucopia][cornucopia].

* **Implementación**: el proyecto [Top 10 Controles Proactivos][proactive10] de OWASP afirma que estos son
"los controles y categorías de control más importantes que todo arquitecto y desarrollador debería incluir sin duda,
al 100% en cada proyecto" y éste ciertamente es un buen consejo.
Implementar estos controles puede proporcionar un alto grado de confianza en que la aplicación
o sistema será razonablemente seguro.
OWASP proporciona dos bibliotecas que se pueden incorporar en aplicaciones web, la librería de control de seguridad
[API de Seguridad Empresarial (ESAPI)][esapi-project]
y [CSRFGuard][csrfguard] para mitigar el riesgo de ataques de [Falsificación de Solicitudes entre Sitios][cscsrf] (CSRF),
que ayudan a implementar estos controles proactivos.
Además, la [serie de Hojas de Referencia][csproject] de OWASP es una valiosa fuente de información
y consejos sobre todos los aspectos de la seguridad de las aplicaciones.

* **Verificación**: OWASP proporciona un número relativamente grande de proyectos que ayudan con las pruebas
y la verificación. Este es el tema de una sección en esta Guía del Desarrollador,
y los proyectos están enumerados al final de esta sección.

* **Formación**: los equipos de desarrollo necesitan continuamente formación en seguridad.
Aunque no forma parte del ciclo iterativo interno del SDLC, la formación todavía debe considerarse en el ciclo de vida
del proyecto. OWASP proporciona muchos entornos y materiales de formación - vea la lista al final de esta sección.

* **Desarrollo de Cultura**: una buena cultura de seguridad dentro de una organización empresarial
ayudará enormemente a mantener seguras las aplicaciones y los sistemas.
Hay muchas actividades que en conjunto ayudan a crear la cultura de seguridad,
el proyecto [Cultura de Seguridad][culture] de OWASP entra en más detalle sobre estas actividades,
y un buen programa de Campeones de Seguridad dentro del negocio es fundamental para una buena postura de seguridad.
La [Guía de Defensores de Seguridad][champions] de OWASP proporciona orientación y material para crear defensores de
seguridad dentro de los equipos de desarrollo - idealmente cada equipo debería tener un defensor de seguridad
que tenga un interés especial en la seguridad y haya recibido formación adicional,
permitiendo al equipo integrar la seguridad.

* **Operaciones**: la [Guía de DevSecOps][devsecops] de OWASP explica cómo implementar mejor un canal(pipeline) seguro,
utilizando mejores prácticas y herramientas de automatización para ayudar a reducir tiempo
y costos al resolver los problemas de seguridad ya en etapas tempranas del proyecto(principio shift-left).
Consulte la Guía de DevSecOps para obtener más información sobre cualquiera de los temas dentro de DevSecOps
y en particular las secciones sobre Operaciones.

* **Cadena de suministro**: los ataques que aprovechan la cadena de suministro pueden ser devastadores
y ha habido varios casos de alto perfil de productos que han sido explotados con éxito.
Una Lista de Materiales de Software (SBOM-Software Bill of Materials) es el primer paso para evitar estos ataques
y vale la pena utilizar el estándar [CycloneDX][cyclone] de OWASP para la Lista de Materiales (BOM-Bill of Materials)
estándar para la [reducción de riesgos en la cadena de suministro][cschain].
Además, el proyecto [Dependency-Track][deptrack] de OWASP es una Plataforma de Análisis Continuo de SBOM
que puede ayudar a prevenir estas explotaciones de la cadena de suministro proporcionando control del SBOM.

* **Dependencias de terceros**: mantener un seguimiento de qué bibliotecas de terceros se incluyen en la aplicación,
y qué vulnerabilidades tienen, es fácilmente automatizable. Muchos repositorios públicos como [github][github]
y [gitlab][gitlab] ofrecen este servicio junto con algunos proveedores comerciales.
OWASP proporciona la herramienta de Análisis de Composición de Software (SCA-Software Composition Analysis)
[Dependency-Check][depcheck] para rastrear bibliotecas externas.

* **Pruebas de seguridad de aplicaciones**: hay varios tipos de pruebas de seguridad que se pueden automatizar
en solicitudes de admisión de código (pull-requests), fusiones(merges)
o compilaciones nocturnas, o incluso manualmente, pero son más poderosas cuando se automatizan.
Comúnmente hay Pruebas de Seguridad de Aplicaciones Estáticas
(SAST-Static Application Security Testing), que analizan el código sin ejecutarlo,
y Pruebas de Seguridad de Aplicaciones Dinámicas (DAST-Dynamic Application Security Testing),
que aplican entrada a la aplicación mientras se ejecuta en un sandbox u otros tipos de entornos aislados.
Las Pruebas de Seguridad de Aplicaciones Interactivas (IAST-Interactive Application Security Testing)
están diseñadas para ejecutarse manualmente así como automatizadas,
y proporcionan retroalimentación instantánea sobre las pruebas mientras se ejecutan.

#### Lecturas adicionales de OWASP

* [Serie de Hojas de Referencia][csproject]
* [Hoja de Referencia de Seguridad CI/CD][cscicd]
* [Cornucopia][cornucopia]
* Estándar de Lista de Materiales (BOM) [CycloneDX][cyclone]
* [Guía de DevSecOps][devsecops]
* [Guía de Defensores de Seguridad][champions]
* [Proyecto de Cultura de Seguridad][culture]
* [Top 10 Controles Proactivos][proactive10]

#### Proyectos de verificación de OWASP

* [Estándar de Verificación de Seguridad de Aplicaciones][asvs] (ASVS)
* [Proyecto Amass][amass]
* [Code Pulse][pulse]
* [Defect Dojo][defectdojo]
* [Seguridad de Aplicaciones Móviles][masproject] (MAS)
* [Nettacker][net]
* [Framework de Pruebas Web Ofensivas][owtf] (OWTF)
* [Guía de Pruebas de Seguridad Web][wstg] (WSTG)
* [Zed Attack Proxy][zap] (ZAP)

#### Proyectos de formación de OWASP

* [Proyecto de Seguridad API][apisec] (API Top 10)
* [Juice Shop][juice]
* [Mobile Top 10][mobile10]
* [Security Shepherd][sec-shep]
* [Snakes And Ladders][snakes]
* [Top 10 de Riesgos de Seguridad en Aplicaciones Web][top10]
* [WebGoat][webgoat]

#### Recursos de OWASP

* [Librería CSRFGuard][csrfguard]
* [Análisis de Composición de Software (SCA) Dependency-Check][depcheck]
* [Plataforma de Análisis Continuo de SBOM Dependency-Track][deptrack]
* [API de Seguridad Empresarial][esapi-project] (ESAPI)
* [Proyecto de Estándares de Integración Wayfinder de Seguridad de Aplicaciones][intstand]
* [Seguridad de Aplicaciones Móviles][mas] (MAS)
* [Modelado de Amenazas Pythónico][pytm]
* [Threat Dragon][tdtm]
* [SecurityRAT][srat] (Herramienta de Automatización de Requisitos)

----

La Guía para Desarrolladores de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse,
[cree un issue][issue0402] o [edítelo en GitHub][edit0402].

[amass]: https://owasp.org/www-project-amass/
[apisec]: https://owasp.org/API-Security
[asvs]: https://owasp.org/www-project-application-security-verification-standard/
[champions]: https://owasp.org/www-project-security-champions-guidebook/
[cscicd]: https://cheatsheetseries.owasp.org/cheatsheets/CI_CD_Security_Cheat_Sheet
[cornucopia]: https://owasp.org/www-project-cornucopia/
[cschain]: https://cheatsheetseries.owasp.org/cheatsheets/Software_Supply_Chain_Security_Cheat_Sheet
[cscsrf]: https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet
[csproject]: https://owasp.org/www-project-cheat-sheets/
[csrfguard]: https://owasp.org/www-project-csrfguard/
[culture]: https://owasp.org/www-project-security-culture/
[cyclone]: https://owasp.org/www-project-cyclonedx/
[depcheck]: https://owasp.org/www-project-dependency-check/
[deptrack]: https://dependencytrack.org/
[devsecops]: https://owasp.org/www-project-devsecops-guideline/
[defectdojo]: https://www.defectdojo.org/
[edit0402]: https://github.com/OWASP/DevGuide/blob/main/docs/es/02-foundations/02-secure-development.md
[esapi-project]: https://owasp.org/www-project-enterprise-security-api/
[github]: https://github.com/
[gitlab]: https://about.gitlab.com/
[issue0402]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2002-foundations/02-secure-development
[juice]: https://owasp.org/www-project-juice-shop/
[mas]: https://mas.owasp.org/
[masproject]: https://owasp.org/www-project-mobile-app-security/
[mobile10]: https://owasp.org/www-project-mobile-top-10/
[net]: https://owasp.org/www-project-nettacker/
[owtf]: https://owasp.org/www-project-owtf/
[proactive10]: https://owasp.org/www-project-proactive-controls/
[pulse]: https://owasp.org/www-project-code-pulse/
[pytm]: https://owasp.org/www-project-pytm/
[samm]: https://owaspsamm.org/about/
[sammd]: https://owaspsamm.org/model/design/
[sammi]: https://owaspsamm.org/model/implementation/
[sammv]: https://owaspsamm.org/model/verification/
[sdlc]: https://owasp.org/www-project-integration-standards/writeups/owasp_in_sdlc/
[sec-shep]: https://owasp.org/www-project-security-shepherd/
[snakes]: https://owasp.org/www-project-snakes-and-ladders/
[srat]: https://owasp.org/www-project-securityrat/
[tdtm]: https://owasp.org/www-project-threat-dragon/
[top10]: https://owasp.org/Top10/
[intstand]: https://owasp.org/www-project-integration-standards/
[webgoat]: https://owasp.org/www-project-webgoat/
[wstg]: https://owasp.org/www-project-web-security-testing-guide/
[zap]: https://www.zaproxy.org/
