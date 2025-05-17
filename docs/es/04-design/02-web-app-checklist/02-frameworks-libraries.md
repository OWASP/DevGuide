Las bibliotecas de código seguro y los marcos de software con seguridad integrada ayudan
a los desarrolladores a protegerse contra fallos de diseño e implementación relacionados con la seguridad.

Consulte el control proactivo [C4: Abordar la Seguridad desde el Principio][control4]
y sus [hojas de referencia][csproactive-c2] para más contexto del proyecto Top 10 Controles Proactivos de OWASP.

Para listas de verificación específicas de tecnología, consulte las Hojas de Referencia de OWASP apropiadas:

* [Seguridad AJAX][csajax]
* [Fortalecimiento de seguridad de la cadena de herramientas basada en C][cscbased]
* [Seguridad Django][csdjango]
* [Django REST framework][csdjangorest]
* [Seguridad Docker][csdocker]
* [Seguridad DotNet][csdotnet]
* [Seguridad GraphQL][csgraphql]
* [Infraestructura como Código][csias]
* [Seguridad Java][csjava]
* [Gestión de Javascript][csjcavascript]
* [Kubernetes][cskube]
* [Seguridad Laravel][cslaravel]
* [Seguridad de Microservicios][csmicro]
* [Mejores prácticas de seguridad NPM][csnpm]
* [Seguridad Node.js][csnode]
* [Seguridad Node.js para Docker][csnodedocker]
* [Configuración PHP][csphp]
* [APIs REST][csrest] y [cómo evaluarlas][csrassess]
* [Seguridad Ruby on Rails][csruby]
* [Framework Symfony][cssymfony]
* [Servicios Web][cswebservice]
* [Seguridad XML][csxml]

y utilícelas como punto de partida para una lista de verificación adaptada a la tecnología utilizada por el proyecto.

Además, considere las siguientes comprobaciones adicionales para marcos y bibliotecas.

### Marcos y Bibliotecas de Seguridad

1. Asegurar que los servidores, marcos y componentes del sistema ejecuten las últimas versiones y parches aprobados
2. Utilizar bibliotecas y marcos de fuentes confiables que se mantengan activamente y sean ampliamente utilizados
3. Revisar todas las aplicaciones secundarias y bibliotecas de terceros para determinar la necesidad empresarial
4. Validar la funcionalidad segura de todas las aplicaciones secundarias y bibliotecas de terceros
5. Crear y mantener un catálogo de inventario de todas las bibliotecas de terceros utilizando
    Análisis de Composición de Software (SCA)
6. Mantener proactivamente actualizadas todas las bibliotecas y componentes de terceros
7. Reducir la superficie de ataque encapsulando la biblioteca y exponiendo solo el comportamiento requerido en su software
8. Utilizar código administrado testeado y aprobado en lugar de crear nuevo código no administrado para tareas comunes
9. Utilizar APIs específicas para tareas integradas para realizar tareas del sistema operativo
10. No permitir que la aplicación emita comandos directamente al Sistema Operativo
11. Utilizar sumas de verificación o hashes para verificar la integridad del código interpretado,
    bibliotecas, ejecutables y archivos de configuración
12. Restringir a los usuarios la generación de nuevo código o la alteración del código existente
13. Implementar actualizaciones seguras utilizando canales cifrados

#### Referencias

* [Dependency Check][dependency] de OWASP
* [Top 10 Controles Proactivos][proactive10] de OWASP

----

Traducción de versión [original en inglés][en060202].

La Guía para Desarrolladores de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse
entonces [envía un issue][issue060202] o [edita en GitHub][edit060202].

[csajax]: https://cheatsheetseries.owasp.org/cheatsheets/AJAX_Security_Cheat_Sheet
[cscbased]: https://cheatsheetseries.owasp.org/cheatsheets/C-Based_Toolchain_Hardening_Cheat_Sheet
[csdjango]: https://cheatsheetseries.owasp.org/cheatsheets/Django_Security_Cheat_Sheet
[csdjangorest]: https://cheatsheetseries.owasp.org/cheatsheets/Django_REST_Framework_Cheat_Sheet
[csdocker]: https://cheatsheetseries.owasp.org/cheatsheets/Docker_Security_Cheat_Sheet
[csdotnet]: https://cheatsheetseries.owasp.org/cheatsheets/DotNet_Security_Cheat_Sheet
[csgraphql]: https://cheatsheetseries.owasp.org/cheatsheets/GraphQL_Cheat_Sheet
[csias]: https://cheatsheetseries.owasp.org/cheatsheets/Infrastructure_as_Code_Security_Cheat_Sheet
[csjava]: https://cheatsheetseries.owasp.org/cheatsheets/Java_Security_Cheat_Sheet
[csjcavascript]: https://cheatsheetseries.owasp.org/cheatsheets/Third_Party_Javascript_Management_Cheat_Sheet
[cskube]: https://cheatsheetseries.owasp.org/cheatsheets/Kubernetes_Security_Cheat_Sheet
[cslaravel]: https://cheatsheetseries.owasp.org/cheatsheets/Laravel_Cheat_Sheet
[csmicro]: https://cheatsheetseries.owasp.org/cheatsheets/Microservices_Security_Cheat_Sheet
[csnpm]: https://cheatsheetseries.owasp.org/cheatsheets/NPM_Security_Cheat_Sheet
[csnode]: https://cheatsheetseries.owasp.org/cheatsheets/Nodejs_Security_Cheat_Sheet
[csnodedocker]: https://cheatsheetseries.owasp.org/cheatsheets/NodeJS_Docker_Cheat_Sheet
[csphp]: https://cheatsheetseries.owasp.org/cheatsheets/PHP_Configuration_Cheat_Sheet
[csrest]: https://cheatsheetseries.owasp.org/cheatsheets/REST_Security_Cheat_Sheet
[csrassess]: https://cheatsheetseries.owasp.org/cheatsheets/REST_Assessment_Cheat_Sheet.html
[csruby]: https://cheatsheetseries.owasp.org/cheatsheets/Ruby_on_Rails_Cheat_Sheet
[cssymfony]: https://cheatsheetseries.owasp.org/cheatsheets/Symfony_Cheat_Sheet
[cswebservice]: https://cheatsheetseries.owasp.org/cheatsheets/Web_Service_Security_Cheat_Sheet
[csxml]: https://cheatsheetseries.owasp.org/cheatsheets/XML_Security_Cheat_Sheet
[csproactive-c2]: https://cheatsheetseries.owasp.org/IndexProactiveControls.html#c2-leverage-security-frameworks-and-libraries
[control4]: https://top10proactive.owasp.org/the-top-10/c4-secure-architecture/
[dependency]: https://owasp.org/www-project-dependency-check/
[edit060202]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/02-web-app-checklist/02-frameworks-libraries.md
[en060202]: https://devguide.owasp.org/en/04-design/02-web-app-checklist/02-frameworks-libraries/
[issue060202]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/02-web-app-checklist/02-frameworks-libraries
[proactive10]: https://top10proactive.owasp.org/
