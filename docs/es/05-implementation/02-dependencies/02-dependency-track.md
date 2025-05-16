OWASP Dependency-Track es una plataforma inteligente para el Análisis de Componentes, incluido Software de Terceros.
Permite a las organizaciones identificar y reducir riesgos en la [cadena de suministro de software][cschain]
utilizando su capacidad para analizar una Lista de Materiales de Software (SBOM).

[Dependency-Track][deptrack-project] es un proyecto Insignia (Flagship) de OWASP
y puede instalarse utilizando un archivo docker-compose desde el [sitio web][deptrack] de Dependency-Track.

#### ¿Qué es Dependency-Track?

La herramienta [Dependency-Track][deptrack] proporciona a una organización un dashboard para analizar, supervisar
y controlar los componentes de todos sus proyectos.
Realiza un seguimiento del uso de componentes en todas las aplicaciones del portafolio
de una organización mediante el análisis de exportaciones
de múltiples proyectos dentro de la organización, a través de SBOMs de CycloneDX y Vulnerability Exploitability Exchange.

Proporciona soporte completo para todo tipo de componentes, incluidos hardware y servicios.
Dependency-Track identifica múltiples formas de riesgo, incluidos componentes con vulnerabilidades conocidas,
mediante la integración con múltiples fuentes de inteligencia de vulnerabilidades como la
Base de Datos Nacional de Vulnerabilidades (NVD), asesorías de seguridad de GitHub y otros.

Tiene soporte incorporado para varios tipos de repositorios,
y proporcionará riesgo y cumplimiento para seguridad, riesgo y operaciones.
Consulte la [Documentación][deptrack-docs] para obtener más información
sobre las características proporcionadas por Dependency-Track.

#### ¿Por qué usarlo?

Al aprovechar las capacidades de la Lista de Materiales de Software (SBOM), Dependency-Track proporciona funcionalidades
que las soluciones tradicionales de Análisis de Composición de Software (SCA) difícilmente podrían lograr.

El dashboard de Dependency-Track tiene la capacidad de analizar todos los proyectos de software dentro de una organización.
Se integra con numerosas plataformas de notificación, por ejemplo Slack y Microsoft Teams, y puede enviar resultados
a varias herramientas de agregación de vulnerabilidades como DefectDojo o Fortify.

Dependency-Track es rico en funcionalidades, proporciona integraciones
y características que la mayoría de las organizaciones necesitarán;
consulte la [Introducción a la Documentación][deptrack-docs] para obtener una lista completa de estas características.

#### Cómo usarlo

La serie OWASP Spotlight proporciona una visión general del seguimiento de dependencias
y la inspección de SBOMs utilizando Dependency-Track:
'Project 15 - [OWASP Dependency-Track][spotlight15]'.

Siga la [guía de inicio][deptrack-docs] para instalar la herramienta Dependency-Track,
utilizando la implementación recomendada de un contenedor Docker.

Aunque Dependency-Track se ejecutará con su configuración predeterminada,
debe configurarse según las necesidades específicas de la organización.
El archivo de configuración de Dependency-Track es importante para ejecutar la herramienta de manera óptima,
pero esto está fuera del alcance de la Guía del Desarrollador - consulte la
[documentación][deptrack-docs] de Dependency-Track para obtener una guía paso a paso de este proceso de configuración.

----

Traducción de versión [original en inglés][en070202].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse
entonces [cree un issue][issue070202] o [edítelo en GitHub][edit070202].

[cschain]: https://cheatsheetseries.owasp.org/cheatsheets/Software_Supply_Chain_Security_Cheat_Sheet
[deptrack]: https://dependencytrack.org/
[deptrack-docs]: https://docs.dependencytrack.org/
[deptrack-project]: https://owasp.org/www-project-dependency-track/
[edit070202]: https://github.com/OWASP/DevGuide/blob/main/docs/es/05-implementation/02-dependencies/02-dependency-track.md
[en070202]: https://devguide.owasp.org/en/05-implementation/02-dependencies/02-dependency-track/
[issue070202]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2005-implementation/02-dependencies/02-dependency-track
[spotlight15]: https://youtu.be/irnZuLq4MDM
