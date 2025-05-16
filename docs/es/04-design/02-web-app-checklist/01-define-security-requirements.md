Un requisito de seguridad es una declaración de funcionalidad de seguridad que garantiza
que se está satisfaciendo la seguridad del software.
Los requisitos de seguridad se derivan de estándares de la industria, leyes aplicables
y un historial de vulnerabilidades pasadas.

Consulte el control proactivo [C4: Abordar la Seguridad desde el Principio][control4]
y sus [hojas de referencia][csproactive-c1]
para más contexto del proyecto Top 10 Controles Proactivos de OWASP,
y use las listas a continuación como sugerencias para una lista de verificación adaptada al proyecto individual.

#### 1. Configuración del sistema

1. Restringir aplicaciones, procesos y cuentas de servicio a los mínimos privilegios posibles
2. Si la aplicación debe ejecutarse con privilegios elevados, elevar privilegios lo más tarde posible
    y reducirlos tan pronto como sea posible
3. Eliminar toda funcionalidad y archivos innecesarios
4. Eliminar código de prueba o cualquier funcionalidad no destinada a producción, antes del despliegue
5. El almacén de configuración de seguridad para la aplicación debe estar disponible
    en formato legible para humanos para facilitar las auditorías
6. Aislar los entornos de desarrollo de la producción y proporcionar acceso solo a grupos autorizados de desarrollo y prueba
7. Implementar un sistema de control de cambios de software para gestionar
    y registrar cambios en el código tanto en desarrollo como en producción

#### 2. Prácticas criptográficas

1. Utilizar módulos criptográficos de código abierto y revisados por pares
2. Todas las funciones criptográficas utilizadas para proteger secretos del usuario
    de la aplicación deben implementarse en un sistema confiable
3. Los módulos criptográficos deben fallar de manera segura
4. Asegurarse de que todos los elementos aleatorios como números, nombres de archivo,
    UUID(identificador único universal) y cadenas se generan
    utilizando el generador de números aleatorios aprobado del módulo criptográfico
5. Los módulos criptográficos utilizados por la aplicación cumplen con FIPS 140-2 o un estándar equivalente
6. Establecer y utilizar una política y proceso para la gestión de claves criptográficas
7. Asegurar que cualquier clave secreta esté protegida contra acceso no autorizado
8. Almacenar claves en una bóveda de secretos adecuada como se describe a continuación
9. Utilizar claves independientes cuando se requieren múltiples claves
10. Crear soporte para cambiar algoritmos y claves cuando sea necesario
11. Construir características de la aplicación para manejar una rotación de claves

#### 3. Gestión de archivos

1. No pasar datos suministrados por el usuario directamente a ninguna función de inclusión dinámica
2. Requerir autenticación antes de permitir la carga de un archivo
3. Limitar el tipo de archivos que se pueden cargar solo a aquellos tipos que son necesarios para fines del negocio
4. Validar que los archivos cargados son del tipo esperado comprobando las cabeceras de archivo en lugar de la extensión
5. No guardar archivos en el mismo contexto web de la aplicación
6. Prevenir o restringir la carga de cualquier archivo que pueda ser interpretado por el servidor web
7. Desactivar los privilegios de ejecución en los directorios de carga de archivos
8. Al hacer referencia a archivos existentes, utilizar una lista blanca de nombres y tipos de archivos permitidos
9. No pasar datos suministrados por el usuario a una redirección dinámica
10. No pasar rutas de directorio o archivo, utilizar valores de índice mapeados a una lista predefinida de rutas
11. Nunca enviar la ruta absoluta del archivo al cliente
12. Asegurar que los archivos y recursos de la aplicación sean de solo lectura
13. Escanear los archivos cargados por usuarios en busca de virus y malware

#### Referencias

* [Estándar de Verificación de Seguridad de Aplicaciones][asvs] (ASVS) de OWASP
* [Seguridad de Aplicaciones Móviles][mas] de OWASP
* [Top 10 Controles Proactivos][proactive10] de OWASP

----

Traducción de versión [original en inglés][en060201].

La Guía para Desarrolladores de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse
entonces [cree un issue][issue060201] o [edítelo en GitHub][edit060201].

[asvs]: https://owasp.org/www-project-application-security-verification-standard/
[csproactive-c1]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c1-define-security-requirements
[control4]: https://top10proactive.owasp.org/the-top-10/c4-secure-architecture/
[edit060201]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/02-web-app-checklist/01-define-security-requirements.md
[en060201]: https://devguide.owasp.org/en/04-design/02-web-app-checklist/01-define-security-requirements/
[issue060201]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/01-define-security-requirements
[mas]: https://mas.owasp.org/
[proactive10]: https://top10proactive.owasp.org/
