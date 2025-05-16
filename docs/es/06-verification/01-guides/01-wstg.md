La [Guía de Testeo de Seguridad Web][wstg] (WSTG) de OWASP es una guía completa para probar la seguridad de
aplicaciones web y servicios web.

El proyecto de [documentación WSTG][wstg] es un Proyecto Insignia de OWASP
y se puede acceder como un [documento basado en web][wstg-latest].

#### ¿Qué es WSTG?

El documento Guía de Testeo de Seguridad Web ([WSTG][wstg]) es una guía completa para probar la seguridad
de aplicaciones web y servicios web.
La WSTG proporciona un marco de mejores prácticas comúnmente utilizadas por testeadores de penetración externos
y organizaciones que realizan pruebas internas.

El documento WSTG describe un [marco de pruebas de aplicaciones web][wstg-framework] sugerido
y también proporciona información general sobre [cómo probar][wstg-howto] aplicaciones web con buenas prácticas de prueba.

Las pruebas se dividen en dominios:

1. Gestión de Configuración y Despliegue
2. Gestión de Identidad
3. Autenticación
4. Autorización
5. Gestión de Sesiones
6. Validación de Entrada
7. Manejo de Errores
8. Criptografía Débil
9. Lógica de Negocio
10. Del lado del Cliente
11. API

Cada prueba en cada dominio tiene suficiente información para entender y ejecutar la prueba, incluyendo:

* Descripción resumida
* Objetivos de la prueba
* Cómo realizar la prueba
* Remediación sugerida
* Herramientas recomendadas y referencias

Las pruebas se identifican con un número de referencia único,
por ejemplo, 'WSTG-APIT-01' se refiere a la primera prueba en el dominio 'Pruebas de API' proporcionada
en el documento WSTG.
Estas referencias son ampliamente utilizadas y comprendidas por las comunidades de pruebas y seguridad.

La WSTG también proporciona un Marco de Pruebas de Seguridad Web sugerido que pueden ser adaptados
a los procesos de una organización particular o puede proporcionar un marco de referencia generalmente aceptado.

#### ¿Por qué usarla?

El documento WSTG es ampliamente utilizado y se ha convertido en el estándar de facto sobre
lo que se requiere para pruebas completas de aplicaciones web.
El proceso de pruebas de seguridad de una organización debería considerar el contenido de la WSTG, o tener equivalentes,
que ayuden a la organización a ajustarse a la expectativa general de la comunidad de seguridad.
El documento de referencia WSTG puede ser adoptado completamente, parcialmente o no adoptarse en absoluto;
según las necesidades y requisitos de una organización.

#### Cómo utilizarla

La serie OWASP Spotlight proporciona una descripción  general de cómo utilizar la WSTG:
'Proyecto 1 - [Aplicando la Guía de Pruebas de OWASP][spotlight01]'.

Se puede acceder a la WSTG a través del [documento web en línea][wstg-latest].
La sección sobre principios y técnicas de pruebas proporciona conocimientos fundamentales,
junto con consejos sobre pruebas dentro de metodologías típicas del Ciclo de Vida de Desarrollo Seguro (SDLC)
y pruebas de penetración.

Las pruebas individuales descritas en los diversos dominios de prueba deben ser seleccionadas
o descartadas según sea necesario;
no todas las pruebas serán relevantes para cada aplicación web o requisito organizacional,
y las pruebas deben adaptarse para proporcionar al menos la cobertura mínima de pruebas
sin gastar demasiado esfuerzo en las pruebas.

#### Referencias

* Proyecto OWASP [Guía de Pruebas de Seguridad Web][wstg] (WSTG)
* [Descargas de WSTG][wstg-latest]

----

Traducción de versión [original en inglés][en080101].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario; si hay algo que necesita cambios,
[cree un issue][issue080101] o [edítelo en GitHub][edit080101].

[edit080101]: https://github.com/OWASP/DevGuide/blob/main/docs/es/06-verification/01-guides/01-wstg.md
[en080101]: https://devguide.owasp.org/en/06-verification/01-guides/01-wstg/
[issue080101]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2006-verification/01-guides/01-wstg
[spotlight01]: https://youtu.be/bxQPePVDbQk
[wstg]: https://owasp.org/www-project-web-security-testing-guide/
[wstg-framework]: https://owasp.org/www-project-web-security-testing-guide/latest/3-The_OWASP_Testing_Framework/0-The_Web_Security_Testing_Framework
[wstg-howto]: https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/
[wstg-latest]: https://owasp.org/www-project-web-security-testing-guide/stable/
