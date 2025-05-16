Las Prácticas de Codificación Segura en Go de OWASP (Go-SCP) son un conjunto de prácticas de codificación segura
para el lenguaje de programación Go.

El [proyecto de documentación Go-SCP][go-scp-project] es un Proyecto Incubadora de OWASP
que tiene suficiente soporte a largo plazo para alcanzar pronto el estado de Laboratorio.
El documento publicado puede ser [descargado en varios formatos][go-scp-download] desde el repositorio de GitHub.

#### ¿Qué es Go-SCP?

Go-SCP proporciona ejemplos y recomendaciones para ayudar a los desarrolladores a evitar errores e inconvenientes comunes,
incluyendo ejemplos de código en Go que proporcionan una guía práctica para implementar las recomendaciones.
Go-SCP cubre la [Guía de Referencia Rápida de Prácticas de Codificación Segura][scp-qrf] de OWASP tema por tema:

* Validación de Entrada
* Sanitización y Codificación de Salida
* Autenticación y Gestión de Contraseñas
* Gestión de Sesiones
* Control de Acceso
* Prácticas Criptográficas
* Manejo de Errores y Registro
* Protección de Datos
* Seguridad en las Comunicaciones
* Configuración del Sistema
* Seguridad de Bases de Datos
* Gestión de Archivos
* Gestión de Memoria
* Prácticas Generales de Codificación

El libro [Prácticas de Codificación Segura en Go][go-scp-project] está disponible en varios formatos:

* PDF
* ePub
* DocX
* MOBI

#### ¿Por qué usar Go-SCP?

Los equipos de desarrollo a menudo necesitan ayuda y soporte para implementar correctamente
la seguridad en aplicaciones web, y parte de esta ayuda proviene de directrices y mejores prácticas de codificación segura.
Go-SCP proporciona esta orientación para una amplia gama de temas de codificación segura,
además de proporcionar ejemplos prácticos de código para cada práctica de codificación.

#### Cómo usar Go-SCP

La audiencia principal de la Guía de Prácticas de Codificación Segura en Go son los desarrolladores,
particularmente aquellos con experiencia previa en otros lenguajes de programación.

Descargue el [documento Go-SCP][go-scp-download] en uno de los formatos: PDF, ePub, DocX y MOBI.
Consulte el capítulo específico del tema y luego utilice los fragmentos de código de ejemplo en Go
para obtener una guía práctica sobre codificación segura usando Go.

----

Traducción de versión [original en inglés][en070102].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse
entonces [cree un issue][issue070102] o [edítelo en GitHub][edit070102].

[edit070102]: https://github.com/OWASP/DevGuide/blob/main/docs/es/05-implementation/01-documentation/02-go-scp.md
[en070102]: https://devguide.owasp.org/en/05-implementation/01-documentation/02-go-scp/
[go-scp-download]: https://github.com/OWASP/Go-SCP/tree/master/dist
[go-scp-project]: https://owasp.org/www-project-go-secure-coding-practices-guide/
[issue070102]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2005-implementation/01-documentation/02-go-scp
[scp-qrf]: https://owasp.org/www-project-secure-coding-practices-quick-reference-guide/
