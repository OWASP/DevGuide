Refiriéndose a la [Hoja de Referencia de Diseño de Producto Seguro][spdcs],
el propósito de la arquitectura y diseño seguros es garantizar
que todos los productos cumplan o excedan los requisitos de seguridad establecidos por la organización,
centrándose en la seguridad vinculada a los componentes y tecnologías utilizados durante el desarrollo de la aplicación.

El Diseño de Arquitectura Segura examina la selección y composición de componentes que forman la base de la solución.
La Gestión de Tecnología examina la seguridad de las tecnologías de apoyo utilizadas durante el desarrollo,
despliegue y operaciones, como el stack de tecnología de desarrollo y sus herramientas, herramientas de despliegue,
y sistemas operativos y sus herramientas.

Un diseño seguro ayudará a establecer valores predeterminados seguros, minimizar el área de superficie de ataque
y fallar de manera segura hacia valores predeterminados bien definidos y comprendidos.
También considerará y seguirá varios principios, como:

* Privilegio Mínimo y Separación de Deberes
* Defensa en Profundidad
* Confianza Cero
* Seguridad en lo Abierto

Un Ciclo de Vida de Desarrollo Seguro (SDLC) ayuda a asegurar que todas las decisiones de seguridad tomadas
sobre el producto en desarrollo sean elecciones explícitas y resulten en el nivel correcto de seguridad
para el diseño del producto.
Se pueden utilizar varios ciclos de vida de desarrollo seguro y generalmente incluyen el modelado de amenazas
en el proceso de diseño.

Las listas de verificación y las Hojas de Referencia son herramientas importantes durante el proceso de diseño;
proporcionan una referencia fácil de conocimiento y ayudan a evitar la repetición de errores y fallos de diseño.

El [Diseño][sammd] de aplicaciones de software es una de las principales funciones de negocio descritas en
el [Modelo de Madurez de Aseguramiento de Software (SAMM)][samm], e incluye prácticas de seguridad:

* [Evaluación de Amenazas][sammdta]
* [Requisitos de Seguridad][sammdsr]
* [Arquitectura de Seguridad][sammdsa]

----

Traducción de versión [original en inglés][en0600].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario;
si ve algo que necesita cambios, entonces [cree un issue][issue0600] o [edítelo en GitHub][edit0600].

[edit0600]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/index.md
[en0600]: https://devguide.owasp.org/en/04-design/
[issue0600]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2004-design/index
[samm]: https://owaspsamm.org/about/
[sammd]: https://owaspsamm.org/model/design/
[sammdsa]: https://owaspsamm.org/model/design/secure-architecture/
[sammdsr]: https://owaspsamm.org/model/design/security-requirements/
[sammdta]: https://owaspsamm.org/model/design/threat-assessment/
[spdcs]: https://cheatsheetseries.owasp.org/cheatsheets/Secure_Product_Design_Cheat_Sheet
