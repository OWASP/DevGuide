El Control de Acceso o [Autorización][csauthz] es el proceso de conceder o denegar solicitudes específicas
de un usuario, programa o proceso.

Consulte el control proactivo [C1: Implementar Controles de Acceso][control1] y sus [hojas de referencia][csproactive-c7]
para obtener más contexto del proyecto OWASP Top 10 Controles Proactivos,
y utilice la lista a continuación como sugerencias para una lista de verificación adaptada para el proyecto individual.

#### 1. Autorización

1. Diseñar el control de acceso / autorización a fondo desde el principio
2. Forzar que todas las solicitudes pasen por verificaciones de control de acceso a menos que sean públicas
3. Denegar por defecto; si una solicitud no está específicamente permitida, entonces es denegada
4. Aplicar el privilegio mínimo, proporcionando el menor acceso que sea necesario
5. Registrar todos los eventos de autorización

#### 2. Control de acceso

1. Obligar al uso de controles de autorización en cada solicitud
2. Utilizar solo objetos de sistema confiables para tomar decisiones de autorización de acceso
3. Utilizar un único componente para todo el sitio para verificar la autorización de acceso
4. Los controles de acceso deben fallar de manera segura
5. Denegar todo acceso si la aplicación no puede acceder a su información de configuración de seguridad
6. Segregar la lógica privilegiada del resto del código de la aplicación
7. Limitar el número de transacciones que un solo usuario o dispositivo puede realizar en un período de tiempo determinado,
    lo suficientemente bajo para disuadir ataques automatizados pero por encima del requisito real del negocio
8. Si se permiten sesiones autenticadas largas, revalidar periódicamente la autorización de un usuario
9. Implementar auditoría de cuentas y hacer obligatoria la desactivación de cuentas no utilizadas
10. La aplicación debe admitir la terminación de sesiones cuando cese la autorización

#### Referencias

* [Hoja de Referencia: Autorización][csauthz] de OWASP
* [Top 10 Controles Proactivos][proactive10] de OWASP

----

Traducción de versión [original en inglés][en060207].

La Guía para Desarrolladores OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse,
[cree un issue][issue060207] o [edítelo en GitHub][edit060207].

[csproactive-c7]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c7-enforce-access-controls
[control1]: https://top10proactive.owasp.org/the-top-10/c1-accesscontrol/
[csauthz]: https://cheatsheetseries.owasp.org/cheatsheets/Authorization_Cheat_Sheet
[edit060207]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/02-web-app-checklist/07-access-controls.md
[en060207]: https://devguide.owasp.org/en/04-design/02-web-app-checklist/07-access-controls/
[issue060207]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/07-access-controls
[proactive10]: https://top10proactive.owasp.org/
