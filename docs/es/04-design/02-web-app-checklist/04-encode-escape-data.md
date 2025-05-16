La codificación y el escapado de datos de salida son técnicas defensivas destinadas a detener ataques de inyección
en un sistema o aplicación objetivo que está recibiendo los datos de salida.

El sistema objetivo puede ser otro componente de software o puede reflejarse de nuevo en el sistema inicial,
como comandos del sistema operativo,
por lo que codificar y escapar datos de salida ayuda a proporcionar defensa en profundidad para el sistema en su conjunto.

Consulte el control proactivo [C3: Validar todas las Entradas y Manejar Excepciones][control3]
y sus [hojas de referencia][csproactive-c4]
para más contexto del proyecto OWASP Top 10 Controles Proactivos,
y use la lista a continuación como sugerencias para una lista de comprobación adaptada al proyecto individual.

#### 1. Codificación de caracteres y canonicalización

1. Aplicar codificación a la salida justo antes de que el contenido sea pasado al sistema objetivo
2. Realizar toda la codificación de salida en un sistema confiable
3. Utilizar una rutina estándar y probada para cada tipo de codificación de salida
4. Especificar conjuntos de caracteres, como UTF-8, para todas las salidas
5. Aplicar canonicalización para convertir datos unicode en una forma estándar
6. Asegurar que la codificación de salida sea segura para todos los sistemas objetivo
7. En particular, desinfectar todas las salidas utilizadas para comandos del sistema operativo

#### 2. Codificación contextual de salida

La codificación contextual de salida de datos se basa en cómo será utilizada por el objetivo.
Los métodos específicos varían dependiendo de la forma en que se utilizan los datos de salida,
como la codificación de entidades HTML.

1. Codificar contextualmente todos los datos devueltos al cliente desde fuentes no confiables
2. Codificar contextualmente toda la salida de datos no confiables en consultas para SQL, XML y LDAP

#### Referencias

* [Hoja de Referencia: Prevención de Inyección][ipcs] de OWASP
* [Proyecto Java Encoder][encoder] de OWASP
* [Top 10 Controles Proactivos][proactive10] de OWASP

----

Traducción de versión [original en inglés][en060204].

La Guía para Desarrolladores de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse
entonces [cree un issue][issue060204] o [edítelo en GitHub][edit060204].

[csproactive-c4]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c4-encode-and-escape-data
[control3]: https://top10proactive.owasp.org/the-top-10/c3-validate-input-and-handle-exceptions/
[edit060204]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/02-web-app-checklist/04-encode-escape-data.md
[encoder]: https://www.owasp.org/index.php/OWASP_Java_Encoder_Project
[ipcs]: https://cheatsheetseries.owasp.org/cheatsheets/Injection_Prevention_Cheat_Sheet
[en060204]: https://devguide.owasp.org/en/04-design/02-web-app-checklist/04-encode-escape-data/
[issue060204]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/04-encode-escape-data
[proactive10]: https://top10proactive.owasp.org/
