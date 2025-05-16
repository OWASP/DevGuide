![OSHP logo](../../../assets/images/logos/oshp.png "OSHP"){ align=right width=140 }

El Proyecto de Cabeceras Seguras de OWASP - OWASP Secure Headers Project ([OSHP][oshp]) proporciona información
sobre las cabeceras de respuesta HTTP
para aumentar la seguridad de una aplicación web.

El proyecto de documentación OSHP es un Proyecto de Laboratorio de OWASP
y concientiza sobre las cabeceras seguras y su uso.

#### ¿Qué es OSHP?

El [proyecto OSHP][oshp] proporciona explicaciones para las cabeceras de respuesta HTTP
que una aplicación puede utilizar para aumentar la seguridad de la aplicación.
Una vez establecidas, las cabeceras de respuesta HTTP pueden restringir a los navegadores modernos
de incurrir en vulnerabilidades fácilmente prevenibles.

OSHP contiene orientación y descargas sobre:

* Explicaciones y uso de cabeceras de respuesta
* Enlaces a soporte individual de navegadores
* Orientación y mejores prácticas
* Recursos técnicos en forma de herramientas y documentos
* Fragmentos de código para ayudar a trabajar con cabeceras de seguridad HTTP

#### ¿Por qué utilizarlo?

El OSHP es un proyecto de documentación que explica el razonamiento y uso de las cabeceras de respuesta HTTP.
Es el documento de referencia para orientación y mejores prácticas;
la información sobre cabeceras de respuesta HTTP es el mejor consejo, en una sola ubicación, y se mantiene actualizada.

#### Cómo utilizarlo

La serie OWASP Spotlight proporciona una descripción general de este proyecto y sus usos:
'Proyecto 24 - [OWASP Security Headers Project][spotlight24]'.

OSHP documenta [varias herramientas][oshp-tools] útiles para la inspección, análisis
y escaneo de cabeceras de respuesta HTTP:

* hsecscan
* humble
* SecurityHeaders.com
* Mozilla Observatory
* Recx Security Analyser
* testssl.sh
* DrHEADer
* csp-evaluator

OSHP también proporciona enlaces a [bibliotecas][oshp-libs] de desarrollo
que proporcionan cabeceras de respuesta HTTP seguras en una variedad de lenguajes y frameworks.

----

Traducción de versión [original en inglés][en080205].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario; si hay algo que necesita cambios,
[cree un issue][issue080205] o [edítelo en GitHub][edit080205].

[edit080205]: https://github.com/OWASP/DevGuide/blob/main/docs/es/06-verification/02-tools/05-secure-headers.md
[en080205]: https://devguide.owasp.org/en/06-verification/02-tools/05-secure-headers/
[issue080205]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2006-verification/02-tools/05-secure-headers
[oshp]: https://owasp.org/www-project-secure-headers/
[oshp-libs]: https://owasp.org/www-project-secure-headers/#development-libraries
[oshp-tools]: https://owasp.org/www-project-secure-headers/#analysis-tools
[spotlight24]: https://youtu.be/N4F3VWQYU9E
