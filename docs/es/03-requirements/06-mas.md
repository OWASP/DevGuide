![MAS logo](../../assets/images/logos/mas.png "OWASP MAS"){ align=right width=180 }

El proyecto insignia de OWASP [Seguridad de Aplicaciones Móviles][masproject] (MAS) proporciona
estándares de la industria para la seguridad de aplicaciones móviles.

El proyecto MAS cubre los procesos, técnicas y herramientas utilizados
para las pruebas de seguridad de aplicaciones móviles.
Proporciona un conjunto de casos de prueba que permite a los testeadores entregar resultados consistentes y completos.
El proyecto OWASP MAS proporciona tanto el [Estándar de Verificación de Seguridad de Aplicaciones Móviles][masvs] (MASVS)
para aplicaciones móviles como la [Guía de Pruebas de Seguridad de Aplicaciones Móviles][mastg] (MASTG).

#### ¿Qué es MASVS?

El [OWASP MASVS][mas] es utilizado por arquitectos y desarrolladores de software móvil
para desarrollar aplicaciones móviles seguras,
así como por evaluadores de seguridad para garantizar la integridad y consistencia de los resultados de las pruebas.
El proyecto MAS tiene varios usos; cuando se trata de definir requisitos,
el MASVS contiene una lista de controles de seguridad para aplicaciones móviles.

Los controles de seguridad se dividen en varias categorías:

* [MASVS-STORAGE](https://mas.owasp.org/MASVS/05-MASVS-STORAGE/) / [Hojas de Referencia][masvs-storage]
* [MASVS-CRYPTO](https://mas.owasp.org/MASVS/06-MASVS-CRYPTO/) / [Hojas de Referencia][masvs-crypto]
* [MASVS-AUTH](https://mas.owasp.org/MASVS/07-MASVS-AUTH/) / [Hojas de Referencia][masvs-auth]
* [MASVS-NETWORK](https://mas.owasp.org/MASVS/08-MASVS-NETWORK/) / [Hojas de Referencia][masvs-network]
* [MASVS-PLATFORM](https://mas.owasp.org/MASVS/09-MASVS-PLATFORM/) / [Hojas de Referencia][masvs-platform]
* [MASVS-CODE](https://mas.owasp.org/MASVS/10-MASVS-CODE/) / [Hojas de Referencia][masvs-code]
* [MASVS-RESILIENCE](https://mas.owasp.org/MASVS/11-MASVS-RESILIENCE/) / [Hojas de Referencia][masvs-resilience]
* [MASVS-PRIVACY](https://mas.owasp.org/MASVS/12-MASVS-PRIVACY/) / [Hojas de Referencia][masvs-privacy]

La última categoría, MASVS-PRIVACY, está siendo reelaborada por lo que está sujeta a cambios.

#### ¿Por qué usar MASVS?

El OWASP MASVS es el estándar de la industria para [seguridad de aplicaciones móviles][csmas]
y se espera que cualquier conjunto dado de requisitos de seguridad satisfaga el MASVS.
Al definir requisitos de seguridad para aplicaciones móviles, cada control de seguridad en el MASVS debe ser considerado.

#### Cómo usar MASVS

MASVS puede ser [accedido en línea][masvs] y se pueden seguir los enlaces para cada control de seguridad.
Además, MASVS puede descargarse como PDF que puede, por ejemplo, utilizarse para fines de evidencia o cumplimiento.
Inspeccione cada control dentro de MASVS y considérelo como un requisito de seguridad potencial.

Las Hojas de Referencia de OWASP han sido indexadas específicamente para [cada categoría del MASVS][csmasvs],
que pueden utilizarse como guía para decidir si la categoría debe incluirse en el esquema de pruebas.

#### Referencias

* [Seguridad de Aplicaciones Móviles][mas] de OWASP(MAS - Mobile Application Security)
* [Proyecto][masproject] MAS
* [Lista de verificación][masc] MAS
* [Estándar de Verificación][masvs] MAS (MASVS)
* Hojas de Referencia de [Seguridad de Aplicaciones Móviles][csmas] de OWASP

----

Traducción de versión [original en inglés][en0506].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiar
entonces [cree un issue][issue0506] o [edítelo en GitHub][edit0506].

[csmas]: https://cheatsheetseries.owasp.org/cheatsheets/Mobile_Application_Security_Cheat_Sheet
[csmasvs]: https://cheatsheetseries.owasp.org/IndexMASVS
[edit0506]: https://github.com/OWASP/DevGuide/blob/main/docs/es/03-requirements/06-mas.md
[en0506]: https://devguide.owasp.org/en/03-requirements/06-mas/
[issue0506]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2003-requirements/06-mas
[mas]: https://mas.owasp.org/
[masc]: https://mas.owasp.org/checklists/
[masproject]: https://owasp.org/www-project-mobile-app-security/
[mastg]: https://mas.owasp.org/MASTG/
[masvs]: https://mas.owasp.org/MASVS/
[masvs-storage]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-storage
[masvs-crypto]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-crypto
[masvs-auth]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-auth
[masvs-network]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-network
[masvs-platform]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-platform
[masvs-code]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-code
[masvs-resilience]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-resilience
[masvs-privacy]: https://cheatsheetseries.owasp.org/IndexMASVS.html#masvs-privacy
