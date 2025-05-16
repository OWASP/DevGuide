![OpenCRE logo](../../assets/images/logos/opencre.png "OWASP OpenCRE"){ width=300 }

El [Enumeración Común Abierta de Requisitos][opencre] (OpenCRE) es un catálogo de requisitos de seguridad:
enumerando temas de seguridad y proporcionando enlaces a varios estándares, hojas de referencia y guías.

El proyecto de [Estándares de Integración][intstand] de OWASP incluye tanto OpenCRE como Seguridad
y el Navegador de Seguridad de Aplicaciones, es un proyecto de documentación de OWASP con estado de producción.

#### ¿Qué es el proyecto de Estándares de Integración?

El proyecto de [Estándares de Integración][intstand] está en el centro de la comunidad de proyectos OWASP;
proporciona orientación sobre cómo navegar y utilizar los numerosos proyectos dentro de OWASP.
Lo hace de dos maneras, primero está el [Navegador de Seguridad de Aplicaciones][intstand] que proporciona un mapa visual
de los proyectos de OWASP más importantes - a agosto de 2024 hay 345 [proyectos OWASP][projects]
por lo que esta es una visualización realmente útil.
La segunda es la Enumeración Común Abierta de Requisitos ([OpenCRE][opencre])
que proporciona una referencia consolidada de
estándares, hojas de referencias, herramientas y otras enumeraciones (como [CWE][cwe]).

El proyecto de Estándares de Integración también ha producido un informe
sobre [Fragmentación de Seguridad de Aplicaciones][sdlc] de OWASP
sobre OWASP y el Ciclo de Vida de Desarrollo de Software (SDLC) seguro.
Esto proporciona una visión general de herramientas y técnicas utilizadas en la mayoría de los SDLC.

#### ¿Qué es OpenCRE?

[OpenCRE][opencre] es un catálogo o enumeración de varios estándares y material de referencia, incluyendo:

* [CAPEC][capecocre]
* [CWE][cweocre]
* [Publicaciones Especiales de NIST][nist] [800-53][nist53] y [800-63][nist63]
* OWASP [ASVS][asvs]
* OWASP [Top10][top10ocre]
* OWASP [Controles Proactivos][proactiveocre]
* OWASP [Hojas de Referencia][csocre]
* OWASP [WSTG][wstgocre]
* [ZAP][zapocre]

El objetivo de este proyecto es 'Vincular todas las cosas con OpenCRE', lo que:

* Facilitará a ingenieros, oficiales de seguridad, evaluadores y departamentos de compras encontrar información relevante
* Facilitará a los creadores de estándares crear y mantener referencias

#### ¿Por qué usar OpenCRE?

OpenCRE: 'Todo organizado'

[OpenCRE][opencre] es una herramienta poderosa que puede proporcionar a los desarrolladores enlaces a muchos recursos,
y es fácil de usar.
Proporciona un conjunto consolidado de referencias sobre varios términos y dominios de seguridad,
y lo crucial es que se mantienen automáticamente actualizados.
Proporciona un práctico catálogo de seguridad que se puede buscar para diversos estándares o términos de seguridad.

Además de ser útil para preguntas cotidianas de seguridad,
OpenCRE también puede usarse como sección de referencias en documentación;
vincular a OpenCRE en lugar de proporcionar una lista de referencias significa
que los enlaces se mantienen automáticamente actualizados.

#### Cómo usar OpenCRE

El catálogo de [OpenCRE][opencre] se puede acceder de formas tradicionales como usar búsquedas o vincular directamente.
Por ejemplo, las referencias de OpenCRE a la Enumeración de Debilidades Comunes pueden accederse
usando la [función de búsqueda][cweocre]
o vinculando directamente a un [Requisito Común Abierto específico][cwe1002].

OpenCRE también es útil al proporcionar referencias en documentación.
OpenCRE puede usarse para estas referencias en lugar de listar varias referencias a un concepto o requisito de seguridad.
Esto proporcionará enlaces a estándares, hojas de referencia, herramientas y otras enumeraciones -
junto con otras fuentes que se han agregado con el tiempo - y todo se mantiene actualizado.
¡Así que no más enlaces rotos o referencias a versiones desactualizadas! :)

Ahora estamos en la era de los modelos extensos de lenguaje, y OpenCRE ha adoptado esta tecnología.
Respuestas inmediatas a preguntas de seguridad o búsquedas pueden proporcionarse por [OpenCRE Chat][opencrechat].

Por ejemplo, en respuesta a la pregunta "_¿De qué sirve la Guía de Desarrollador de OWASP?_"
OpenCRE Chat proporciona la siguiente respuesta:

_"La Guía de Desarrollador de OWASP proporciona una visión general completa de los riesgos de seguridad de aplicaciones_
_y cómo mitigarlos._
_Cubre temas como validación de entrada, codificación de salida, prácticas de codificación segura_
_y principios de diseño seguro._
_La guía es un recurso valioso para desarrolladores que quieren crear aplicaciones seguras."_

#### Referencias

* OWASP [OpenCRE][opencre]
* [Spotlight sobre OpenCRE][spotlight28]
* [Fragmentación de Seguridad de Aplicaciones][sdlc] de OWASP
* Proyecto de [Estándares de Integración][intstand] de OWASP
* [Comprendiendo la Cadena Completa de Seguridad de Aplicaciones Usando OpenCRE org][opencretalk]

----

Traducción de versión [original en inglés][en0503].

La Guía de Desarrollador OWASP es un esfuerzo comunitario; si hay algo que necesite cambios
entonces [cree un issue][issue0503] o [edítelo en GitHub][edit0503].

[asvs]: https://owasp.org/www-project-application-security-verification-standard/
[capecocre]: https://opencre.org/search/CAPEC
[csocre]: https://opencre.org/search/OWASP%20Cheat%20Sheets
[cweocre]: https://opencre.org/search/CWE
[cwe]: https://cwe.mitre.org/
[cwe1002]: https://www.opencre.org/node/standard/CWE/sectionid/1002
[edit0503]: https://github.com/OWASP/DevGuide/blob/main/docs/es/03-requirements/03-opencre.md
[en0503]: https://devguide.owasp.org/en/03-requirements/03-opencre/
[intstand]: https://owasp.org/www-project-integration-standards/
[issue0503]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2003-requirements/03-opencre
[nist]: https://csrc.nist.gov/
[nist53]: https://www.nist.gov/privacy-framework/nist-privacy-framework-and-cybersecurity-framework-nist-special-publication-800-53
[nist63]: https://pages.nist.gov/800-63-3/
[opencre]: https://www.opencre.org/
[opencrechat]: https://www.opencre.org/chatbot
[opencretalk]: https://www.youtube.com/watch?v=VPOkT9quve0
[proactiveocre]: https://www.opencre.org/search/Proactive%20Controls
[projects]: https://owasp.org/projects/
[sdlc]: https://owasp.org/www-project-integration-standards/writeups/owasp_in_sdlc/
[spotlight28]: https://www.youtube.com/watch?v=TwNroVARmB0&list=PLUKo5k_oSrfOTl27gUmk2o-NBKvkTGw0T
[top10ocre]: https://www.opencre.org/search/OWASP%20Top%2010
[wstgocre]: https://opencre.org/search/WSTG
[zapocre]: https://opencre.org/search/ZAP
