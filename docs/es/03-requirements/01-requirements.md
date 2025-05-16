Esta sección trata sobre los Requisitos de Seguridad, que es una práctica de seguridad
en la sección de función empresarial de Diseño del Modelo de Madurez de Garantía de Software de OWASP ([SAMM][samm]).
Esta práctica de requisitos de seguridad tiene dos actividades: Requisitos de Software y Seguridad de Proveedores,
siendo los requisitos regulatorios y estatutarios un subconjunto importante de ambas actividades.

#### Descripción general

Los requisitos de seguridad son parte de cada proceso de desarrollo seguro
y forman la base de la postura de seguridad de la aplicación.
Los requisitos ayudarán sin duda en la prevención de muchos tipos de vulnerabilidades.

Los requisitos provienen de diversas fuentes, siendo tres las más comunes:

1. Requisitos relacionados con el software que especifican objetivos y expectativas
    para proteger el servicio y los datos en el núcleo de la aplicación
2. Requisitos relativos a organizaciones proveedoras que son parte del contexto de desarrollo de la aplicación
3. Requisitos regulatorios y reglamentarios

Idealmente, los requisitos de seguridad se integran al inicio del desarrollo,
pero no hay un mal momento para considerar estos requisitos de seguridad y añadir nuevos cuando sea necesario.

#### Requisitos de software

Definir requisitos de seguridad puede ser desalentador a veces,
por ejemplo, pueden hacer referencia a técnicas criptográficas que pueden aplicarse incorrectamente,
pero es completamente aceptable expresar estos requisitos en lenguaje cotidiano.
Por ejemplo, un requisito de seguridad podría escribirse como "Identificar al usuario de la aplicación en todo momento"
y esto es ciertamente suficiente para requerir que la autenticación se incluya en el diseño.

La práctica de [Requisitos de Seguridad][sammdsr] de SAMM enumera los niveles de madurez
de los requisitos de seguridad de software
que especifican objetivos y expectativas.
Elija el nivel apropiado para la organización y el equipo de desarrollo,
con la comprensión de que cualquiera de estos niveles es completamente aceptable.

Los niveles de madurez de los requisitos de seguridad de software son:

1. Los objetivos de seguridad de la aplicación de alto nivel son mapeados a requisitos funcionales
2. Requisitos de seguridad estructurados están disponibles y son utilizados por equipos de desarrollo
3. Construir un marco de requisitos para que los equipos de producto lo utilicen

OWASP proporciona proyectos que pueden ayudar a identificar requisitos de seguridad
que protegerán el servicio y los datos en el núcleo de la aplicación.
El [Estándar de Verificación de Seguridad de Aplicaciones][asvs] proporciona una lista de requisitos
para el desarrollo seguro,
y puede usarse como punto de partida para los requisitos de seguridad.
La [Seguridad de Aplicaciones Móviles][mas] proporciona un conjunto similar de requisitos de seguridad estándar
para aplicaciones móviles.

Considere usar [Casos de Abuso][csabuse] para identificar posibles ataques y los controles necesarios para mitigarlos.
Esto puede luego formar parte de los requisitos de seguridad de software.

#### Seguridad de proveedores

Los proveedores externos involucrados en el proceso de desarrollo deben ser
evaluados por sus prácticas de seguridad y cumplimiento.
Dependiendo de su nivel de participación, estos proveedores pueden tener
un impacto significativo en la seguridad de la aplicación,
por lo que será necesario negociar con ellos un conjunto de requisitos de seguridad.

[SAMM][sammdsr] enumera los niveles de madurez para los requisitos de seguridad
que aclararán las fortalezas y debilidades de sus proveedores.
Tenga en cuenta que la seguridad de los proveedores es distinta de la seguridad de software
y bibliotecas de terceros, y se trata el uso de software de terceros y de código abierto
en su propia sección sobre verificación y seguimiento de dependencias.

Los niveles de madurez de los requisitos de seguridad de proveedores son:

1. Evaluar al proveedor según los requisitos de seguridad organizacionales
2. Incorporar la seguridad en los acuerdos con proveedores para garantizar
    el cumplimiento de los requisitos organizacionales
3. Asegurar una cobertura de seguridad adecuada para proveedores externos proporcionando objetivos claros

#### Requisitos regulatorios y reglamentarios

Los requisitos regulatorios pueden incluir requisitos de seguridad que deben tenerse en cuenta.
Diferentes industrias están reguladas en mayor o menor medida,
y el único consejo general es estar consciente de ellos y seguir las regulaciones.

Diferentes jurisdicciones tendrán distintos requisitos reglamentarios que pueden resultar en requisitos de seguridad.
Cualquier requisito de seguridad reglamentario aplicable debe añadirse a los requisitos de seguridad de la aplicación.
De manera similar a los requisitos regulatorios,
el único consejo general es estar familiarizado y seguir los requisitos reglamentarios apropiados.

#### Revisión periódica

Los requisitos de seguridad deben identificarse y registrarse al inicio de cualquier nuevo desarrollo
y también cuando se añaden nuevas características a una aplicación existente.
Estos requisitos de seguridad deben revisarse periódicamente y modificarse según sea necesario;
por ejemplo, los estándares de seguridad se actualizan y entran en vigor nuevas regulaciones,
ambos pueden tener un impacto directo en la aplicación.

#### Referencias

* Proyectos OWASP:
  * [Modelo de Madurez de Garantía de Software (SAMM)][samm]
  * [Top 10 Controles Proactivos][proactive10]
  * [Estándar de Verificación de Seguridad de Aplicaciones (ASVS)][asvs]
  * [Seguridad de Aplicaciones Móviles][mas]

----

Traducción de versión [original en inglés][en0501].

La Guía del Desarrollador OWASP es un esfuerzo comunitario; si hay algo que necesite cambios
entonces [cree un issue][issue0501] o [edítelo en GitHub][edit0501].

[asvs]: https://owasp.org/www-project-application-security-verification-standard/
[csabuse]: https://cheatsheetseries.owasp.org/cheatsheets/Abuse_Case_Cheat_Sheet
[edit0501]: https://github.com/OWASP/DevGuide/blob/main/docs/es/03-requirements/01-requirements.md
[en0501]: https://devguide.owasp.org/en/03-requirements/01-requirements/
[issue0501]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2003-requirements/01-requirements
[mas]: https://mas.owasp.org/
[proactive10]: https://owasp.org/www-project-proactive-controls/
[samm]: https://owaspsamm.org/about/
[sammdsr]: https://owaspsamm.org/model/design/security-requirements/
