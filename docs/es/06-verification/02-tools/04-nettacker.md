![Logo de Nettacker](../../../assets/images/logos/nettacker.png "Nettacker de OWASP"){ align=right width=180 }

### 6.2.4 Nettacker

OWASP Nettacker es una utilidad de línea de comandos para escaneo automatizado de redes y vulnerabilidades.
Puede utilizarse durante pruebas de penetración tanto para evaluaciones de seguridad internas como externas de redes.

El [proyecto atacante/herramienta][nettacker-project] Nettacker es un Proyecto Incubadora de OWASP;
la última versión puede descargarse desde el [repositorio github][nettacker-install] del proyecto.

#### ¿Qué es Nettacker?

[Nettacker][nettacker-project] es una herramienta automatizada de pruebas de penetración.
Se utiliza para escanear una red para descubrir nodos y servidores en la red, incluyendo subdominios.
Nettacker puede luego identificar servidores, servicios y números de puerto en uso.

Nettacker es una aplicación modular en Python que puede extenderse con otras funciones de escaneo.
Los numerosos módulos disponibles están agrupados en dominios:

* Módulos de [escaneo][nettacker-scan] para reconocimiento
* Módulos de [vulnerabilidad][nettacker-vuln] que intentan exploits específicos
* Módulos de [fuerza bruta][nettacker-brute]

Nettacker se ejecuta en Windows, Linux y MacOS.

#### ¿Por qué utilizarla?

Nettacker es fácil de usar desde la línea de comandos, lo que facilita su uso en scripts,
y también viene con una interfaz de navegador web para una fácil navegación de los resultados.
Esto lo convierte en una forma rápida y confiable de obtener información de una red.

Nettacker puede utilizarse tanto para fines de auditoría como para pruebas de penetración.

#### Cómo utilizarla

La serie OWASP Spotlight proporciona una descripción general de la gestión de superficie de ataque utilizando Nettacker:
'Proyecto 11 - [Nettacker][spotlight11]'.

La documentación para Nettacker se proporciona en las páginas wiki del repositorio;
siga [estas instrucciones][nettacker-install] para instalarlo.

Nettacker es una herramienta de escaneo flexible y modular que puede utilizarse de muchas formas y con muchas opciones.
La mejor manera de comenzar a utilizarla es siguiendo el [video de introducción][nettacker-intro]
y luego continuar desde allí.

----

Traducción de versión [original en inglés][en080204].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario; si hay algo que necesita cambios,
[cree un issue][issue080204] o [edítelo en GitHub][edit080204].

[edit080204]: https://github.com/OWASP/DevGuide/blob/main/docs/es/06-verification/02-tools/04-nettacker.md
[en080204]: https://devguide.owasp.org/en/06-verification/02-tools/04-nettacker/
[issue080204]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2006-verification/02-tools/04-nettacker
[nettacker-brute]: https://github.com/OWASP/Nettacker/wiki/Modules#brute-modules
[nettacker-install]: https://github.com/OWASP/Nettacker/wiki/Installation
[nettacker-intro]: https://github.com/OWASP/Nettacker/wiki#introduction
[nettacker-project]: https://owasp.org/www-project-nettacker/
[nettacker-scan]: https://github.com/OWASP/Nettacker/wiki/Modules#scan-modules
[nettacker-vuln]: https://github.com/OWASP/Nettacker/wiki/Modules#vuln-modules
[spotlight11]: https://www.youtube.com/watch?v=OGv7OtG127A
