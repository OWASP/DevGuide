![Amass logo](../../../assets/images/logos/amass.png "OWASP Amass"){ align=right width=80 }

OWASP Amass es una herramienta que proporciona gestión de superficie de ataque para los sitios web
y aplicaciones de una organización.
Se utiliza durante pruebas de penetración para el mapeo de redes de superficies de ataque
y descubrimiento de activos externos mediante la integración de varias herramientas de seguridad existentes.

El [proyecto atacante/herramienta][amass] Amass es un Proyecto Insignia de OWASP y los instaladores pueden
descargarse desde el [área de versiones][amass-download] del repositorio github del proyecto.

#### ¿Qué es Amass?

Amass es una herramienta de línea de comandos que proporciona información sobre los sitios web de una organización,
utilizando varias herramientas de recopilación de información de código abierto y técnicas de reconocimiento activo.

Se ejecuta desde la línea de comandos con [subcomandos][amass-docs]:

1. 'amass intel' recopila inteligencia sobre la organización objetivo
2. 'amass enum' realiza enumeración DNS y mapeo de red para poblar la base de datos de resultados
3. 'amass db'

Cada comando viene con un amplio conjunto de opciones que controlan las herramientas utilizadas
y el formato de los hallazgos.

#### ¿Por qué utilizarla?

Amass es una herramienta importante para los equipos de testeo de seguridad.
Amass está incluida en la distribución [Kali Linux][kali],
que es ampliamente utilizada por equipos de pruebas de penetración, con Amass proporcionando una forma sencilla
de ejecutar un amplio conjunto de herramientas de reconocimiento y enumeración.

Además, Amass es una herramienta de fácil uso que está disponible tanto para equipos de pruebas legítimos
como para actores maliciosos.
Es muy probable que cualquier organización haya sido escaneada y enumerada por Amass en algún momento,
ya sea maliciosamente o legítimamente,
por lo que es importante ejecutar la herramienta para determinar qué información puede obtener un actor malicioso.

#### Cómo utilizarla

Si se está utilizando [Kali Linux][kali], entonces Amass viene ya instalado,
de lo contrario, existe un amplio conjunto de [instaladores][amass-install] para otras plataformas.

El extenso [tutorial de Amass][amass-tutorial] proporciona la mejor manera de aprender a usar Amass y sus características.

----

Traducción de versión [original en inglés][en080202].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario; si hay algo que necesita cambios,
[cree un issue][issue080202] o [edítelo en GitHub][edit080202].

[amass]: https://owasp.org/www-project-amass/
[amass-docs]: https://github.com/owasp-amass/amass/blob/master/doc/user_guide.md
[amass-download]: https://github.com/owasp-amass/amass/releases
[amass-install]: https://github.com/owasp-amass/amass/blob/master/doc/install.md
[amass-tutorial]: https://github.com/owasp-amass/amass/blob/master/doc/tutorial.md
[edit080202]: https://github.com/OWASP/DevGuide/blob/main/docs/es/06-verification/02-tools/02-amass.md
[en080202]: https://devguide.owasp.org/en/06-verification/02-tools/02-amass/
[issue080202]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2006-verification/02-tools/02-amass
[kali]: https://www.kali.org/
