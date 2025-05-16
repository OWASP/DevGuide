![Logo de ESAPI](../../../assets/images/logos/esapi.png "OWASP ESAPI"){ align=right width=180 }

La librería OWASP Enterprise Security API (ESAPI) [library][esapi-docs] es una librería de controles de seguridad
para aplicaciones web escritas en Java.

La [librería ESAPI][esapi-project] es un proyecto de Laboratorio OWASP que se encuentra en desarrollo activo
para [controles de seguridad de Java][esapi-java] con lanzamientos regulares.

#### ¿Qué es la librería ESAPI?

La [librería][esapi-docs] OWASP Enterprise Security API (ESAPI) proporciona un conjunto de interfaces de control
de seguridad que definen los tipos de parámetros que se pasan a los controles de seguridad.

ESAPI es una librería de controles de seguridad para aplicaciones web de código abierto que facilita
a los programadores de Java escribir aplicaciones con menor riesgo.
La librería Java de ESAPI está diseñada para ayudar a los programadores
a incorporar seguridad sobre aplicaciones Java existentes,
y la librería también sirve como una base sólida para nuevos desarrollos.

#### ¿Por qué usarla?

El uso de la librería Java ESAPI no es fácil de justificar, aunque su uso ciertamente debe ser considerado.
Las decisiones de ingeniería que un equipo de desarrollo necesitará tomar al usar ESAPI se discuten
en el documento '[¿Debería usar ESAPI?][esapi-question]'.

Para proyectos nuevos o para modificar un proyecto existente, se deberían considerar seriamente las alternativas:

* Codificación de salida: Proyecto OWASP [Java Encoder][java-encoder]
* Sanitización general de HTML: OWASP [Java HTML Sanitizer][java-sanitizer]
* Validación: [JSR-303/JSR-349 Bean Validation][bean]
* Criptografía fuerte: Google [Tink][google-tink] o [Keyczar][google-keyczar]
* Autenticación y autorización: [Apache Shiro][shiro], autenticación usando [Spring Security][spring]
* Protección [CSRF][cscsrf]: Proyecto OWASP [CSRFGuard][csrfguard]

Se podría considerar el uso de ESAPI si múltiples controles de seguridad proporcionados por esta librería se utilizan
en un proyecto; entonces podría ser útil usar la librería monolítica ESAPI
en lugar de múltiples librerías de clases dispares.

#### Cómo usarla

Si la decisión de ingeniería es usar la librería ESAPI,
entonces puede descargarse como un archivo de paquete Java Archive (.jar).
Hay una implementación de referencia para cada control de seguridad.

#### Referencias

* [ESAPI para Java][esapi-java]
* [Documentación][esapi-docs] de ESAPI
* [Proyecto][esapi-project] ESAPI
* Proyecto [Java Encoder][java-encoder] de OWASP
* [Java HTML Sanitizer][java-sanitizer]
* [Spring Security][spring]

----

Traducción de versión [original en inglés][en070301].

La Guía para Desarrolladores de OWASP es un esfuerzo comunitario;
si hay algo que necesita cambiarse, [cree un issue][issue070301] o [edítelo en GitHub][edit070301].

[bean]: http://beanvalidation.org/
[csrfguard]: https://owasp.org/www-project-csrfguard/
[cscsrf]: https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet
[edit070301]: https://github.com/OWASP/DevGuide/blob/main/docs/es/05-implementation/03-secure-libraries/01-esapi.md
[esapi-docs]: https://www.javadoc.io/doc/org.owasp.esapi/esapi/latest/index.html
[esapi-java]: https://mvnrepository.com/artifact/org.owasp.esapi/esapi
[esapi-project]: https://owasp.org/www-project-enterprise-security-api/
[esapi-question]: https://owasp.org/www-project-enterprise-security-api/#div-shouldiuseesapi
[google-keyczar]: https://github.com/google/keyczar
[google-tink]: https://github.com/google/tink
[en070301]: https://devguide.owasp.org/en/07-implementation/03-secure-libraries/01-esapi/
[issue070301]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2005-implementation/03-secure-libraries/01-esapi
[java-encoder]: https://owasp.org/www-project-java-encoder
[java-sanitizer]: https://owasp.org/www-project-java-html-sanitizer
[shiro]: https://shiro.apache.org/
[spring]: https://docs.spring.io/spring-security/reference/features/index.html
