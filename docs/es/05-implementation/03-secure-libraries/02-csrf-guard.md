OWASP [CSRFGuard][csrfguard] es un control de seguridad que ayuda a proteger las aplicaciones Java
contra ataques de [Falsificación de Petición en Sitios Cruzados][cscsrf] (CSRF).

El proyecto CSRFGuard Builder/Breaker Tool es un Proyecto de Producción OWASP
y está siendo mantenido activamente por un grupo de voluntarios internacionales.

#### ¿Qué es CSRFGuard?

OWASP [CSRFGuard][csrfguard] es una librería que implementa una variante del patrón de token sincronizador
para mitigar el riesgo de ataques de Falsificación de Petición en Sitios Cruzados (CSRF) para aplicaciones Java.

La librería OWASP CSRFGuard se integra mediante el uso de un Filtro JavaEE y expone varias formas automatizadas
y manuales para integrar tokens por sesión o pseudo-por-petición en HTML. Cuando un usuario interactúa con este HTML,
los tokens de prevención CSRF se envían con la petición HTTP correspondiente.
CSRFGuard asegura que el token esté presente y sea válido para la petición HTTP actual.

#### ¿Por qué usarlo?

La librería OWASP CSRFGuard es ampliamente utilizada para aplicaciones Java, y ayudará a mitigar contra CSRF.

#### Cómo usarlo

Las versiones precompiladas de la biblioteca CSRFGuard pueden descargarse
desde el [repositorio Maven Central][csrfguard-maven] o el repositorio [OSS Sonatype Nexus][csrfguard-nexus].

Sigue las [instrucciones][csrfguard-build] para integrar CSRFGuard en la aplicación Java utilizando Maven.

#### Referencias

* [CSRFGuard][csrfguard] de OWASP
* [Hoja de Referencia para Prevención de Falsificación de Petición en Sitios Cruzados][cscsrf] de OWASP

----

Traducción de versión [original en inglés][en070302].

La Guía para Desarrolladores de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse,
[cree un issue][issue070302] o [edítelo en GitHub][edit070302].

[csrfguard]: https://owasp.org/www-project-csrfguard/
[csrfguard-build]: https://github.com/OWASP/www-project-csrfguard/blob/master/readme.md#using-with-maven
[csrfguard-nexus]: https://oss.sonatype.org/#nexus-search;gav~~csrfguard~~~
[csrfguard-maven]: https://central.sonatype.com/search?q=csrfguard&smo=true
[cscsrf]: https://cheatsheetseries.owasp.org/cheatsheets/Cross-Site_Request_Forgery_Prevention_Cheat_Sheet
[edit070302]: https://github.com/OWASP/DevGuide/blob/main/docs/es/05-implementation/03-secure-libraries/02-csrf-guard.md
[en070302]: https://devguide.owasp.org/en/05-implementation/03-secure-libraries/02-csrf-guard/
[issue070302]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2005-implementation/03-secure-libraries/02-csrf-guard
