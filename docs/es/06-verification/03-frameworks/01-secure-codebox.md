![SecureCodeBox logo](../../../assets/images/logos/securecodebox.png "OWASP SecureCodeBox"){ align=right width=250 }

OWASP [secureCodeBox][codebox] es una cadena de herramientas modularizada basada en Kubernetes
que proporciona escaneos de seguridad continuos de los proyectos y aplicaciones web de una organización.

El [proyecto constructor/herramienta][codebox-project] secureCodeBox es un Proyecto de Laboratorio OWASP
y se instala usando [Helm ChartMuseum][codebox-repo].

#### ¿Qué es secureCodeBox?

OWASP secureCodeBox combina herramientas de seguridad existentes en los dominios de análisis estático,
análisis dinámico y análisis de red.
Utiliza estas herramientas para proporcionar un panorama integral de las amenazas y vulnerabilidades
que afectan a la red y las aplicaciones de una organización.

OWASP secureCodeBox orquesta una variedad de herramientas de pruebas de seguridad en varios dominios:

* Análisis de contenedores:
  * Escáner de vulnerabilidades de contenedores Trivy
  * Escáner de dependencias de contenedores Trivy SBOM

* Análisis de Sistemas de Gestión de Contenido:
  * CMSeeK para detectar el CMS Joomla y sus vulnerabilidades principales
  * Typo3Scan para detectar el CMS Typo3 y sus extensiones instaladas
  * WPScan escáner de vulnerabilidades de Wordpress

* Análisis de Kubernetes:
  * Kube Hunter escáner de vulnerabilidades
  * Kubeaudit escáner de configuración

* Análisis de red:
  * Amass escáner de enumeración de subdominios
  * doggo cliente DNS
  * Ncrack fuerza bruta de autenticación de red
  * Nmap descubrimiento de red y auditoría de seguridad
  * Whatweb identificación de sitios web

* Análisis de repositorios:
  * Git Repo Scanner para descubrir repositorios Git
  * Gitleaks para encontrar posibles secretos en repositorios
  * Semgrep análisis estático de código

* Escaneo de configuración y políticas SSH/TLS con SSH-audit y SSLyze

* Análisis de aplicaciones web:
  * ffuf descubrimiento de elementos y contenido de servidores web y aplicaciones web
  * Nikto escáner de vulnerabilidades de servidores web
  * Nuclei escáner de vulnerabilidades basado en plantillas
  * Screenshooter toma capturas de pantalla de sitios web
  * ZAP escáner avanzado de vulnerabilidades de aplicaciones web y OpenAPI

Con el tiempo se pueden añadir otras herramientas.

#### ¿Por qué usarlo?

OWASP secureCodeBox proporciona la potencia de las principales herramientas de pruebas de seguridad de código abierto
con una plataforma multi-escáner.
Esto proporciona la capacidad de ejecutar escaneos rutinarios de forma continua y automática
en la infraestructura de red y aplicaciones de una organización.

OWASP secureCodeBox es completamente escalable y puede configurarse por separado
para múltiples equipos, sistemas o clústeres.

#### Cómo usarlo

OWASP secureCodeBox se ejecuta en [Kubernetes][kube] y utiliza [Helm][helm] para la instalación
usando [Helm ChartMuseum][codebox-repo].
Hay una excelente guía, '[Iniciando tus primeros escaneos][codebox-start]' para comenzar con secureCodeBox,
con el resto de la [documentación][codebox-docs] que proporciona información clara sobre la configuración
y ejecución de secureCodeBox.

#### Referencias

* OWASP [secureCodeBox][codebox]
* [Kubernetes][kube] orquestador de contenedores
* [Helm][helm] gestor de paquetes para Kubernetes

----

Traducción de versión [original en inglés][en080301].

La Guía para Desarrolladores de OWASP es un esfuerzo comunitario; si hay algo que necesita cambiarse,
[cree un issue][issue080301] o [edítelo en GitHub][edit080301].

[codebox]: https://www.securecodebox.io/
[codebox-project]: https://owasp.org/www-project-securecodebox/
[codebox-repo]: https://charts.securecodebox.io
[codebox-start]: https://www.securecodebox.io/docs/getting-started/first-scans
[codebox-docs]: https://www.securecodebox.io/docs/getting-started/installation
[edit080301]: https://github.com/OWASP/DevGuide/blob/main/docs/es/06-verification/03-frameworks/01-secure-codebox.md
[helm]: https://helm.sh/
[en080301]: https://devguide.owasp.org/en/06-verification/03-frameworks/
[issue080301]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2006-verification/03-frameworks/01-secure-codebox
[kube]: https://kubernetes.io/
