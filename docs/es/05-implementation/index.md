![Logo de la guía del desarrollador](../../assets/images/dg_logo.png "Guía del Desarrollador"){ align=right width=180 }

## 5. Implementación

La función de negocio [Implementación][sammi] está descrita por
el [Modelo de Madurez de Aseguramiento de Software][sammm] (SAMM) de OWASP.
La Implementación se centra en los procesos y actividades relacionadas con la manera en que una organización
construye y despliega componentes de software y sus defectos relacionados.
Las actividades de Implementación tienen el mayor impacto en la vida diaria de los desarrolladores,
y un objetivo importante de la Implementación es entregar software que funcione de manera confiable
con un mínimo de defectos.

La Implementación debe incluir prácticas de seguridad como:

* Construcción Segura
* Despliegue Seguro
* Gestión de Defectos

La Implementación es donde la aplicación/sistema comienza a tomar forma; se escribe el código fuente y se crean las pruebas.
La implementación de la aplicación sigue un ciclo de vida de desarrollo seguro, con seguridad incorporada desde el inicio.

La implementación utilizará un método seguro de control y almacenamiento del código fuente
para cumplir con los requisitos de seguridad del diseño.
El equipo de desarrollo se referirá a la documentación que aconseja sobre las mejores prácticas,
utilizará bibliotecas seguras siempre que sea posible,
además de verificar y realizar seguimiento de las dependencias externas.

Gran parte de la habilidad de implementación proviene de la experiencia,
y tener en cuenta lo que se debe hacer y lo que no se debe hacer
durante el desarrollo seguro es en sí misma una actividad de conocimiento importante.

----

Traducción de versión [original en inglés][en0700].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario;
si ve algo que necesita cambios, entonces [cree un issue][issue0700] o [edítelo en GitHub][edit0700].

[edit0700]: https://github.com/OWASP/DevGuide/blob/main/docs/es/05-implementation/index.md
[en0700]: https://devguide.owasp.org/en/05-implementation/
[issue0700]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2005-implementation/index
[sammm]: https://owaspsamm.org/model/
[sammi]: https://owaspsamm.org/model/implementation/
