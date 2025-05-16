Manejar [excepciones y errores][cserror] correctamente es crítico para hacer que su código sea confiable y seguro.
El manejo de errores y excepciones ocurre en todas las áreas de una aplicación, incluyendo la lógica crítica del negocio
así como las características de seguridad y el código del framework.

Consulte el control proactivo [C3: Validar todas las Entradas y Manejar Excepciones][control3]
y sus [hojas de referencia][csproactive-c10] para obtener más contexto del proyecto OWASP Top 10 Controles Proactivos,
y utilice la lista a continuación como sugerencias para una lista de verificación adaptada para el proyecto individual.

#### 1. Errores y excepciones

1. Gestionar las excepciones de manera centralizada para evitar bloques try/catch duplicados en el código
2. Asegurar que todo comportamiento inesperado se maneje correctamente dentro de la aplicación
3. Asegurar que los mensajes de error mostrados a los usuarios no filtren datos críticos,
    pero que sean lo suficientemente detallados para permitir la respuesta adecuada del usuario
4. Asegurar que los registros de excepciones proporcionen información suficiente para los equipos de soporte,
    control de calidad, forense o respuesta a incidentes
5. Probar y verificar cuidadosamente el código de manejo de errores
6. No revelar información sensible en las respuestas de error, por ejemplo
    detalles del sistema, identificadores de sesión o información de la cuenta
7. Utilizar manejadores de errores que no muestren información de depuración o de seguimiento de pila
8. Implementar mensajes de error genéricos y utilizar páginas de error personalizadas
9. La aplicación debe manejar los errores de la aplicación y no depender de la configuración del servidor
10. Liberar adecuadamente la memoria asignada cuando ocurran condiciones de error
11. La lógica de manejo de errores asociada con los controles de seguridad debe denegar el acceso por defecto

#### Referencias

* [Guía de Revisión de Código: Manejo de Errores][review] de OWASP
* [Manejo Inadecuado de Errores][handle]  de OWASP
* [Top 10 Controles Proactivos][proactive10]  de OWASP

----

Traducción de versión [original en inglés][en060210].

La Guía para Desarrolladores OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse,
[cree un issue][issue060210] o [edítelo en GitHub][edit060210].

[cserror]: https://cheatsheetseries.owasp.org/cheatsheets/Error_Handling_Cheat_Sheet
[csproactive-c10]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c10-handle-all-errors-and-exceptions
[control3]: https://top10proactive.owasp.org/the-top-10/c3-validate-input-and-handle-exceptions/
[edit060210]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/02-web-app-checklist/10-handle-errors-exceptions.md
[handle]: https://owasp.org/www-community/Improper_Error_Handling
[en060210]: https://devguide.owasp.org/en/04-design/02-web-app-checklist/10-handle-errors-exceptions/
[issue060210]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/10-handle-errors-exceptions
[proactive10]: https://top10proactive.owasp.org/
[review]: https://owasp.org/www-project-code-review-guide/
