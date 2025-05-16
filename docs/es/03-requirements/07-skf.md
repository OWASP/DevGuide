![SKF logo](../../assets/images/logos/skf.png "OWASP SKF"){ align=right width=180 }

El framework de conocimientos de seguridad[Security Knowledge Framework][skf] (SKF)
es una aplicación de sistema experto que utiliza varios proyectos de código abierto
para apoyar a los equipos de desarrollo y arquitectos de seguridad en la construcción de aplicaciones seguras.
El SKF se basa en el [Estándar de Verificación de Seguridad de Aplicaciones][asvs] (ASVS) de OWASP
para ayudar a los desarrolladores tanto en las fases previas al desarrollo como posteriores al desarrollo
y crear aplicaciones seguras por diseño.

Después de haber sido un proyecto insignia de OWASP durante muchos años, el SKF ya no forma parte de la organización OWASP;
y continuará siendo referenciado en el OWASP Wayfinder y otros proyectos de OWASP
porque es un proyecto insignia para cualquier organización.

#### ¿Qué es el Security Knowledge Framework?

El [SKF][skf] es una aplicación web que está disponible en el [repositorio de github][skfinstall].
Hay una [versión demo][skfdemo] de SKF que es útil para explorar los múltiples beneficios del SKF.
Tenga en cuenta que SKF está en proceso de migración a un [nuevo repositorio][skfrepo]
por lo que el enlace de descarga puede cambiar.

El SKF proporciona capacitación y orientación para la seguridad de aplicaciones:

* [Organizador][skfreqs] de requisitos
* [Cursos][skfdemo] de aprendizaje:
  * Desarrollo de Software Seguro (LFD121)
  * Entendiendo las 10 Principales Amenazas de Seguridad de OWASP (SKF100)
  * Desarrollo de Software Seguro: Implementación (LFD105x)
* [Laboratorios][skflabs] de práctica
* Documentación sobre [instalación y uso][skfdocs] del SKF

#### ¿Por qué usar el SKF para requisitos?

El SKF organiza los requisitos de seguridad en varias categorías que proporcionan un buen punto de partida
para la seguridad de aplicaciones.

* API y Servicio Web
* Control de Acceso
* Arquitectura, Diseño y Modelado de Amenazas
* Autenticación
* Lógica de Negocio
* Comunicación
* Configuración
* Protección de Datos
* Manejo de Errores y Registro
* Archivos y Recursos
* Código Malicioso
* Gestión de Sesiones
* Criptografía Almacenada
* Validación, Sanitización y Codificación

#### Cómo usar el SKF para requisitos

Visite el [sitio web de la herramienta de requisitos][skfreqs]
y seleccione los requisitos relevantes de las diversas categorías.
Exporte la selección al formato de su elección (Markdown, hoja de cálculo CSV o texto plano)
y utilícelo como punto de partida para los requisitos de seguridad de la aplicación.

La serie OWASP Spotlight proporciona una visión general del SKF:
'Proyecto 7 - [Security Knowledge Framework (SKF)][spotlight07]'.

#### Referencias

* [Security Knowledge Framework][skf] (SKF)
* [Cursos y laboratorios de SKF][skfdemo]
* [Requisitos de SKF][skfreqs]
* OWASP [Estándar de Verificación de Seguridad de Aplicaciones][asvs] (ASVS)

----

Traducción de versión [original en inglés][en0507].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiar
entonces [cree un issue][issue0507] o [edítelo en GitHub][edit0507].

[asvs]: https://owasp.org/www-project-application-security-verification-standard/
[edit0507]: https://github.com/OWASP/DevGuide/blob/main/docs/es/03-requirements/07-skf.md
[en0507]: https://devguide.owasp.org/en/03-requirements/07-skf/
[issue0507]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2003-requirements/07-skf
[skf]: https://www.securityknowledgeframework.org/
[skfdemo]: https://secureby.design/
[skfdocs]: https://skf.readme.io/docs/introduction
[skfinstall]: https://github.com/blabla1337/skf-flask/releases
[skflabs]: https://secureby.design/labs
[skfrepo]: https://github.com/Security-Knowledge-Framework
[skfreqs]: https://starfish-app-kd3eo.ondigitalocean.app/
[spotlight07]: https://youtu.be/TFX_ZBy6lNY
