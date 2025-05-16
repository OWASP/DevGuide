La [autenticación][csauthn] es el proceso de verificar que un individuo o entidad es quien dice ser.
La gestión de sesiones es un proceso mediante el cual un servidor mantiene el estado de la autenticación de los usuarios
para que el usuario pueda continuar utilizando el sistema sin tener que volver a autenticarse.

Consulte el control proactivo [C7: Implementar Identidad Digital][control7] y sus [hojas de referencia][csproactive-c6]
para obtener más contexto del proyecto OWASP Top 10 Controles Proactivos,
y utilice la lista a continuación como sugerencias para una lista de verificación adaptada para el proyecto individual.

#### 1. Autenticación

1. Diseñar a fondo la autenticación del control de acceso desde el principio
2. Forzar que todas las solicitudes pasen por controles de acceso a menos que sean públicas
3. No codificar de forma fija (hard code) controles de acceso basados en roles
4. Registrar todos los eventos de control de acceso
5. Utilizar [Autenticación Multi-Factor][csmfa] (MFA) para cuentas transaccionales sensibles o de alto valor

#### 2. Contraseñas

1. Requerir autenticación para todas las páginas y recursos, excepto aquellos específicamente destinados a ser públicos
2. Todos los controles de autenticación deben aplicarse en un sistema confiable
3. Establecer y utilizar servicios de autenticación estándar y probados siempre que sea posible
4. Utilizar una implementación centralizada para todos los controles de autenticación
5. Segregar la lógica de autenticación del recurso solicitado y
    utilizar redirección hacia y desde el control de autenticación centralizado
6. Todos los controles de autenticación deben fallar de manera segura
7. La administración y gestión de cuentas debe ser al menos tan segura como el mecanismo de autenticación principal
8. Si su aplicación gestiona un almacén de credenciales, utilice hashes unidireccionales criptográficamente
    fuertes con un salt
9. El hash de contraseñas debe implementarse en un sistema confiable
10. Validar los datos de autenticación solo al completar toda la entrada de datos
11. Las respuestas de fallo de autenticación no deben indicar qué parte de los datos de autenticación fue incorrecta
12. Utilizar autenticación para conexiones a sistemas externos que involucren información o funciones confidenciales
13. Las credenciales de autenticación para acceder a servicios externos a la aplicación deben almacenarse
    en un almacén seguro
14. Utilizar solo solicitudes HTTP POST para transmitir credenciales de autenticación
15. Enviar  contraseñas no temporales solo a través de una conexión cifrada o como datos cifrados
16. Aplicar requisitos de complejidad y longitud de contraseña establecidos por políticas o regulaciones
17. Aplicar la desactivación de cuentas después de un número establecido de intentos de inicio de sesión no válidos
18. Las operaciones de restablecimiento y cambio de contraseña requieren el mismo nivel de controles
    que la creación de cuentas y la autenticación
19. Las preguntas de restablecimiento de contraseña están en desuso,
    consulte [Hoja de Referencia sobre Elegir y Usar Preguntas de Seguridad][csquestions] para saber por qué
20. Si utiliza restablecimientos basados en correo electrónico, envíe correo electrónico solo
    a una dirección preregistrada con un enlace/contraseña temporal
21. Las contraseñas y enlaces temporales deben tener un tiempo de caducidad corto
22. Aplicar el cambio de contraseñas temporales en el próximo uso
23. Notificar a los usuarios cuando ocurre un restablecimiento de contraseña
24. Prevenir la reutilización de contraseñas
25. El último uso (exitoso o no exitoso) de una cuenta de usuario debe informarse al usuario
    en su próximo inicio de sesión exitoso
26. Cambiar todas las contraseñas e ID de usuario predeterminados proporcionados
    por el proveedor o deshabilitar las cuentas asociadas
27. Volver a autenticar a los usuarios antes de realizar operaciones críticas
28. Si utiliza código de terceros para la autenticación, inspeccione el código cuidadosamente
    para asegurarse de que no esté afectado por ningún código malicioso

#### 3. Autenticación basada en criptografía

1. Utilizar los controles de gestión de sesiones del servidor o del framework
2. La creación de identificadores de sesión siempre debe realizarse en un sistema confiable
3. Los controles de gestión de sesiones deben utilizar algoritmos cuidadosamente probados que
    garanticen identificadores de sesión suficientemente aleatorios
4. Establecer el dominio y la ruta para las cookies que contienen identificadores de sesión autenticados
    a un valor apropiadamente restringido para el sitio
5. La funcionalidad de cierre de sesión debe terminar completamente la sesión o conexión asociada
6. La funcionalidad de cierre de sesión debe estar disponible en todas las páginas protegidas por autorización
7. Establecer un tiempo de espera de inactividad de sesión que sea lo más corto posible,
    basado en equilibrar el riesgo y los requisitos funcionales del negocio
8. No permitir inicios de sesión persistentes y aplicar terminaciones periódicas de sesión,
    incluso cuando la sesión está activa
9. Si se estableció una sesión antes del inicio de sesión, cierre esa sesión
    y establezca una nueva después de un inicio de sesión exitoso
10. Genere un nuevo identificador de sesión en cualquier reautenticación
11. No permitir inicios de sesión concurrentes con el mismo ID de usuario
12. No exponer identificadores de sesión en URLs, mensajes de error o registros
13. Implementar controles de acceso apropiados para proteger los datos de sesión del lado del servidor
    de acceso no autorizado por parte de otros usuarios del servidor
14. Generar periódicamente un nuevo identificador de sesión y desactivar el antiguo
15. Generar un nuevo identificador de sesión si la seguridad de la conexión cambia de HTTP a HTTPS,
    como puede ocurrir durante la autenticación
16. Establecer el atributo `secure` para las cookies transmitidas a través de una conexión [TLS][tls]
17. Establecer cookies con el atributo `HttpOnly`,
    a menos que específicamente requiera scripts del lado del cliente dentro de su aplicación
    para leer o establecer un valor de cookie

#### Referencias

* [Hoja de Referencia: Autenticación][csauthn] de OWASP
* [Hoja de Referencia: Autenticación][csauthn] de OWASP
* [Hoja de Referencia: Elegir y Usar Preguntas de Seguridad][csquestions] de OWASP
* [Hoja de Referencia: Contraseña Olvidada][csforgot] de OWASP
* [Hoja de Referencia: Autenticación Multifactor][csmfa] de OWASP
* [Hoja de Referencia: Almacenamiento de Contraseñas][cspass] de OWASP
* [Hoja de Referencia: Gestión de Sesiones][cssession] de OWASP
* [Top 10 Controles Proactivos][proactive10] de OWASP

----

Traducción de versión [original en inglés][en060206].

La Guía para Desarrolladores OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse,
[cree un issue][issue060206] o [edítelo en GitHub][edit060206].

[csproactive-c6]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c6-implement-digital-identity
[control7]: https://top10proactive.owasp.org/the-top-10/c7-secure-digital-identities/
[csauthn]: https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet
[csmfa]: https://cheatsheetseries.owasp.org/cheatsheets/Multifactor_Authentication_Cheat_Sheet
[cspass]: https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet
[csforgot]: https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet
[cssession]: https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet
[csquestions]: https://cheatsheetseries.owasp.org/cheatsheets/Choosing_and_Using_Security_Questions_Cheat_Sheet
[edit060206]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/02-web-app-checklist/06-digital-identity.md
[en060206]: https://devguide.owasp.org/en/04-design/02-web-app-checklist/06-digital-identity/
[issue060206]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/06-digital-identity
[proactive10]: https://top10proactive.owasp.org
[tls]: https://cheatsheetseries.owasp.org/cheatsheets/Transport_Layer_Security_Cheat_Sheet
