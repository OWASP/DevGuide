![Logo la guía del desarrollador](../../../assets/images/dg_logo_bbd.png "Guía del Desarrollador"){ align=right width=180 }

La gestión de dependencias de software se describe en la actividad [Dependencias de Software][sammisbsd] de SAMM,
que a su vez forma parte de la práctica de seguridad [Construcción Segura][sammisb] de SAMM
dentro de la función de negocio [Implementación][sammi].

Es importante registrar todas las dependencias utilizadas en todo el entorno de producción de la aplicación.
Esto puede lograrse mediante el Análisis de Composición de Software (SCA) para identificar las dependencias de terceros.

Una Lista de Materiales de Software (SBOM) proporciona un registro de las dependencias dentro del sistema/aplicación,
y ofrece información sobre cada dependencia para que pueda ser rastreada:

* Dónde se utiliza o referencia
* Versión utilizada
* Licencia
* Información de origen y repositorio
* Estado de soporte y mantenimiento de la dependencia

Disponer de un SBOM proporciona la capacidad de averiguar rápidamente qué aplicaciones se ven afectadas por una
[Vulnerabilidad y Exposición Común][cve] (CVE) específica, o qué CVEs están presentes en una aplicación particular.

----

Traducción de versión [original en inglés][en0702].

La Guía del Desarrollador de OWASP es un esfuerzo comunitario;
si ve algo que necesita cambios, entonces [cree un issue][issue0702] o [edítelo en GitHub][edit0702].

[cve]: https://cve.mitre.org/
[edit0702]: https://github.com/OWASP/DevGuide/blob/main/docs/es/05-implementation/02-dependencies/index.md
[en0702]: https://devguide.owasp.org/en/05-implementation/02-dependencies/
[issue0702]: https://github.com/OWASP/DevGuide/issues/new?labels=enhancement&template=request.md&title=Update:%2005-implementation/02-dependencies/index
[sammi]: https://owaspsamm.org/model/implementation/
[sammisb]: https://owaspsamm.org/model/implementation/secure-build/
[sammisbsd]: https://owaspsamm.org/model/implementation/secure-build/stream-b/
