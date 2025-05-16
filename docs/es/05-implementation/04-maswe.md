![Logo de lista de verificación MAS](../../../assets/images/logos/mas.png "OWASP MASWE"){ align=right width=180 }

El proyecto insignia de OWASP [Seguridad de Aplicaciones Móviles][masproject] (MAS)
proporciona estándares de la industria para la seguridad de aplicaciones móviles.

El proyecto OWASP [MASWE][maswe] es una de las herramientas proporcionadas por MAS,
y ofrece una lista de debilidades que se han encontrado en varias aplicaciones móviles.

#### ¿Qué es el MASWE?

La [Enumeración de Debilidades][maswe] de MAS lista debilidades y, por lo tanto, posibles vulnerabilidades,
que se han encontrado en varias aplicaciones móviles a lo largo del tiempo.

El MASWE se divide en categorías de debilidades que corresponden a las categorías de verificación de [MASVS][masvs]:

* [MASVS-STORAGE](https://mas.owasp.org/MASWE/MASVS-STORAGE/MASWE-0001/) almacenamiento de datos sensibles
* [MASVS-CRYPTO](https://mas.owasp.org/MASWE/MASVS-CRYPTO/MASWE-0009/) mejores prácticas de criptografía
* [MASVS-AUTH](https://mas.owasp.org/MASWE/MASVS-AUTH/MASWE-0028/) mecanismos de autenticación y autorización
* [MASVS-NETWORK](https://mas.owasp.org/MASWE/MASVS-NETWORK/MASWE-0047/) comunicaciones de red
* [MASVS-PLATFORM](https://mas.owasp.org/MASWE/MASVS-PLATFORM/MASWE-0053/) interacciones con la plataforma móvil
* [MASVS-CODE](https://mas.owasp.org/MASWE/MASVS-CODE/MASWE-0075/) plataforma y software de terceros
* [MASVS-RESILIENCE](https://mas.owasp.org/MASWE/MASVS-RESILIENCE/MASWE-0089/) integridad
  y ejecución en una plataforma confiable
* [MASVS-PRIVACY](https://mas.owasp.org/MASWE/MASVS-PRIVACY/MASWE-0108/) privacidad de usuarios, datos y recursos

#### ¿Por qué usarlo?

Aunque el MASWE es un proyecto relativamente nuevo desde 2024, ya proporciona un lenguaje común
para discutir y categorizar debilidades encontradas en aplicaciones móviles.
También proporciona una lista de posibles vulnerabilidades que deben considerarse durante el ciclo de vida del diseño
y al crear o revisar requisitos de seguridad para aplicaciones móviles.

El MASWE es una valiosa lista de lo que podría salir mal con las aplicaciones móviles junto
con las actividades de actores maliciosos.

#### Cómo usarlo

La Enumeración de Debilidades Comunes ([CWE][cwe]), publicada por MITRE, puede ser utilizada por arquitectos de seguridad
para que estén conscientes de qué debilidades y vulnerabilidades potenciales podrían estar presentes en una aplicación.
Los equipos de desarrollo pueden usar el CWE como referencia para estas debilidades
y para ayudar a comprender cualquier mitigación.
Estos son solo dos ejemplos de cómo se utiliza ampliamente el CWE.

De manera similar, el MASWE puede utilizarse en el desarrollo de aplicaciones móviles para:

* informar a los equipos de desarrollo sobre debilidades específicas
* identificación de requisitos de seguridad
* utilizarse como ayuda para la capacitación
* proporcionar categorización de debilidades

Esta lista es solo un punto de partida; hay muchos usos para el MASWE.

#### Referencias

* Proyecto de Seguridad de Aplicaciones Móviles ([MAS][masproject])
* Enumeración de Debilidades MAS ([MASWE][maswe])
* Enumeración de Debilidades Comunes de MITRE ([CWE][cwe])
* Estándar de Verificación MAS ([MASVS][masvs])
* Lista de Verificación [MAS][masc]
* Guía de Pruebas MAS ([MASTG][mastg])

----

Traducción de versión [original en inglés][en0704].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario;
si ve algo que necesita cambios, entonces [cree un issue][issue0704] o [edítelo en GitHub][edit0704].

[cwe]: https://cwe.mitre.org/
[edit0704]: https://github.com/OWASP/DevGuide/blob/main/docs/es/05-implementation/04-maswe.md
[en0704]: https://devguide.owasp.org/en/05-implementation/04-maswe/
[issue0704]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2005-implementation/04-maswe
[masproject]: https://owasp.org/www-project-mobile-app-security/
[masc]: https://mas.owasp.org/checklists/
[mastg]: https://mas.owasp.org/MASTG/
[maswe]: https://mas.owasp.org/MASWE/
[masvs]: https://mas.owasp.org/MASVS/
