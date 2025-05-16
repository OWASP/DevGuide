Asegure que el acceso a todos los almacenes de datos sea seguro,
incluyendo tanto bases de datos relacionales como bases de datos NoSQL.

Consulte el control proactivo [C3: Validar todas las Entradas y Manejar Excepciones][control3]
y sus [hojas de referencia][csproactive-c3]
para más contexto sobre el proyecto Top 10 Controles Proactivos de OWASP,
y use la lista a continuación como sugerencias para una lista de comprobación adaptada al proyecto individual.

#### 1. Consultas seguras

1. Utilizar Parametrización de Consultas para evitar que entradas no confiables sean interpretadas
    como parte de un comando SQL
2. Utilizar consultas parametrizadas fuertemente tipadas
3. Utilizar validación de entrada y codificación de salida, asegurándose de encargarse de los meta caracteres
4. No ejecutar el comando de base de datos si la validación de entrada falla
5. Asegurar que las variables estén fuertemente tipadas
6. Las cadenas de conexión no deben estar codificadas de forma fija dentro de la aplicación
7. Las cadenas de conexión deben almacenarse en un archivo de configuración separado en un sistema confiable
    y deben estar cifradas

#### 2. Configuración segura

1. La aplicación debe usar el nivel más bajo posible de privilegios al acceder a la base de datos
2. Utilizar procedimientos almacenados para abstraer el acceso a datos y permitir la eliminación de permisos
    a las tablas base en la base de datos
3. Cerrar la conexión de la base de datos tan pronto como sea posible
4. Desactivar toda funcionalidad innecesaria de la base de datos
5. Eliminar contenido predeterminado innecesario del proveedor, por ejemplo esquemas de muestra
6. Deshabilitar cualquier cuenta predeterminada que no sea necesaria para soportar los requisitos del negocio

#### 3. Autenticación segura

1. Eliminar o cambiar todas las contraseñas administrativas predeterminadas de la base de datos
2. La aplicación debe conectarse a la base de datos con credenciales diferentes para cada nivel de confianza
    (por ejemplo, usuario, usuario de solo lectura, invitado, administradores)
3. Utilizar credenciales seguras para el acceso a la base de datos

#### Referencias

* [Hoja de Referencia: Parametrización de Consultas][csquery] de OWASP
* [Hoja de Referencia: Seguridad de Bases de Datos][csdb]de OWASP
* [Top 10 Controles Proactivos][proactive10] de OWASP

----

Traducción de versión [original en inglés][en060203].

La Guía para Desarrolladores de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse
entonces [cree un issue][issue060203] o [edítelo en GitHub][edit060203].

[csproactive-c3]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c3-secure-database-access
[control3]: https://top10proactive.owasp.org/the-top-10/c3-validate-input-and-handle-exceptions/
[csdb]: https://cheatsheetseries.owasp.org/cheatsheets/Database_Security_Cheat_Sheet
[csquery]: https://cheatsheetseries.owasp.org/cheatsheets/Query_Parameterization_Cheat_Sheet
[edit060203]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/02-web-app-checklist/03-secure-database-access.md
[en060203]: https://devguide.owasp.org/en/04-design/02-web-app-checklist/03-secure-database-access/
[issue060203]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/03-secure-database-access
[proactive10]: https://top10proactive.owasp.org/

\newpage
