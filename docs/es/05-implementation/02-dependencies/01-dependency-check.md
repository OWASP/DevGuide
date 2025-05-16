![Logo de DepCheck](../../../assets/images/logos/depcheck.png "OWASP Dependency-Check"){ width=250 }

OWASP [Dependency-Check][depcheck] es una herramienta que proporciona Análisis de Composición de Software (SCA)
desde la línea de comandos.
Identifica las bibliotecas de terceros en un proyecto de aplicación web
y verifica si estas bibliotecas son vulnerables utilizando la [base de datos NVD][nist-db].

Dependency-Check es un proyecto Insignia (Flagship) de OWASP y puede descargarse desde el área
de [versiones de GitHub][depcheck-download].
Dependency-Check se inició en septiembre de 2012 y desde entonces ha recibido soporte continuo con versiones regulares.

#### ¿Qué es Dependency-Check?

Dependency-Check es una herramienta de Análisis de Composición de Software (SCA) que intenta detectar
vulnerabilidades públicas contenidas dentro de las dependencias de un proyecto.
Lo hace determinando si existe un identificador de enumeracion de plataforma común - [Common Platform Enumeration][cpe]
(CPE) para una dependencia dada.

El motor principal contiene una serie de analizadores que inspeccionan las dependencias del proyecto
e identifican el CPE para la dependencia dada.
Si se identifica un CPE, entonces se hace referencia cruzada con la [base de datos CVE de NIST][nist-db]
y cualquier entrada [Common Vulnerability and Exposure][cve] (CVE) asociada se lista en el informe.

El motor de análisis principal de Dependency-Check puede usarse como:

* una Tarea Ant
* una Herramienta de Línea de Comandos
* Plugin de Gradle
* Plugin de Jenkins
* Plugin de Maven
* Plugin de SBT

#### ¿Por qué usarlo?

La verificación de componentes vulnerables, '[A06 Componentes Vulnerables y Desactualizados][a06]', está en el OWASP Top 10
y es una de las actividades de seguridad más directas y efectivas para implementar.
La herramienta Dependency-Check proporciona verificaciones de componentes vulnerables
que podrían ejecutarse desde la línea de comandos.

Esto es útil para los equipos de desarrollo; la capacidad de verificar componentes vulnerables
de la aplicación desde la línea de comandos
proporciona retroalimentación inmediata al desarrollador sin tener que esperar a que se ejecute un pipeline.

Dependency-Check también proporciona plugins para verificar componentes vulnerables en [pipelines CI/CD][cscicd].

#### Cómo usarlo

La serie OWASP Spotlight proporciona un ejemplo de los riesgos involucrados en el uso de bibliotecas desactualizadas
y vulnerables, y cómo usar Dependency-Check: 'Project 2 - [OWASP Dependency Check][spotlight02]'.

Consulte la [documentación][depcheck-docs] de Dependency-Check para comenzar a ejecutarlo desde la línea de comandos:

* asegúrese de que Java está instalado, por ejemplo desde [Eclipse Adoptium][adoptium]
* descargue y descomprima la última [versión][depcheck-download] de Dependency-Check
* navegue al directorio 'bin' de Dependency-Check y ejecútelo, usando Threat Dragon como ejemplo:
  `./dependency-check.sh --project "Threat Dragon" --scan ~/github/threat-dragon`
* abra el archivo de salida html y actúe según los hallazgos

La línea de comandos es útil para la depuración inmediata durante el desarrollo.
Dependiendo del entorno de automatización que esté en funcionamiento, también se puede instalar un plugin
en un pipeline que luego puede generar los informes SCA.

#### Referencias

* Proyecto [Dependency-Check][depcheck] de OWASP
* Documentación de [Dependency-Check][depcheck-docs] de OWASP
* [Hoja de Referencia de Seguridad CI/CD][cscicd] de OWASP
* [Top 10][a06] de OWASP

----

Traducción de versión [original en inglés][en070201].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario;
si hay algo que necesita cambiarse entonces [cree un issue][issue070201] o [edítelo en GitHub][edit070201].

[a06]: https://owasp.org/Top10/A06_2021-Vulnerable_and_Outdated_Components/
[adoptium]: https://adoptium.net/
[cpe]: https://nvd.nist.gov/products/cpe
[cscicd]: https://cheatsheetseries.owasp.org/cheatsheets/CI_CD_Security_Cheat_Sheet
[cve]: https://cve.mitre.org/
[depcheck]: https://owasp.org/www-project-dependency-check/
[depcheck-docs]: https://jeremylong.github.io/DependencyCheck/
[depcheck-download]: https://github.com/jeremylong/DependencyCheck/releases
[edit070201]: https://github.com/OWASP/DevGuide/blob/main/docs/es/05-implementation/02-dependencies/01-dependency-check.md
[en070201]: https://devguide.owasp.org/en/05-implementation/02-dependencies/01-dependency-check/
[issue070201]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2005-implementation/02-dependencies/01-dependency-check
[nist-db]: https://nvd.nist.gov/
[spotlight02]: https://youtu.be/YAXf3TaAYeA

\newpage
