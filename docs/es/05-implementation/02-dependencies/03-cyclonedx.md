![Logo de CycloneDX](../../../assets/images/logos/cyclonedx.png "CycloneDX de OWASP"){ align=right width=180 }

[CycloneDX][cyclonedx] de OWASP es un estándar completo de Lista de Materiales (BOM)
que proporciona capacidades avanzadas para la cadena de suministro con el fin de reducir el riesgo cibernético.
Este [proyecto][cyclonedx-project] es uno de los proyectos insignia de OWASP.

#### ¿Qué es CycloneDX?

CycloneDX es un estándar ampliamente utilizado para varios tipos de [Listas de Materiales][cyclonedx-spec].
Proporciona a la [cadena de suministro][cschain] de una organización la reducción de riesgos de seguridad del software.
La especificación provee:

* [Lista de Materiales de Software][cyclonedx-sbom] (SBOM)
* [Lista de Materiales de Software como Servicio][cyclonedx-saasbom] (SaaSBOM)
* [Lista de Materiales de Hardware][cyclonedx-hbom] (HBOM)
* [Lista de Materiales de Machine-learning][cyclonedx-mlbom] (ML-BOM)
* [Lista de Materiales de Fabricación][cyclonedx-mbom] (MBOM)
* [Lista de Materiales de Operaciones][cyclonedx-obom] (OBOM)
* [Lista de Vulnerabilidades][cyclonedx-bov] (BOV)
* [Informes de Divulgación de Vulnerabilidades][cyclonedx-vdr] (VDR)
* [Intercambio de Explotabilidad de Vulnerabilidades][cyclonedx-vex] (VEX)
* Formato común para [Notas de Lanzamiento][cyclonedx-notes]
* Sintaxis para [Vinculación de Lista de Materiales][cyclonedx-bomlink] (BOM-Link)

El proyecto CycloneDX proporciona estándares en XML, JSON y Protocol Buffers.
Existe una gran colección de herramientas oficiales y respaldadas por la comunidad que consumen
y crean BOMs de CycloneDX o interoperan con el estándar CycloneDX.

#### ¿Por qué utilizarlo?

CycloneDX es un estándar muy bien establecido para SBOMs y varios otros tipos de BOM.
Existe un enorme ecosistema construido alrededor de CycloneDX y es utilizado globalmente por muchas empresas.
Además, los SBOMs son obligatorios para muchas industrias y varios gobiernos - en algún momento,
todas las organizaciones tendrán que proporcionar SBOMs para sus clientes, y CycloneDX es un estándar aceptado para esto.

CycloneDX también proporciona estándares para otros tipos de BOMs que pueden ser requeridos en la cadena de suministro
junto con estándares para notas de lanzamiento y [divulgación responsable][csdisclose].
Es útil utilizar CycloneDX a lo largo de la cadena de suministro ya que promueve la interoperabilidad
entre las diversas herramientas.

#### Cómo utilizarlo

La serie OWASP Spotlight proporciona una visión general de CycloneDX junto con una demostración del uso de SBOMs:
'Proyecto 21 - [OWASP CycloneDX][spotlight21]'.

CycloneDX es un estándar fácil de entender que puede ser aumentado para adaptarse a todas las partes
de una cadena de suministro, y hay [muchas herramientas][cyclonedx-tools] (más de 220 a febrero de 2024)
que interoperan con CycloneDX.

La forma más sencilla de utilizar CycloneDX es seleccionar herramientas de esta lista
para cualquiera de los tipos de BOM compatibles,
con herramientas tanto propietarias/comerciales como de código abierto incluidas en la lista.
Un ejemplo común es cuando un cliente solicita que se proporcione un SBOM para una aplicación web,
y se pueden elegir [varias herramientas][cyclonedx-tools] que pueden exportar el SBOM en varios formatos.

----
Traducción de versión [original en inglés][release070203].

La Guía para Desarrolladores de OWASP es un esfuerzo comunitario;
si hay algo que necesita cambiarse, [cree un issue][issue070203] o [edítelo en GitHub][edit070203].

[release070203]: https://github.com/OWASP/www-project-developer-guide/blob/main/release/07-implementation/02-dependencies/03-cyclonedx.md
[cschain]: https://cheatsheetseries.owasp.org/cheatsheets/Software_Supply_Chain_Security_Cheat_Sheet
[csdisclose]: https://cheatsheetseries.owasp.org/cheatsheets/Vulnerability_Disclosure_Cheat_Sheet
[cyclonedx]: https://cyclonedx.org/
[cyclonedx-bomlink]: https://cyclonedx.org/capabilities/bomlink/
[cyclonedx-bov]: https://cyclonedx.org/capabilities/bov/
[cyclonedx-hbom]: https://cyclonedx.org/capabilities/hbom/
[cyclonedx-mbom]: https://cyclonedx.org/capabilities/mbom/
[cyclonedx-mlbom]: https://cyclonedx.org/capabilities/mlbom/
[cyclonedx-notes]: https://cyclonedx.org/capabilities/release-notes/
[cyclonedx-obom]: https://cyclonedx.org/capabilities/obom/
[cyclonedx-project]: https://owasp.org/www-project-cyclonedx/
[cyclonedx-saasbom]: https://cyclonedx.org/capabilities/saasbom/
[cyclonedx-sbom]: https://cyclonedx.org/capabilities/sbom/
[cyclonedx-spec]: https://cyclonedx.org/specification/overview/
[cyclonedx-tools]: https://cyclonedx.org/tool-center/
[cyclonedx-vdr]: https://cyclonedx.org/capabilities/vdr/
[cyclonedx-vex]: https://cyclonedx.org/capabilities/vex/
[edit070203]: https://github.com/OWASP/DevGuide/blob/main/docs/es/05-implementation/02-dependencies/03-cyclonedx.md
[issue070203]: https://github.com/OWASP/DevGuide/issues/new?labels=content&template=request.md&title=Update:%2005-implementation/02-dependencies/03-cyclonedx
[spotlight21]: https://youtu.be/qEG6cxwl8os
