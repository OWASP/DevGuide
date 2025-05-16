Esta sección trata sobre el Modelado de Amenazas, una actividad descrita en
el Modelo de Madurez de Aseguramiento de Software de OWASP ([SAMM][samm]).
El modelado de amenazas es parte de la práctica de seguridad de [Evaluación de Amenazas][sammdta]
en la función empresarial de [Diseño][sammd].

Gran parte del material de esta sección está extraído del [proyecto de Modelado de Amenazas][tmproject] de OWASP,
y la filosofía de esta sección intenta seguir el [Manifiesto de Modelado de Amenazas][tmmanifesto].

![TMM logo](../../../assets/images/logos/tmmanifesto.png "OWASP TM Manifesto"){ width=250 }

#### Descripción general

Las actividades de modelado de amenazas intentan descubrir lo que podría salir mal dentro de un sistema
y determinar qué hacer al respecto.
Los resultados del modelado de amenazas toman diversas formas, incluyendo modelos y diagramas de sistemas,
listas de amenazas, mitigaciones o suposiciones, notas de reuniones y más.
Esto puede reunirse en un único documento de modelo de amenazas; una representación estructurada de toda la información
que afecta a la seguridad de una aplicación.
Una buena visión general de esta actividad se proporciona en la sección sobre modelado de amenazas
del proyecto [Cultura de Seguridad][culturetm].

En esencia, es una visión de la aplicación y su entorno a través de cristales de seguridad.

El modelado de amenazas es un proceso para capturar, organizar y analizar toda esta información
y permite la toma de decisiones informadas sobre el riesgo de seguridad de la aplicación.
Además de producir un modelo, los esfuerzos típicos de modelado de amenazas también producen una lista priorizada
de vulnerabilidades de seguridad _potenciales_ en el concepto, los requisitos, el diseño o la implementación.
Cualquier vulnerabilidad potencial que se haya identificado a partir del modelo debe ser remediada
utilizando una de las estrategias comunes: mitigar, eliminar, transferir o aceptar la amenaza de ser explotada.

Hay muchas razones para hacer modelado de amenazas, pero la más importante es que esta actividad es _útil_,
probablemente es la única etapa en un ciclo de vida de desarrollo donde un equipo se detiene y pregunta:
"¿Qué puede salir mal?".

Hay otras razones para el modelado de amenazas, por ejemplo, el cumplimiento de estándares
o el análisis para la recuperación ante desastres, pero el objetivo principal del modelado de amenazas es remediar
vulnerabilidades (posibles) antes de que los actores maliciosos puedan explotarlas.

#### Qué es el modelado de amenazas

El modelado de amenazas trabaja para identificar, comunicar y comprender las amenazas y mitigaciones
dentro del contexto de proteger algo de valor.

El modelado de amenazas se puede aplicar a una amplia gama de cosas, incluyendo software, aplicaciones, sistemas, redes,
sistemas distribuidos, cosas en Internet de las cosas, procesos de negocio, etc.
Hay muy pocos productos técnicos que no puedan tener un modelado de amenazas;
que sea más o menos gratificante, dependiendo de cuánto éste se comunica, o interactúa, con el mundo.

Un documento de modelo de amenazas es un registro del proceso de modelado de amenazas, y a menudo incluye:

* una descripción / diseño / modelo de lo que es preocupante
* una lista de suposiciones que pueden ser verificadas o rechazadas en el futuro
    a medida que cambia el panorama de amenazas
* amenazas potenciales al sistema
* remediación / acciones a tomar para cada amenaza
* formas de validar el modelo y las amenazas, y verificación del éxito de las acciones tomadas

El modelo de amenazas debe estar en una forma que pueda ser fácilmente revisada y modificada
durante las discusiones posteriores de modelado de amenazas.

#### Por qué hacerlo

Como todas las actividades de ingeniería, el esfuerzo dedicado al modelado de amenazas tiene que ser justificable.
Raramente cualquier proyecto o desarrollo tiene esfuerzo de ingeniería que "salga sobrando",
y los beneficios del modelado de amenazas tienen que superar el costo de ingeniería de esta actividad.
Usualmente esto es difícil de cuantificar; una forma más fácil de abordarlo puede ser preguntar
¿cuáles son los costos de _no_ hacer modelado de amenazas?
Estos costos pueden consistir en fallas de cumplimiento, un mayor riesgo de ser explotado, daño a la reputación, etc.

La inclusión del modelado de amenazas en las actividades de desarrollo seguro puede ayudar a:

* Construir un diseño seguro
* Inversión eficiente de recursos; priorizar adecuadamente la seguridad, el desarrollo y otras tareas
* Reunir a Seguridad y Desarrollo para colaborar en una comprensión compartida, informando el desarrollo del sistema
* Identificar amenazas y requisitos de cumplimiento, y evaluar su riesgo
* Definir y construir los controles requeridos.
* Equilibrar riesgos, controles y usabilidad
* Identificar dónde construir un control es innecesario, basado en un riesgo aceptable
* Documentar amenazas y mitigación
* Asegurar que los requisitos de negocio (o metas) estén adecuadamente protegidos frente a
    un actor malicioso, accidentes u otras causas de impacto
* Identificación de casos de prueba de seguridad / escenarios de prueba de seguridad
    para probar los requisitos de seguridad

El modelado de amenazas también proporciona una clara "línea de visión" (mediante límites y alcances del objetivo)
a través de un proyecto que puede ser utilizada
para justificar otros esfuerzos de seguridad.
El modelo de amenazas permite que las decisiones de seguridad se tomen racionalmente, con toda la información disponible,
para que las decisiones de seguridad puedan ser adecuadamente respaldadas.
El proceso de modelado de amenazas naturalmente produce un argumento de aseguramiento que puede ser utilizado para explicar
y defender la seguridad de una aplicación.
Un argumento de aseguramiento comienza con algunas afirmaciones de alto nivel
y luego las justifica con sub-afirmaciones o evidencias.

#### Cuándo modelar amenazas

No hay un momento incorrecto para hacer modelado de amenazas;
cuanto antes se haga en el ciclo de vida del desarrollo, más beneficioso es,
pero el modelado de amenazas también es útil en cualquier momento durante el desarrollo de la aplicación.

El modelado de amenazas se aplica mejor de forma continua a lo largo de un proyecto de desarrollo de software.
El proceso es esencialmente el mismo en diferentes niveles de abstracción,
aunque la información se vuelve cada vez más granular a lo largo del ciclo de vida del desarrollo.
Idealmente, un modelo de amenazas de alto nivel debería definirse en la fase de concepto o planificación,
y luego refinarse durante las fases de desarrollo.
A medida que se agregan más detalles al sistema, se identifican nuevos vectores de ataque,
por lo que el proceso continuo de modelado de amenazas debe examinar, diagnosticar y abordar estas amenazas.

Nótese que es una parte natural del refinamiento de un sistema que se expongan nuevas amenazas.
Cuando se selecciona una tecnología particular, como Java por ejemplo,
se asume la responsabilidad de identificar las nuevas amenazas que se crean por esa elección.
Incluso decisiones de implementación como usar expresiones regulares para la validación
introducen nuevas amenazas potenciales que hay que tratar.

Modelado de amenazas: _cuanto antes mejor, pero nunca demasiado tarde_

#### Preguntas que hacer

A menudo, el modelado de amenazas es una actividad conceptual más que un proceso riguroso,
donde se reúnen equipos de desarrollo y se les pide que piensen en formas de comprometer la seguridad de su sistema.
Para proporcionar algo de estructura, es útil comenzar con el [Marco de Cuatro Preguntas][4QFW] de Shostack:

**1 ¿En qué estamos trabajando**?

Como punto de partida, se debe definir el alcance del Modelo de Amenazas.
Esto requerirá una comprensión de la aplicación que se está construyendo,
y algunos ejemplos de entradas para el modelo de amenazas podrían ser:

* Diagramas de arquitectura
* Transiciones de flujo de datos
* Clasificaciones de datos

Es común representar las respuestas a esta pregunta con uno o más diagramas de flujo de datos
y a menudo diagramas complementarios como diagramas de secuencia de mensajes.

Es mejor reunir a personas de diferentes roles con suficiente conciencia técnica y de riesgo
para que puedan acordar el marco a utilizar durante el ejercicio de modelado de amenazas.

**2 ¿Qué puede salir mal**?

Esta es una actividad de investigación para encontrar las principales amenazas que se aplican a tu aplicación.
Hay muchas formas de abordar la pregunta, incluida la discusión abierta o el uso de una estructura para ayudar a pensarlo.
Las técnicas y metodologías a considerar incluyen CIA, [STRIDE][stride], [LINDDUN][linddun],
[cadenas de eliminación cibernética][chains], [PASTA][pasta], patrones de ataque comunes ([CAPEC][capec]) y otros.

Existen recursos disponibles que ayudarán a identificar amenazas y vulnerabilidades.
OWASP proporciona un conjunto de tarjetas, [Cornucopia][corncards],
que ofrecen sugerencias y explicaciones para vulnerabilidades generales.
El juego de tarjetas de modelado de amenazas [Elevation of Privileges][eop]
es una forma fácil de comenzar con el modelado de amenazas,
y existe la versión OWASP de [Serpientes y Escaleras][snakes] que realmente gamifica estas actividades.

**3 ¿Qué vamos a hacer al respecto**?

En esta fase, se convierte los hallazgos del modelo de amenazas en acciones específicas.
Considere la remediación apropiada para cada amenaza identificada: Transferir, Evitar, Mitigar o Eliminar.

**4 ¿Hicimos un trabajo lo suficientemente bueno**?

Finalmente, realiza una actividad retrospectiva sobre el trabajo identificado para verificar
calidad, viabilidad, progreso o planificación.

El [Manual de Modelado de Amenazas][tmpb] de OWASP profundiza en estos aspectos prácticos
y proporciona estrategias para mantener el modelado de amenazas dentro de una organización.

#### Cómo hacerlo

No existe un único proceso para el modelado de amenazas.
Cómo se hace en la práctica variará según la cultura de la organización,
según qué tipo de sistema/aplicación se está modelando
y según las preferencias del propio equipo de desarrollo.
Las diversas técnicas y conceptos se discuten en la [Hoja de Referencia de Modelado de Amenazas][cstm]
y se pueden resumir así:

1. Terminología: intente usar términos estándar como actores, límites de confianza, etc,
    ya que esto ayudará a transmitir estos conceptos
2. Alcance: sea claro sobre lo que se está modelando y manténgase dentro de este alcance
3. Documentar: decida qué herramientas y qué resultados se requieren para satisfacer el cumplimiento, por ejemplo
4. Descomponer: divida el sistema que se está modelando en partes manejables
5. Confianza: identifique los límites de confianza, considere la [segmentación de red][ccsnet]
6. Agentes: identifique quiénes son los actores (maliciosos o no) y qué pueden hacer
7. Categorizar: priorice las amenazas teniendo en cuenta la probabilidad, el impacto y cualquier otro factor
8. Remediación: asegúrese de decidir qué hacer con las amenazas identificadas, la razón principal del modelado de amenazas

Vale la pena decirlo de nuevo: hay muchas formas de hacer modelado de amenazas,
todas perfectamente válidas, así que elija el proceso correcto que funcione para un equipo específico.

#### Recomendación final

Algunas palabras finales sobre el modelado de amenazas.

**Hágalo incremental**:

Considere firmemente usar [modelado de amenazas incremental][sammgata].
Sin duda alguna es una mala idea tratar de modelar completamente una aplicación o sistema existente;
puede ser muy lento modelar todo un sistema,
y para cuando se complete dicho modelo, probablemente ya estaría desactualizado.
En cambio, modela incrementalmente nuevas características o mejoras a medida que se desarrollan.

El modelado de amenazas incremental asume que las aplicaciones y características existentes
ya han sido atacadas con el tiempo y estas vulnerabilidades del mundo real han sido remediadas.
Son las nuevas características o nuevas aplicaciones las que presentan un mayor riesgo de seguridad;
si son vulnerables, reducirán la seguridad de la aplicación o sistema existente.
Concentrarse en los nuevos cambios aplica el esfuerzo de modelado de amenazas en el lugar donde más se necesita;
como mínimo, los cambios no deberían empeorar la seguridad, e, idealmente, la seguridad debería mejorar.

**Las herramientas son secundarias**:

Es bueno estandarizar las herramientas de modelado de amenazas en toda la organización,
pero también permitir que los equipos elijan cómo registran sus modelos de amenazas.
Si un equipo decide usar Threat Dragon, por ejemplo, y otro quiere usar una pizarra,
entonces eso generalmente está bien.
Las discusiones mantenidas durante el proceso de modelado de amenazas son más importantes que la herramienta utilizada,
aunque podrías preguntar al equipo que usa la pizarra cómo implementan el control de cambios para sus modelos.

**La brevedad es primordial**:

Es muy fácil crear un modelo de amenazas que se parezca mucho a un diagrama del sistema,
con muchos componentes y flujos de datos.
Esto logrará un diagrama convincente, pero no es un modelo específico para la amenaza de exploits.
En cambio, concéntrese en las superficies de ataque/amenaza y sea robusto al consolidar múltiples componentes del sistema
en un solo componente del modelo de amenazas.
Esto mantendrá el número de componentes y flujos de datos de tamano manejable, y enfoca la discusión en lo que más importa:
actores maliciosos (externos o internos) tratando de comprometer la seguridad de su sistema.

**Elige tu metodología**:

Es una buena estrategia elegir una metodología de categorización de amenazas para toda la organización
y luego tratar de mantenerla.
Por ejemplo, podría ser [STRIDE][stride] o [LINDDUN][linddun], pero si la tríada CIA proporciona suficiente granularidad,
entonces también es una elección perfectamente buena.

#### Lectura adicional

* [Manifiesto de Modelado de Amenazas][tmmanifesto]
* [Proyecto de Modelo de Amenazas][tmproject] de OWASP
* [Hoja de Referencia de Modelado de Amenazas]  [cstm]  de OWASP
* [Manual de Modelado de Amenazas (OTMP)][tmpb]  de OWASP
* [Hoja de Referencia de Análisis de Superficie de Ataque][asacs]  de OWASP
* Páginas comunitarias de OWASP sobre [Modelado de Amenazas][TM] y el [Proceso de Modelado de Amenazas][TMP]
* [El Marco de Cuatro Preguntas Para el Modelado de Amenazas](https://youtu.be/Yt0PhyEdZXU) video de 60 segundos
* [Cadena de Eliminación Cibernética][chains] de Lockheed
* Proceso de VerSprite para Simulación de Ataques y Análisis de Amenazas ([PASTA][pasta])
* [Modelado de Amenazas: Diseñando para la Seguridad][TMdesigning]
* [Modelado de Amenazas: Una Guía Práctica para Equipos de Desarrollo][TMpractical]

#### Recursos

* [Marco de Cuatro Preguntas][4QFW] de Shostack
* [pytm][PYTM] herramienta de Modelado de Amenazas Pythónico de OWASP
* OWASP [Threat Dragon][tdtm] herramienta de modelado de amenazas usando diagramas de flujo de datos
* [Threagile](https://threagile.io), un proyecto de código abierto que proporciona modelado de amenazas Ágil
* [Herramienta de Modelado de Amenazas][TMT] de Microsoft, una herramienta ampliamente utilizada
    en toda la comunidad de seguridad y de descarga gratuita
* [threatspec](https://github.com/threatspec/threatspec), una herramienta de código abierto basada
    en comentarios en línea con el código
* Enumeración y Clasificación de Patrones de Ataque Comunes de MITRE ([CAPEC][capec])
* [Calculadora del Sistema Común de Puntuación de Vulnerabilidades][nist-cvss] de NIST

----

Traducción de versión [original en inglés][en060101].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario; si hay algo que necesita cambios,
[cree un issue][issue060101] o [edítelo en GitHub][edit060101].

[4QFW]: https://github.com/adamshostack/4QuestionFrame
[asacs]: https://cheatsheetseries.owasp.org/cheatsheets/Attack_Surface_Analysis_Cheat_Sheet
[capec]: https://capec.mitre.org/
[chains]: https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html
[corncards]: https://owasp.org/www-project-cornucopia/
[ccsnet]: https://cheatsheetseries.owasp.org/cheatsheets/Network_Segmentation_Cheat_Sheet
[cstm]: https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet
[culturetm]: https://owasp.org/www-project-security-culture/stable/6-Threat_Modelling/
[eop]: https://shostack.org/games/elevation-of-privilege
[edit060101]: https://github.com/OWASP/DevGuide/blob/main/docs/es/04-design/01-threat-modeling/01-threat-modeling.md
[en060101]: https://devguide.owasp.org/en/04-design/01-threat-modeling/01-threat-modeling/
[issue060101]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2004-design/01-threat-modeling/01-threat-modeling
[linddun]: https://linddun.org/
[nist-cvss]: https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator
[pasta]: https://versprite.com/blog/what-is-pasta-threat-modeling/
[PYTM]: https://owasp.org/www-project-pytm/
[samm]: https://owaspsamm.org/about/
[sammd]: https://owaspsamm.org/model/design/
[sammdta]: https://owaspsamm.org/model/design/threat-assessment/
[sammgata]: https://owaspsamm.org/guidance/agile/#TA
[snakes]: https://owasp.org/www-project-snakes-and-ladders/
[stride]: https://en.wikipedia.org/wiki/STRIDE_%28security%29
[tdtm]: https://owasp.org/www-project-threat-dragon/
[tmpb]: https://owasp.org/www-project-threat-modeling-playbook/
[tmproject]: https://owasp.org/www-project-threat-model/
[tmmanifesto]: https://www.threatmodelingmanifesto.org/
[TM]: https://owasp.org/www-community/Threat_Modeling
[TMP]: https://owasp.org/www-community/Threat_Modeling_Process
[TMdesigning]: https://shostack.org/books/threat-modeling-book
[TMpractical]: https://threatmodeling.dev/
[TMT]: https://learn.microsoft.com/en-us/azure/security/develop/threat-modeling-tool
