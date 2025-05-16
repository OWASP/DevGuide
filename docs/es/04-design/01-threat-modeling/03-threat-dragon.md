![Logo de Threat dragon](../../../assets/images/logos/threat_dragon.png "OWASP Threat Dragon"){ align=right width=180 }

El proyecto [Threat Dragon][tdtm] de OWASP  proporciona una herramienta diagramática para el modelado de amenazas
de aplicaciones, APIs y sistemas de software.
Es un Proyecto de Laboratorio OWASP con [varias versiones][tddownload] y está en desarrollo activo.

#### ¿Qué es Threat Dragon?

Threat Dragon es una herramienta que puede ayudar a los equipos de desarrollo con su proceso de modelado de amenazas.
Permite crear y modificar diagramas de flujo de datos que proporcionan el
contexto y dirección para las actividades de modelado de amenazas.
También almacena los detalles de las amenazas identificadas durante las sesiones de modelado de amenazas,
y éstas se guardan junto con el diagrama del modelo de amenazas en un archivo basado en texto.
Threat Dragon también puede generar el diagrama del modelo de amenazas y las amenazas asociadas como un reporte PDF.

#### ¿Por qué usarlo?

Threat Dragon es una herramienta útil para equipos pequeños que desean crear modelos de amenazas rápida y fácilmente.
Threat Dragon tiene como objetivos:

* Simplicidad - puedes instalar y comenzar a usar Threat Dragon muy rápidamente
* Flexibilidad - la diagramación y generación de amenazas permite describir todo tipo de amenazas
* Accesibilidad - varios tipos diferentes de equipos pueden beneficiarse de la facilidad de uso de Threat Dragon

Admite varias metodologías y categorizaciones de amenazas utilizadas durante las actividades de modelado de amenazas:

* STRIDE
* LINDDUN
* PLOT4ai
* CIA
* DIE

y puede ser utilizado por todo tipo de equipos de desarrollo.

#### Cómo usarlo

La serie Spotlight de OWASP proporciona una visión general de Threat Dragon y cómo usarlo:
'Proyecto 22 - [OWASP Threat Dragon][spotlight22]'.

Es sencillo comenzar a usar Threat Dragon; la última versión está [disponible para usar en línea][tddemo]:

1. seleccione 'Conectarse con Sesión Local' (Iniciar sesión en sesión local)
2. seleccione 'Crear un nuevo modelo de amenazas (threat model) desde cero' (Explorar un modelo de amenazas de ejemplo)
3. seleccione 'Version 2 Demo Model' (Modelo de demostración versión 2)
4. Se muestra los metadatos del modelo de amenazas que pueden ser editados
5. haga clic en el diagrama 'Main Request Data Flow' (Flujo de datos de solicitud principal)
    para mostrar el diagrama de flujo de datos
6. los componentes del diagrama pueden ser inspeccionados, y se muestran sus amenazas asociadas
7. los componentes pueden ser añadidos y eliminados, junto con la edición de sus propiedades

Threat Dragon se distribuye como una aplicación de escritorio multiplataforma y como una aplicación web.
La [aplicación de escritorio][tddownload] puede descargarse para Windows, Linux y MacOS.
La aplicación web puede ejecutarse utilizando un [contenedor Docker][tddocker] o desde el [código fuente][tdcode].

Una característica importante de Threat Dragon es la salida de informes en PDF que puede utilizarse para documentación
y propósitos de cumplimiento GRC; desde la ventana de metadatos del modelo de amenazas, haga clic en el botón Reporte.

#### Referencias

* OWASP [Threat Dragon][tdtm]

----

Traducción de versión [original en inglés][en060103].

La Guía para Desarrolladores de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse,
[cree un issue][issue060103] o [edítelo en GitHub][edit060103].

[edit060103]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/01-threat-modeling/03-threat-dragon.md
[en060103]: https://devguide.owasp.org/en/04-design/01-threat-modeling/03-threat-dragon/
[issue060103]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/01-threat-modeling/03-threat-dragon
[tddemo]: https://www.threatdragon.com/#/
[tdcode]: https://github.com/OWASP/threat-dragon
[tddocker]: https://hub.docker.com/r/owasp/threat-dragon/tags
[tddownload]: https://github.com/OWASP/threat-dragon/releases
[tdtm]: https://owasp.org/www-project-threat-dragon/
[spotlight22]: https://youtu.be/hUOAoc6QGJo
