Esta sección aborda el Perfil de Riesgo de la Aplicación,
una actividad en el Modelo de Madurez de Garantía de Software de OWASP ([SAMM][samm]).
La actividad de perfil de riesgo es parte de la práctica de Evaluación de Amenazas en la función empresarial de Diseño.

#### Descripción general

La gestión de riesgos es la identificación, evaluación y priorización de riesgos para la aplicación o sistema.
El objetivo de la gestión de riesgos es garantizar que la incertidumbre no desvíe las actividades de desarrollo
de los objetivos empresariales.

La remediación es la estrategia elegida en respuesta a un riesgo para el sistema empresarial,
y estos riesgos se identifican utilizando diversas técnicas como modelado de amenazas
y análisis de requisitos de seguridad.

La gestión de riesgos puede dividirse en dos fases. Primero, crear un perfil de riesgo para la aplicación
y luego proporcionar soluciones (remediar) a esos riesgos de la manera que mejor convenga al negocio;
la gestión de riesgos siempre debe estar orientada por los objetivos el negocio.

#### Perfil de riesgo de la aplicación

El perfil de riesgo de la aplicación se crea para comprender la probabilidad y el impacto de un ataque.
Con el tiempo, se podrían crear varios perfiles que deberían almacenarse en un inventario de perfiles de riesgo,
e idealmente, los perfiles de riesgo deberían revisarse como parte de la estrategia
de desarrollo seguro de la organización.

Cuantificar los riesgos es a menudo difícil y hay muchas formas de abordar esto;
consulte la lista de lectura a continuación para conocer diversas estrategias
para crear un modelo de calificación de riesgos.
La página de OWASP sobre [Metodología de Calificación de Riesgos][rrm] describe
algunos pasos para identificar y cuantificar riesgos:

1. Identificar un riesgo
2. Factores para estimar la probabilidad
3. Factores para estimar el impacto
4. Determinar la gravedad del riesgo
5. Decidir qué corregir
6. Personalizar el modelo de calificación de riesgos

Las actividades involucradas en la creación de un perfil de riesgo dependen mucho de los procesos
y el nivel de madurez de la organización, lo cual está más allá del alcance de esta
Guía del Desarrollador, por lo que consulte la lectura adicional que se lista a continuación
para obtener orientación y ejemplos.

#### Remediación

Los riesgos identificados durante la evaluación de amenazas, por ejemplo,
a través del perfil de riesgo o mediante modelado de amenazas,
deben tener soluciones o remedios aplicados.

Hay cuatro formas comunes de manejar el riesgo, a menudo representadas por el acrónimo TAME:

1. Transferir: el riesgo se considera grave pero puede transferirse a otra parte

2. Aceptar: el negocio es consciente del riesgo pero se ha decidido que no se necesita tomar ninguna acción;
    el nivel de riesgo se considera aceptable

3. Mitigar: el riesgo se considera lo suficientemente grave como para requerir la implementación de controles de seguridad
    para reducir el riesgo a un nivel aceptable

4. Eliminar / Evitar: el riesgo puede evitarse o eliminarse completamente,
    a menudo eliminando el objeto asociado con el riesgo

Ejemplos:

1. Transferir: un ejemplo común de transferencia de riesgo es el uso de un seguro de terceros
    en respuesta al riesgo de RansomWare.
    Se pagan primas de seguro, pero las pérdidas para el negocio están cubiertas por el seguro

2. Aceptar: a veces un riesgo es lo suficientemente bajo en prioridad, o el resultado tolerable, para no mitigarlo,
    un ejemplo podría ser cuando se muestra la versión de software y esto es aceptable (o incluso deseable)

3. Mitigar: es común implementar un control de seguridad para mitigar el impacto de un riesgo, por ejemplo,
    la sanitización de entrada o la codificación de salida pueden usarse para información proporcionada
    por una fuente no confiable, o el uso de canales de comunicación cifrados para transferir información de alto riesgo

4. Eliminar: un ejemplo puede ser que una aplicación implemente funcionalidad heredada que ya no se usa,
    si hay un riesgo de que sea explotada, el riesgo puede eliminarse quitando esta funcionalidad heredada

#### Referencias

* [Metodología de Calificación de Riesgos de OWASP][rrm]
* [NIST 800-30 - Guía para Realizar Evaluaciones de Riesgos][nist]
* [Metodología Armonizada de Evaluación de Amenazas y Riesgos del Gobierno de Canadá][tra]
* [Resumen de Evaluación de Riesgos][rrs] de Mozilla y [Evaluación Rápida de Riesgos (RRA)][rra]
* [Sistema de Puntuación de Vulnerabilidades Comunes (CVSS)][cvss] utilizado para clasificación de severidad y riesgo

----

Traducción de versión [original en inglés][en0502].

La Guía de Desarrollador OWASP es un esfuerzo comunitario; si hay algo que necesite cambios
entonces [cree un issue][issue0502] o [edítelo en GitHub][edit0502].

[cvss]: https://www.first.org/cvss/
[edit0502]: https://github.com/OWASP/DevGuide/blob/main/docs/es/03-requirements/02-risk.md
[en0502]: https://devguide.owasp.org/en/03-requirements/02-risk/
[issue0502]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2003-requirements/02-risk
[nist]: https://csrc.nist.gov/publications/detail/sp/800-30/rev-1/final
[rra]: https://infosec.mozilla.org/guidelines/risk/rapid_risk_assessment.html
[rrm]: https://owasp.org/www-community/OWASP_Risk_Rating_Methodology
[rrs]: https://infosec.mozilla.org/guidelines/assessing_security_risk
[samm]: https://owaspsamm.org/about/
[tra]: https://cyber.gc.ca/en/guidance/harmonized-tra-methodology-tra-1
