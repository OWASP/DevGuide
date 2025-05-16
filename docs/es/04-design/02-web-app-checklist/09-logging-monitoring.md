El registro es la grabación de información de seguridad durante la operación en tiempo de ejecución de una aplicación.
El monitoreo es la revisión en vivo de los registros de aplicaciones y seguridad utilizando varias formas de automatización.

Consulte el control proactivo [C9: Implementar Registro y Monitoreo de Seguridad][control9]
y sus [hojas de referencia][csproactive-c9] para obtener más contexto del proyecto OWASP Top 10 Controles Proactivos,
y utilice la lista a continuación como sugerencias para una lista de verificación adaptada para el proyecto individual.

#### 1. Registro de seguridad

1. Registrar datos enviados que estén fuera de un rango numérico esperado.
2. Registrar datos enviados que impliquen cambios en datos que no deberían ser modificables
3. Registrar solicitudes que violen las reglas de control de acceso del lado del servidor
4. Codificar y validar cualquier carácter peligroso antes de registrar para prevenir ataques de inyección en registros
5. No registrar información sensible
6. Los controles de registro deben admitir tanto el éxito como el fracaso de eventos de seguridad especificados
7. No almacenar información sensible en los registros, incluidos detalles innecesarios del sistema,
    identificadores de sesión o contraseñas
8. Utilizar una función hash criptográfica para validar la integridad de las entradas de registro

#### 2. Diseño de registro de seguridad

1. Proteger la integridad del registro
2. Asegurar que las entradas de registro que incluyen datos no confiables no se ejecutarán como código
    en la interfaz o software de visualización de registros previsto
3. Restringir el acceso a los registros solo a individuos autorizados
4. Utilizar una rutina central para todas las operaciones de registro
5. Reenviar registros de sistemas distribuidos a un servicio de registro central y seguro
6. Seguir un formato y enfoque de registro común dentro del sistema y entre sistemas de una organización
7. Sincronizar entre nodos para garantizar que las marcas de tiempo sean consistentes
8. Todos los controles de registro deben implementarse en un sistema confiable
9. Asegurar que exista un mecanismo para realizar análisis de registros

#### Referencias

* [Hoja de Referencia: Registro][cslogging] de OWASP
* [Hoja de Referencia: Vocabulario de Registro de Aplicaciones][csvocabulary] de OWASP
* [Top 10 Controles Proactivos][proactive10] de OWASP

----

Traducción de versión [original en inglés][en060209].

La Guía para Desarrolladores OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse,
[cree un issue][issue060209] o [edítelo en GitHub][edit060209].

[csproactive-c9]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c9-implement-security-logging-and-monitoring
[control9]: https://top10proactive.owasp.org/the-top-10/c9-security-logging-and-monitoring/
[cslogging]: https://cheatsheetseries.owasp.org/cheatsheets/Logging_Cheat_Sheet
[csvocabulary]: https://cheatsheetseries.owasp.org/cheatsheets/Logging_Vocabulary_Cheat_Sheet
[edit060209]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/02-web-app-checklist/09-logging-monitoring.md
[en060209]: https://devguide.owasp.org/en/04-design/02-web-app-checklist/09-logging-monitoring/
[issue060209]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/09-logging-monitoring
[proactive10]: https://top10proactive.owasp.org/
