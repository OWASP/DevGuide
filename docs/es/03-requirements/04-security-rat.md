La Herramienta de Automatización de Requisitos[SecurityRAT][srat] de OWASP se utiliza
para generar y gestionar requisitos de seguridad
usando información del proyecto [OWASP ASVS][asvs].
También proporciona un enfoque automatizado para la gestión de requisitos
durante el desarrollo de aplicaciones frontend, de servidor y móviles.

En la actualidad es un proyecto de Incubadora de OWASP, pero es probable que pronto se actualice al estado de Laboratorio.

#### ¿Qué es SecurityRAT?

SecurityRAT es una herramienta complementaria para el conjunto de requisitos de [ASVS][asvs];
puede usarse para generar un conjunto inicial de requisitos a partir de ASVS
y luego hacer un seguimiento del estado y las actualizaciones de estos requisitos.
Viene con [documentación e instrucciones][sratdocs] sobre cómo instalar y ejecutar SecurityRAT.

Para generar la lista inicial de requisitos, SecurityRAT necesita que se le proporcionen tres atributos definidos por ASVS:

* ID del capítulo del Estándar de Verificación de Seguridad de Aplicaciones - por ejemplo 'V2 - Autenticación'
* Nivel de Verificación de Seguridad de Aplicaciones - el nivel de cumplimiento, por ejemplo 'L2'
* Autenticación - si se utiliza autenticación de inicio de sesión único (SSO) o no

SecurityRAT genera entonces una lista inicial de requisitos recomendados.
Esta lista puede almacenarse en una base de datos de SecurityRAT que permite el seguimiento y actualización
del conjunto de requisitos.
SecurityRAT también proporciona integración con JIRA de Atlassian para la creación y seguimiento de problemas de software.

La serie Spotlight de OWASP proporciona una visión general de lo que puede hacer SecurityRAT y cómo usarlo:
'Proyecto 5 - [OWASP SecurityRAT][spotlight05]'.

#### ¿Por qué usarlo?

En el momento de su redacción, ASVS tiene más de 280 requisitos sugeridos para el desarrollo de software seguro.
Este número de requisitos lleva tiempo para clasificarlos y determinar si
son aplicables o no a un proyecto de desarrollo determinado.

El uso de SecurityRAT para crear un subconjunto más manejable de los requisitos de ASVS es un beneficio directo tanto para
arquitectos de seguridad como para el equipo de desarrollo.
Además, SecurityRAT permite el seguimiento y actualización de este conjunto de requisitos
durante todo el ciclo de desarrollo,
añadiendo seguridad a la aplicación al ayudar a garantizar que se cumplan los requisitos de seguridad.

#### Cómo usar SecurityRAT

Instale las aplicaciones de SecurityRAT de Producción y Desarrollo descargando una versión e instalándola
en el Kit de Desarrollo Java JDK11.
Alternativamente, descargue y ejecute la [imagen Docker][sratdocker] desde DockerHub.
Configure SecurityRAT consultando la [documentación de implementación][sratdeploy]; esto no es muy sencillo,
por lo que para comenzar hay una [demostración en línea][sratdemo] disponible.

Al iniciar sesión en el sitio de demostración, usando las credenciales de la [página del proyecto][srat],
se muestra la definición de un conjunto de requisitos o la importación de un conjunto existente.
Suponiendo que queremos un nuevo conjunto de requisitos, asigne un nombre al artefacto de requisitos y luego
seleccione secciones/capítulos específicos de ASVS de la lista:

* V1 - Arquitectura, Diseño y Modelado de Amenazas
* V2 - Autenticación
* V3 - Gestión de Sesiones
* V4 - Control de Acceso
* V5 - Validación, Sanitización y Codificación
* V6 - Criptografía Almacenada
* V7 - Manejo de Errores y Registro
* V8 - Protección de Datos
* V9 - Comunicación
* V10 - Código Malicioso
* V11 - Lógica de Negocio
* V12 - Archivos y Recursos
* V13 - API y Servicio Web
* V14 - Configuración

o déjelo en blanco para incluir todos los requisitos de verificación.

Seleccione el nivel usando los niveles de cumplimiento de seguridad definidos por ASVS:

* Nivel 1 es para niveles de garantía bajos y completamente verificables mediante pruebas de penetración
* Nivel 2 es para aplicaciones que contienen datos sensibles y es el nivel recomendado para la mayoría de las aplicaciones
* Nivel 3 es para las aplicaciones más críticas

Finalmente, seleccione si se está utilizando autenticación SSO y genere una lista de requisitos.
Este artefacto de requisitos se almacena ahora en SecurityRAT y puede recuperarse en sesiones posteriores.

SecurityRAT presenta entonces una pantalla de administración que permite el seguimiento
y edición de los requisitos de verificación de ASVS.
Consulte el [Spotlight de OWASP sobre SecurityRAT][spotlight05] para obtener una explicación
de cómo integrarlo con JIRA de Atlassian.

#### ¿Qué es SecurityCAT?

[SecurityCAT][scat] (Herramienta de Automatización de Cumplimiento) es una extensión
de SecurityRAT destinada a la prueba automática de requisitos.
No existe una implementación real de SecurityCAT,
SecurityRAT proporciona una API que permite crear una herramienta de cumplimiento,
por lo que este puede ser un desarrollo futuro de SecurityRAT.

#### Referencias

* [SecurityRAT][srat] de OWASP
* [Documentación][sratdocs] de SecurityRAT de OWASP
* [SecurityCAT][scat] de OWASP
* [Estándar de Verificación de Seguridad de Aplicaciones][asvs] (ASVS) de OWASP

----

Traducción de versión [original en inglés][en0504].

La Guía de Desarrollador OWASP es un esfuerzo comunitario; si hay algo que necesite cambios
entonces [cree un issue][issue0504] o [edítelo en GitHub][edit0504].

[asvs]: https://owasp.org/www-project-application-security-verification-standard/
[edit0504]: https://github.com/OWASP/DevGuide/blob/main/docs/es/03-requirements/04-security-rat.md
[en0504]: https://devguide.owasp.org/en/03-requirements/04-security-rat/
[issue0504]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2003-requirements/04-security-rat
[spotlight05]: https://youtu.be/HiaHXtzJ3DE
[scat]: https://securityrat.github.io/int_securitycat.html#securitycat
[srat]: https://owasp.org/www-project-securityrat/
[sratdemo]: https://securityrat.org/
[sratdeploy]: https://securityrat.github.io/depl_production.html
[sratdocker]: https://hub.docker.com/r/securityrat/securityrat
[sratdocs]: https://securityrat.github.io/
