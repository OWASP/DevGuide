Las pruebas dinámicas de seguridad de aplicaciones (DAST) representan un proceso de prueba no funcional
para identificar debilidades de seguridad y vulnerabilidades en aplicaciones.
El proceso de prueba puede realizarse manualmente o automatizarse.
La evaluación manual de una aplicación implica intervención humana para identificar fallos de seguridad
que podrían pasar desapercibidos para una herramienta automatizada.
Normalmente, los errores de lógica de negocio, verificaciones de condiciones de carrera
y ciertas vulnerabilidades de día cero solo pueden identificarse mediante evaluaciones manuales.

### 6.2.1 Herramientas DAST

Las herramientas DAST son programas que se comunican con una aplicación web a través de la interfaz web
para identificar posibles vulnerabilidades de seguridad en la aplicación web y debilidades arquitectónicas.
Realizan pruebas de caja negra. A diferencia de las herramientas de pruebas estáticas de seguridad de aplicaciones,
las herramientas DAST no tienen acceso al código fuente y, por lo tanto,
detectan vulnerabilidades realizando ataques reales.

#### Diferentes herramientas DAST

La Comunidad OWASP contiene una [lista de herramientas DAST][dast] que pueden utilizarse para realizar DAST.
Todas estas herramientas tienen sus propias fortalezas y debilidades.
Si está interesado en la efectividad de las herramientas DAST, consulte el proyecto [OWASP Benchmark][benchmark],
que intenta medir científicamente la efectividad de todos los tipos de herramientas de detección de vulnerabilidades,
incluyendo DAST.

#### ¿Por qué utilizarlas?

La gran ventaja de este tipo de herramientas es que pueden escanear
durante todo el año para buscar constantemente vulnerabilidades.
Con nuevas vulnerabilidades siendo descubiertas regularmente, esto permite a las empresas encontrar
y parchar vulnerabilidades antes de que puedan ser explotadas.

#### Contras

Debido a que estas herramientas realizan pruebas dinámicas, no pueden cubrir el 100% del código fuente de la aplicación y,
por tanto, la aplicación en sí misma.
El evaluador de penetración debe observar la cobertura de la aplicación web o de su superficie de ataque
para saber si la herramienta se configuró correctamente o si fue capaz de entender la aplicación web.

#### Referencias

* [Pruebas dinámicas de seguridad de aplicaciones][wikipedia]
* [Herramientas de Escaneo de Vulnerabilidades][dast]

----

Traducción de versión [original en inglés][en080201].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario;
si hay algo que necesita cambios, [cree un issue][issue080201] o [edítelo en GitHub][edit080201].

[benchmark]: https://owasp.org/www-project-benchmark/
[dast]: https://owasp.org/www-community/Vulnerability_Scanning_Tools
[edit080201]: https://github.com/OWASP/DevGuide/blob/main/docs/es/06-verification/02-tools/01-dast.md
[en080201]: https://devguide.owasp.org/en/06-verification/02-tools/01-dast/
[issue080201]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2006-verification/02-tools/01-dast
[wikipedia]: https://en.wikipedia.org/wiki/Dynamic_application_security_testing
